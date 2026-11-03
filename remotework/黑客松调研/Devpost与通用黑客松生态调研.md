# Devpost 与通用（非 Web3）编程黑客松生态调研

> 调研基准日：2026-10-29（美西时间）。所有奖池金额、日期、规则均以官方页面最新公布为准。
> 证据标注：[官方原文] = 平台帮助中心/条款/官方赛事页原文；[官方介绍] = 平台官网营销/博客/客户案例；[权威背景] = 官方文档引用的规范；[未能查证] = 未打开官方页面核实。

---

## 1. Devpost 深挖

### 1.1 平台定位与运作方式

Devpost 是面向软件开发者的在线黑客松/编程竞赛托管与作品展示平台。按其服务条款的定义，平台上有两类角色：

- **Makers（参赛者）**：创建技能与作品档案（portfolio），提交软件项目参加比赛；
- **Posters（主办方）**：在平台上发布黑客松，提出需求、规则与奖金，吸引开发者参赛。[官方原文] https://info.devpost.com/legal/terms-of-service

Devpost 官方自我定位为"the leading hackathon platform to engage developers at scale"，为企业提供注册、项目提交、评审的一体化线上平台，并附带专家托管服务（managed services）；官方营销页称可触达"a global community of 6M+ developers"。[官方介绍] https://info.devpost.com/product/public-hackathons
（注：其官网另一分页仍写"4M+ developers"，两处口径不一致，具体数字以官方最新页面为准。）[官方介绍] https://info.devpost.com/?page=2

**标准参赛闭环（浏览 → 报名 → 提交 → 评审 → 颁奖）：**

1. **浏览/搜索赛事**：在 https://devpost.com/hackathons 发现赛事，查看 Overview、Rules、Judging、Prizes、Participants 等页签。
2. **报名（Register / Join Hackathon）**：点击"Join hackathon"，需注册免费 Devpost 账号；报名用于接收赛事更新并获得提交资格。[官方原文] https://help.devpost.com/article/126-know-your-submission-steps
3. **提交（Submit）**：在赛事页点击"Start project"创建项目，按 5 步表单完成：[官方原文] https://help.devpost.com/article/126-know-your-submission-steps
   - Step 1 Manage team：通过邮件邀请队友，可个人参赛；
   - Step 2 Project Overview：项目名（必填）、tagline/一句话简介（必填）、缩略图（JPG/PNG/GIF，≤5MB，建议 3:2）；
   - Step 3 Project Details：项目故事（支持 Markdown/LaTeX，必填）、"Built with"技术标签（最多 25 个，须标注赞助商工具）、Try it out 链接、图片画廊、**演示视频链接（通常必填，须公开托管在 YouTube 或 Vimeo）**；
   - Step 4 Additional Details：赛事定制问题——可选文件上传（≤35MB，zip/pdf/word/apk）、提交者类型（个人/团队/组织）、居住国家、类别、代码仓库 URL、MIT License 确认、公开可访问确认、赛事期间改进说明、开发者账号 ID 等；
   - Step 5 Submit：同意赛事条款后提交；截止前可随时修改草稿。[官方原文] 同上；条款明确：提交期结束后不得再改动参赛提交物（portfolio 里的项目仍可继续更新）。[官方原文] https://info.devpost.com/legal/terms-of-service
4. **评审（Judging）**：平台支持两种方式——[官方原文] https://help.devpost.team/article/230-how-to-set-up-judging
   - **正式评审（Judging only，最常见）**：主办方设定评分标准（criteria），评委登录后按 1–5 分打分；[官方原文] https://help.devpost.com/article/131-setting-up-judging
   - **公开投票（Public Voting）**：可选；每个已验证 Devpost 账号对每个提交限投 1 票、仅限一个账号；禁止买票/刷票，违规票作废，主办方有权取消相关提交。[官方原文] https://info.devpost.com/legal/terms-of-service
5. **颁奖（Prizes）**：奖金由**主办方（Poster）承担与发放**。条款规定主办方义务包括：公平公正、公布并遵守 Official Rules、必须兑现网站上宣传的奖金、并标注奖金的真实应税现金价值。[官方原文] https://info.devpost.com/legal/terms-of-service 若赛事为 Devpost 托管（Managed by Devpost），Devpost 团队协助后勤与"prize fulfillment（奖金兑付）"。[官方介绍] https://info.devpost.com/customer-stories/google-hackathons-on-devpost
   - 具体到账方式、税务处理由每个赛事的 Official Rules 规定，平台无统一发放通道。[未能查证：未找到 Devpost 统一的奖金打款 FAQ]

