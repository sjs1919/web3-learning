# Web3 Wallet 项目实践学习（逐阶段推进）

> 协作分工：**本仓库（web3-learning）= 学习整理**；**web3-wallet = Claude Code 实现功能代码**
> 依据：《Web3转行学习清单.md》 + 《LearningPlan.md》（12 周 / 5 阶段，按周推进）
> 项目：`D:\workspace\projects\web3-wallet`（Vue3 + Java17/Spring Cloud Alibaba + web3j 4.9.7 + MySQL/Redis + Foundry anvil）

---

## 一、项目 ↔ 学习阶段映射（整体路线）

| 学习阶段（LearningPlan） | 对应项目模块 | 这一阶段「我学」 | 「Claude Code 实现」 |
|---|---|---|---|
| ① 读懂一笔链上交易（第1–2周） | —（概念为主） | 区块/交易/账户/Gas/签名/钱包 | 无（纯概念，可在读到代码时对照） |
| ② 用熟悉语言接入链（第3–4周） | **account-service**（最小学习闭环） | web3j 接链、RPC、余额、转账、地址 | 本地链转账 + 余额查询 |
| ③ 把链上数据接稳（第5–6周） | **deposit-scanner** | 扫描入账、检查点、去重、重组、账务 | 充值扫描模块 |
| ④ 管好提现与交易状态（第7–8周） | **withdrawal-service** | 提现状态机、幂等、Nonce、签名边界 | 提现签名模块 |
| ⑤ 做成面试材料（第9–12周） | 全项目收尾 | 对账、监控、演示、简历 | 对账 + 运维 + 演示 |

> 当前进度：**第 0 步（骨架）已完成，正在进入第 1 步：最小学习闭环（阶段②）**。

---

## 二、项目现状（骨架里已有什么 / 缺什么）

### 已有（基础设施骨架）
- **backend/pom.xml**：Spring Boot 3.2.4、Spring Cloud Alibaba 2023.0.1.0、web3j 4.9.7；modules = `common / gateway / account-service`（deposit-scanner、withdrawal-service 未挂载，阶段③④再启用）
- **common**：`ErrorCode`（5 位错误码）、`BusinessException`、`GlobalExceptionHandler`、`Result`
- **gateway**：`GatewayApplication` + `application.yml`（Spring Cloud Gateway 网关）
- **account-service**：仅 `/account/health` 健康检查；`AccountService` 只有 `health()` 接口
- **规范**：`CLAUDE.md` 红线（禁自动 git、私钥/助记词禁入库、金额用 BigDecimal、未测试禁部署）、`rules/` 三层规范、`docs/` 文档仓
- 环境：Java 17 + Maven（WSL，阿里云镜像）+ Foundry anvil 本地链（8545）

### 缺口（本阶段要实现的「最小学习闭环」）
- ❌ web3j 连接 anvil 本地链
- ❌ 余额查询（按地址查余额，wei→可读单位）
- ❌ 转账（构建交易 → 签名 → 广播 → 等回执）
- ❌ 地址/密钥管理（本地密钥，仅学习用）
- ❌ 前端 `web/` 完全为空（Vue3 项目未初始化）

---

## 三、第 1 步 · 最小学习闭环（对应阶段②：用熟悉语言接入链）

> 目标（README 定义）：**本地链转账 + 余额查询**，验证 web3j 接链 + 技术栈可行性。
> 我整理下面 6 个学习单元，每个单元：**学什么 → 要理解的概念 → 项目里对应要实现的（给 Claude Code）→ 怎么验证**。

### 单元 1｜web3j 连接本地链（anvil）
**学什么**
- web3j 是 Java 的 Ethereum 客户端库，封装了 JSON-RPC
- `Web3j.build(HttpService("http://localhost:8545"))` 连接节点；anvil 默认 8545
- 用 `web3j.web3ClientVersion()` 验证连通（对应 JSON-RPC `web3_clientVersion`）

**要理解的概念**：RPC 端点 / 节点；JSON-RPC 是传输协议，web3j 是它的 Java 封装；本地链 vs 主网/测试网

**给 Claude Code 实现**：一个 `Web3jConfig` 配置类 + 连通性检查（health 可扩展为同时探 web3 连通）

**验证**：`anvil` 启动后，应用启动日志显示成功连上本地链

### 单元 2｜查询余额（getBalance）
**学什么**
- `web3j.ethGetBalance(address, blockParam)` 返回 `EthGetBalance`，数值在 `balance.getValue()`（`BigInteger`，单位 **wei**）
- **wei → ETH 换算**：1 ETH = 10¹⁸ wei；用 `Convert.fromWei(wei, Unit.ETHER)`
- 金额精度：链上整数（wei / BigInteger）与业务 BigDecimal 之间转换要精确，**禁止 float/double**（项目红线）
- blockParam：`DefaultBlockParameterName.LATEST` / `PENDING`，理解"最新已确认" vs "待确认"

**要理解的概念**：原生币余额、最小单位、wei/ETH；读操作（eth_call）不改状态

