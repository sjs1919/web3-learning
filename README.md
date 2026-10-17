# Web3 Learning

> 面向 Web3 / 区块链开发求职与远程工作的系统学习仓库。
> 目标：用最短路径掌握 Web3 核心技术栈，通过面试拿到远程 Offer。

## 项目定位

本仓库是一个**结构化自学 + 求职准备**项目，聚焦三条主线：

1. **学习主线（learning/）**：Web3 转行学习路线图，按 5 个阶段（读链上交易 → 接入链 → 数据接入 → 提现对账 → 项目收尾）系统掌握开发能力。
2. **面试主线（interview/）**：Web3 面试八股文，覆盖区块链基础、密码学、共识机制、以太坊、Solidity、DeFi、Layer2、合约安全等，用于面试冲刺与知识体系搭建。
3. **远程工作主线（remotework/）**：真实的远程工作机会认知、求职渠道、避坑指南、学习路径手册，来自 Web3 从业者的一手经验整理。

## 目录结构

```
web3-learning/
├── README.md                  # 本文件：项目说明与学习路线
├── learning/             # 学习路线图
│   └── Web3转行学习清单.md      # 5 阶段转行学习路线图（含每周安排/Checklist/资料）
├── interview/            # 面试准备
│   └── Web3面试八股文.md       # 系统面试八股文（11章 + 60 题速答）
└── remotework/                # 远程工作文档（含完整媒体：图片/PDF/画板已下载）
    ├── 关于远程工作你想知道的都在这/      # 阿兵：远程工作全景手册
    │   ├── 正文.md
    │   └── media/                # 133 张图 + 1 PDF + 1 画板（视频因无导出权限未下载）
    ├── C2E手册/
    │   └── 正文.md                 # C2E 手册总目录
    └── C2E手册-子文档/            # 8 个子文档，各自 正文.md + media/
        ├── 01-AI赛道分析与岗位选择/
        ├── 02-为什么Web3是程序员的破局出路/
        ├── 03-Web3真实薪资结果展示/
        ├── 04-Web3开发岗位选择/
        ├── 05-Web3远程工作机会&接单渠道/     # 含 4 张求职渠道表格
        ├── 06-Web3转型落地路径（自学）/
        ├── 07-转型避坑指南/
        └── 08-C2E Labs社区资源支持体系/
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
- 按 `learning/Web3转行学习清单.md` 逐阶段推进（5 阶段主线）
- 精读 `interview/Web3面试八股文.md`，逐条过关
- 复盘 2-3 个实战项目，准备项目讲述
- 英文听力/口语突击（Web3 远程岗位普遍要求英文）

**阶段四：求职落地（持续）**
- 按 `remotework/` 中的渠道投递：Wellfound、Web3.career、Dejob、Smartdeer 等
- 关注社区内推机会（Web3 以内推 + 社区群为主）

## 参考资料来源

- `remotework/` 下文档来自飞书 wiki 公开分享的从业者手册（阿兵 / C2E Labs）。每份文档 = `正文.md` + `media/`（图片、PDF、画板已完整下载到本地，正文内用相对路径引用）。
- **视频限制**：正文中的视频因当前账号对该分享文档**无导出权限**（`media-download` 返回 permission_denied），无法下载原始视频文件；正文已标注视频名称与原文档，请到原飞书文档查看。
- 05 文档嵌入的 4 张求职/接单渠道表格（海外全职、国内全职、全球外包、国内私活）已读取为 Markdown 表格，可离线查阅。
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