### 1.2 参赛资格（Eligibility）

- **平台层面**：须年满 13 周岁；未满 13 岁不得注册；未成年人可由父母/监护人代为注册并参赛获奖。[官方原文] https://info.devpost.com/legal/terms-of-service
- **赛事层面**：具体资格由各赛事的 Official Rules 规定，优先于平台条款。常见限定：达到居住国法定成年年龄、排除特定国家/地区（出口管制等原因）、学生限定、团队人数上限等。[官方原文] https://info.devpost.com/legal/terms-of-service
- **团队/组织参赛**：须指定一名授权代表（Representative），该代表须满足赛事资格要求。[官方原文] 同上

### 1.3 提交物要求小结（平台通用底线）

- 项目名 + tagline + 项目故事（Markdown/LaTeX）[官方原文]
- 演示视频（YouTube/Vimeo 公开链接，时长限制看各赛事规则）[官方原文]
- "Built with"标签须包含赞助商指定工具/API；代码仓库公开可访问（评审期间保持可用）[官方原文]
- 可上传文件 ≤35MB（zip/pdf/word/apk）[官方原文]
- 提交物须为本人原创工作，不得抄袭/刷量；主办方有权要求验证项目真实可运行及参赛者角色，拒绝配合可取消资格。[官方原文] https://info.devpost.com/legal/terms-of-service

### 1.4 真实企业主办赛事示例（官方页面，已打开核对）

**示例 A：Meta VR Start Developer Competition 2026**
- 官方页面：https://start-developer-competition-26.devpost.com/ [官方原文]
- 主办方：Meta；标注"Managed by Devpost"；线上、Public；
- 奖池：**$1,000,000 in cash**（顶级单项 $100,000）；截止：**Nov 18, 2026 @ 3:00pm EST**（以页面最新公布为准）；页面显示 4267 名参赛者；
- 形式：8 周挑战，面向 Meta VR Start 计划成员，分 Entertainment / Gaming / Productivity 三条 track，每条 track 分"全新项目"与"已有项目重大更新"两个 division；
- 提交要求：可运行 build（APK 通过 Meta VR Dashboard 发放邀请链接，或 WebXR 部署链接）+ ≤3 分钟演示视频（YouTube/Vimeo）+ 完整提交表单；评审维度为 Innovation & Creativity、Experience Design、Technical Implementation、Polish & Presentation。

**示例 B：Google（客户案例，证明主办方类型）**
- Devpost 官方客户案例：自 2019 年起为 Google 托管黑客松，提供注册/组队/评审平台、赛事后勤、参赛者支持与奖金兑付，并将 Google 与平台全球开发者社群对接。[官方介绍] https://info.devpost.com/customer-stories/google-hackathons-on-devpost
- Devpost 官方招聘页列出其客户包括 Amazon、Google、Microsoft、Atlassian、Square、Meta、Snap、Ford 及大量初创与非营利组织。[官方介绍] https://info.devpost.com/careers?page=3

### 1.5 主要主办方类型

- **科技企业（产品推广/开发者生态运营）**：Meta、Google、Amazon、Microsoft 等——核心目的是让开发者上手其 SDK/AI 工具，拉动产品采用与生态建设。[官方介绍] https://info.devpost.com/product/public-hackathons
- **学生赛事**：官方明确"学生可在 Devpost 上免费举办自己的黑客松"（线上/线下）。[官方介绍] https://info.devpost.com/product/public-hackathons
- **初创公司与非营利组织**：见上述客户名单。[官方介绍] https://info.devpost.com/careers?page=3
- 另有 **Devpost for Teams**：面向企业的内部私密黑客松工具线。[官方原文] https://help.devpost.team/article/230-how-to-set-up-judging

### 1.6 "参赛者被公司看到/招聘"的官方说法

- Devpost 条款中确实存在**面向雇主的 Terms of Service（for Employers）**与**面向求职者的 Terms of Service（for Candidates）**，说明平台自带招聘连接功能，但条款未承诺"参赛即获录用"。[官方原文] https://info.devpost.com/legal/terms-of-service
- 官方博客有一篇参赛者现身说法（User story: Brij）：作者称通过参赛和公开展示项目拓展人脉，在交流中认识了 Thomson Reuters 的招聘人员，先后拿到三段实习并最终转为全职。[官方介绍] https://info.devpost.com/blog/user-story-brij
- 官方帮助中心说明：Devpost portfolio（devpost.com/username）是公开作品档案页，任何人可访问，用于展示项目。[官方原文] https://help.devpost.com/article/115-what-is-a-devpost-portfolio-and-how-do-i-use-it
- **结论**：官方层面只提供"作品集曝光 + 官方博客案例"，**没有任何"参赛必被公司挖/保证求职成功"的官方承诺**；求职价值属于间接、案例性的。[官方介绍]