**给 Claude Code 实现**：`GET /account/{address}/balance` → 返回该地址余额（BigDecimal ETH + 原始 wei）

**验证**：anvil 预置账户余额非 0，接口返回正确；手工 `cast balance <addr>` 对照

### 单元 3｜地址与密钥管理（学习用）
**学什么**
- 以太坊账户 = 私钥 → 公钥 → 地址；谁有私钥谁掌控资产
- anvil 启动时会打印一组测试账户（带私钥），用于本地开发
- web3j `Credentials.create(privateKey)` 由私钥生成凭证；`credentials.getAddress()`
- **红线：私钥/助记词严禁入库**，只留占位符，真实值在 gitignored 的 `docs/credentials.local.md` 或环境变量

**要理解的概念**：私钥/公钥/地址关系、HD 钱包/助记词（了解）、只用于学习、不放真实资金

**给 Claude Code 实现**：账户相关接口（如列出学习账户、按地址查），密钥走环境变量，不硬编码

### 单元 4｜转账（构建 → 签名 → 广播 → 回执）
**学什么**
- 一笔交易：`from` / `to` / `value` / `data` / `Nonce` / `gasPrice` / `gasLimit` / `ChainID`
- web3j 流程：`TransactionManager` 或 `Transfer.sendFunds(...)` 构建并签名 → `ethSendTransaction` 广播 → 拿 txHash → `ethGetTransactionReceipt` 等回执
- **Nonce**：账户的交易序号，防止重放；同地址并发发送要管好 Nonce
- **Gas**：为什么转账要手续费；anvil 本地链 gasPrice 可设为 0
- 回执里的 `status`（0x1 成功 / 0x0 失败）与 `logs`

**要理解的概念**：交易生命周期、签名边界（谁在签）、广播 vs 确认、回执证明什么（回到阶段①的"成功回执能证明什么"）

**给 Claude Code 实现**：`POST /account/transfer`（from 私钥、to 地址、value）→ 完成签名广播，返回 txHash；并提供一个"按 txHash 查回执状态"接口

**验证**：转账后 from 余额减、to 余额增；`cast tx <txHash>` 对照；重启应用后仍能查到该交易（不是只打印一次）

### 单元 5｜金额与数据模型（BigDecimal 红线）
**学什么**
- 链上金额是整数最小单位（wei），业务账务用 **BigDecimal** 精确十进制
- 换算不可用 double：`Convert.fromWei` / `toWei` 都是精确的
- 数据库存金额：最小单位整数（BIGINT）或 BigDecimal，禁止 float/double

**要理解的概念**：金额精度为什么重要（回到阶段①的"不能假设所有代币都是 18 位精度"）

**给 Claude Code 实现**：金额传输 DTO 用 String/BigDecimal，链上换算在 service 层精确处理

### 单元 6｜测试（TDD / 分层）
**学什么**
- web3j 单测：mock 返回值测 service 逻辑
- 集成：用 **anvil 本地链**做真实转账/余额测试（不需要主网）
- 项目规范：`cd backend && mvn test` 全过才可提请部署（红线）

**要理解的概念**：区分业务失败 vs RPC 故障（回到阶段②验收）；测试怎么隔离外部链

**给 Claude Code 实现**：AccountService 单测 + 一条 anvil 集成测试（转账→余额变化）

---

## 四、第 1 步验收标准（勾完才算进入第 3 步）

- ☐ `anvil` 启动，后端能连上并查询余额
- ☐ 能对一个地址查余额（返回 wei + 可读 ETH），与 `cast balance` 一致
- ☐ 能完成一次转账：广播返回 txHash，查询回执 status 成功，from 减 / to 增
- ☐ 重启应用后仍能查到这笔交易（不丢失）
- ☐ 金额全程 BigDecimal / wei 整数，无 float/double
- ☐ 私钥不在代码与仓库中（走环境变量 / 占位符）
- ☐ `mvn test` 全过；前端 `npm run build` 通过（若 web 已初始化）
- ☐ 前端 `web/` 至少能展示一个地址的余额（Vue3 已初始化时）

> 全部勾完 = 阶段②目标达成，进入**第 3 步：充值扫描模块（阶段③，deposit-scanner）**。

---

## 五、后续阶段预告（逐一开始）

| 下一步 | 阶段 | 我整理的学习主题 | Claude Code 实现的模块 |
|---|---|---|---|
| 第 3 步 | ③ 把链上数据接稳 | 扫描入账、检查点、去重、账务一致、重组 | `deposit-scanner`（挂载进 pom） |
| 第 4 步 | ④ 管好提现与交易状态 | 提现状态机、幂等、Nonce、签名边界 | `withdrawal-service`（挂载进 pom） |
| 第 5 步 | ⑤ 做成面试材料 | 对账、监控、演示、简历 | 对账 + 运维 + 文档收尾 |

每进入下一步前，我会先把该阶段的学习单元整理好（对照上面的单元结构），再让 Claude Code 按验收标准实现。
