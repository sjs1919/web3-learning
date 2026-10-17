# Web3 Learning

> 面向 Web3 / 区块链开发求职与远程工作的系统学习仓库。
> 目标：用最短路径掌握 Web3 核心技术栈，通过面试拿到远程 Offer。

## 项目定位

本仓库是一个**结构化自学 + 求职准备**项目，聚焦三条主线：

1. **学习主线（learning-path/）**：Web3 转行学习路线图，按 5 个阶段（读链上交易 → 接入链 → 数据接入 → 提现对账 → 项目收尾）系统掌握开发能力。
2. **面试主线（interview-prep/）**：Web3 面试八股文，覆盖区块链基础、密码学、共识机制、以太坊、Solidity、DeFi、Layer2、合约安全等，用于面试冲刺与知识体系搭建。
3. **远程工作主线（remotework/）**：真实的远程工作机会认知、求职渠道、避坑指南、学习路径手册，来自 Web3 从业者的一手经验整理。

## 目录结构

```
web3-learning/
├── README.md                  # 本文件：项目说明与学习路线
├── learning-path/             # 学习路线图
│   └── Web3转行学习清单.md      # 5 阶段转行学习路线图（含每周安排/Checklist/资料）
├── interview-prep/            # 面试准备
│   └── Web3面试八股文.md       # 系统面试八股文（11章 + 60 题速答）
└── remotework/                # 远程工作文档（机会、渠道、避坑、路径）
    ├── 关于远程工作你想知道的都在这.md        # 阿兵：远程工作全景手册
    ├── C2E Labs AI&Web3转型远程工作手册.md     # 手册总目录
    └── C2E手册-子文档/                        # C2E 手册引用的 8 个子文档
        ├── 01-AI赛道分析与岗位选择.md
        ├── 02-为什么Web3是程序员的破局出路.md
        ├── 03-Web3真实薪资结果展示.md
        ├── 04-Web3开发岗位选择.md
        ├── 05-Web3远程工作机会&接单渠道.md
        ├── 06-Web3转型落地路径（自学）.md
        ├── 07-转型避坑指南.md
        └── 08-C2E Labs社区资源支持体系.md
```

## 学习路线建议

**阶段一：认知建立（1 周）**
- 通读 `remotework/` 手册，明确 Web3 岗位分层、薪资水平、风险与避坑点
- 确定技术方向：底层（公链/跨链）or 应用层（DeFi/GameFi/NFT）

**阶段二：核心技术（4-6 周）**
- 掌握区块链原理：密码学、共识机制、去中心化账本
- 深入以太坊：账户模型、Gas、EVM、交易生命周期
- 学习 Solidity 与智能合约开发，用 Hardhat/Foundry 写合约
- 掌握 DeFi 核心协议与安全常识

**阶段三：面试冲刺（2 周）**
- 按 `learning-path/Web3转行学习清单.md` 逐阶段推进（5 阶段主线）
- 精读 `interview-prep/Web3面试八股文.md`，逐条过关
- 复盘 2-3 个实战项目，准备项目讲述
- 英文听力/口语突击（Web3 远程岗位普遍要求英文）

**阶段四：求职落地（持续）**
- 按 `remotework/` 中的渠道投递：Wellfound、Web3.career、Dejob、Smartdeer 等
- 关注社区内推机会（Web3 以内推 + 社区群为主）

## 参考资料来源

- `remotework/` 下文档来自飞书 wiki 公开分享的从业者手册（阿兵 / C2E Labs），已按原始内容转存为 Markdown 便于检索。
- 技术内容依据以太坊官方文档、OpenZeppelin、知名 Web3 技术社区整理。

## Git

- 远程仓库：`git@github.com:sjs1919/web3-learning.git`
- 首次提交：
  ```bash
  git init
  git add .
  git commit -m "init: web3 learning repo (learning-path + remotework)"
  git branch -M main
  git remote add origin git@github.com:sjs1919/web3-learning.git
  git push -u origin main
  ```

## License

仅供个人学习与求职准备使用。