---

## 2. 通用黑客松生态补充：MLH（Major League Hacking）

### 2.1 平台定位

MLH 官方自我定位为"The World's Largest Developer Community"，业务覆盖黑客松、Fellowship（奖学金/实习替代项目）与 DEV 的在线社区；官方首页数据：**5M+ developers、1000+ annual events、100 countries**；其列举的社区支持者包括 Google、GitHub、ElevenLabs、Snowflake。[官方介绍] https://www.mlh.com/

与 Devpost 的差异：**MLH 不是"企业悬赏赛"托管平台，而是学生/线下周末黑客松的认证（sanction）与组织者服务体系**——为本地学生赛事提供规则模板、行为准则、纪律政策与组织者指南；同时运营自己的 Fellowship：12 周全远程、带 stipend（津贴）的开源协作项目，定位为"internship alternative（实习替代）"。[官方介绍] https://www.mlh.com/

### 2.2 规则要点（MLH 官方组织者指南，推荐标准规则）

来源：MLH Hackathon Organizer Guide（标准规则模板，同时引用 GitHub 上 mlh-policies/standard-hackathon-rules.md）。[权威背景] https://guide.mlh.com/general-information/judging-and-submissions/rules-for-your-hackathon

- 团队 1–4 人，可 solo；不建议跨赛事重复投稿；
- **不得在赛事开始前动工**，提交截止即停止开发，不得复用旧项目代码；
- 代码须以公开链接提交（GitHub / repl.it / Google Drive 等），**提交前移除 API key**；
- 可使用公开框架，但须在 README 中列明；
- **可使用 LLM/ChatGPT/AI 工具，但必须在提交中声明用法、说明"哪些是自己做的、哪些是 AI 生成的"，不得只是套皮（reskin）现有 AI 工具；未声明 AI 用量可被取消资格并上报 cheating@mlh.io**；
- 评审默认线下进行，推荐"science fair"展位式；
- 学生赛事限定学生参赛，志愿者/组织者/导师不可获奖（可为作品集做项目）。

此外 MLH 有独立的《Disciplinary Action Policy》与 Code of Conduct 强制要求。[权威背景] https://static.mlh.io/docs/disciplinary-action-policy.pdf

### 2.3 第三个平台

本次未再展开第三家独立平台（Devpost 本身已聚合绝大多数公开企业悬赏赛，MLH 覆盖学生/线下体系）。[未能查证：未对第三家平台做官方页面级核实，故不点名，避免编造]

---

## 3. Web3 vs 通用编程黑客松对比

> 说明：Web3 侧本次未做独立官方页面抓取（本子任务聚焦通用生态），下表中 Web3 列仅作行业通识性对照，凡无本次官方出处的均标注 [未能查证]，请按需另行核实。

| 维度 | 通用编程黑客松（Devpost/MLH） | Web3 黑客松 |
|---|---|---|
| 面向人群 | 全球开发者，平台门槛低（13+ 可注册），学生友好；企业赛面向会用其 SDK 的工程师。[官方原文] | 区块链/钱包/智能合约开发者，需加密货币与钱包使用经验。[未能查证] |
| 奖金来源 | **企业营销/产品预算**：Meta、Google 等赞助商出资，官方要求标注应税现金价值。[官方原文] https://info.devpost.com/legal/terms-of-service | 协议生态基金会/风投/项目金库出资，常见以原生代币计价发放（如搜索结果中 Oasis Bloom 赛事奖池标注为"$50,000 in ROSE"，代币计价、非现金）。[未能查证：该赛事页本次未打开核对] |
| 评审侧重 | 创新创意、体验设计、技术实现、完成度/包装，且强绑定赞助商 track 与工具采用（Meta 赛四维度即为实例）。[官方原文] https://start-developer-competition-26.devpost.com/ | 链上可运行性、钱包/协议集成、代币经济与增长叙事。[未能查证] |
| 求职价值 | 间接但有官方背书路径：公开 portfolio + 官方博客案例（认识招聘人员 → 实习 → 全职）；平台另有雇主/求职者两套条款。[官方介绍] https://info.devpost.com/blog/user-story-brij | 多为项目孵化/团队融资导向，获奖者常获投资与生态 grant，求职连接弱于直接招聘。[未能查证] |
| 变现方式 | 现金奖金（需报税）+ 作品集沉淀 + 潜在面试机会。[官方原文] | 代币奖金（价格波动大）+ grant + 项目被生态收购/融资。[未能查证] |
| 对资深技术负责人（你）的现实意义 | 可把 Web3 钱包项目抽象成"全栈/AI 工程能力"样本去投企业赛，作品档案即简历附件；但企业赛多要求用赞助商工具，存在"为参赛改项目"的成本。 | 与正在做的钱包项目同赛道，获奖即直接为项目背书/融资，但奖金为代币、规则与合规风险更高。[判断性结论，非官方数据] |

---

## 4. 来源清单与核对入口

| # | 事实 | 来源 URL | 证据等级 |
|---|---|---|---|
| 1 | Devpost 提交五步流程、文件/视频/图片规格 | https://help.devpost.com/article/126-know-your-submission-steps | [官方原文] |
| 2 | 服务条款：资格（13+）、团队代表、公开投票规则、主办方奖金义务、雇主/求职者条款 | https://info.devpost.com/legal/terms-of-service | [官方原文] |
| 3 | 评审设置（criteria 1–5 分 / 公开投票） | https://help.devpost.team/article/230-how-to-set-up-judging ; https://help.devpost.com/article/131-setting-up-judging | [官方原文] |
| 4 | Meta VR Start Developer Competition 2026 官方赛事页（$1M、截止 2026-11-18 EST、提交物与评审维度） | https://start-developer-competition-26.devpost.com/ | [官方原文] |
| 5 | Google 客户案例（2019 起托管、奖金兑付） | https://info.devpost.com/customer-stories/google-hackathons-on-devpost | [官方介绍] |
| 6 | 客户名单（Amazon/Google/Microsoft/Meta/Snap/Ford 等） | https://info.devpost.com/careers?page=3 | [官方介绍] |
| 7 | 平台定位、6M+ 开发者口径、学生免费办赛 | https://info.devpost.com/product/public-hackathons | [官方介绍] |
| 8 | portfolio 公开作品档案 | https://help.devpost.com/article/115-what-is-a-devpost-portfolio-and-how-do-i-use-it | [官方原文] |
| 9 | 参赛者求职案例（Brij → Thomson Reuters） | https://info.devpost.com/blog/user-story-brij | [官方介绍] |
| 10 | MLH 定位（5M+/1000+ events/100 countries、Fellowship） | https://www.mlh.com/ | [官方介绍] |
| 11 | MLH 标准赛事规则（团队/AI 声明/赛前不动工/代码公开） | https://guide.mlh.com/general-information/judging-and-submissions/rules-for-your-hackathon | [权威背景] |
| 12 | MLH 纪律政策 | https://static.mlh.io/docs/disciplinary-action-policy.pdf | [权威背景] |
| 13 | Devpost 赛事总览入口（自行浏览） | https://devpost.com/hackathons | [官方原文] |

---

## 自检清单

**已逐条打开官方页面核对的事实：**
- Devpost 提交五步流程与各步规格（help 中心原文）
- 平台条款中的年龄门槛、团队代表、公开投票一票一提交规则、主办方"必须兑现宣传奖金并标注应税现金价值"义务、雇主/求职者条款存在
- 评审两种模式与 1–5 分制
- Meta VR Start 2026 赛事：$1M 现金池、截止 2026-11-18 EST、4267 参赛者、tracks/division/提交物/四维修维标准（官方赛事页原文）
- Google 自 2019 起由 Devpost 托管并含 prize fulfillment（官方客户案例）
- MLH 官网定位数据（5M+/1000+/100 国）与 Fellowship 形态
- MLH 标准规则全部要点（含 AI 声明、赛前不动工、代码公开链接）

**未能查证 / 待官方核对：**
- Devpost 统一的奖金打款/税务 FAQ（平台无统一通道，逐赛 Official Rules 规定）
- Devpost 社群规模两处口径（6M+ vs 4M+）不一致，以最新页为准
- Web3 侧所有对比项（本次未做 Web3 官方页抓取），尤其 Oasis 赛事"in ROSE"代币计价仅来自搜索摘要，未打开原页
- 第三家通用赛事平台（未做官方级核实，故不点名）
