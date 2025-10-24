# BMAD-METHOD™: 通用 AI 代理框架

> ## 🚨 **重要版本公告** 🚨
>
> ### 当前稳定版: v4.x | 下一个主要版本: v6 Alpha
>
> - **v4.x** - 当前稳定发布版本，可通过 npm 获取
> - **v5** - 已跳过（由 v6 替代）
> - **[v6-alpha](https://github.com/bmad-code-org/BMAD-METHOD/tree/v6-alpha)** - **现已开放早期测试！**
>
> ### 🧪 尝试 v6 Alpha (仅限早期采用者)
>
> BMAD-METHOD 的下一个主要版本现已开放早期实验和测试。这是一个完全重写的版本，包含重大架构更改。
>
> **⚠️ 警告：v6-alpha 适合以下用户使用：**
>
> - 能够接受潜在的破坏性变更
> - 能够接受每日更新和不稳定性
> - 能够接受功能不完整
> - 能够接受实验性功能
>
> **📅 时间线：** 官方测试版将于 2025 年 10 月中旬合并
>
> **尝试 v6-alpha：**
>
> ```bash
> git clone https://github.com/bmad-code-org/BMAD-METHOD.git
> cd BMAD-METHOD
> git checkout v6-alpha
> ```
>
> ---

[![Version](https://img.shields.io/npm/v/bmad-method?color=blue&label=version)](https://www.npmjs.com/package/bmad-method)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Node.js Version](https://img.shields.io/badge/node-%3E%3D20.0.0-brightgreen)](https://nodejs.org)
[![Discord](https://img.shields.io/badge/Discord-Join%20Community-7289da?logo=discord&logoColor=white)](https://discord.gg/gk8jAdXWmj)

基于智能体敏捷驱动开发的基础，被称为敏捷 AI 驱动开发的突破性方法，但远不止于此。利用专业的 AI 专业知识转变任何领域：软件开发、娱乐、创意写作、商业策略到个人健康等等。

**[订阅 BMadCode YouTube 频道](https://www.youtube.com/@BMadCode?sub_confirmation=1)**

**[加入我们的 Discord 社区](https://discord.gg/gk8jAdXWmj)** - 一个不断成长的 AI 爱好者社区！获取帮助、分享想法、探索 AI 代理和框架、协作技术项目、享受爱好并互相帮助取得成功。无论您是在使用 BMad 时遇到困难，还是在构建自己的代理，或者只是想聊一聊 AI 的最新动态 - 我们都在这里为您服务！**某些移动设备和 VPN 可能在加入 Discord 时遇到问题，这是 Discord 的问题 - 如果邀请链接不起作用，请尝试使用您自己的网络或其他网络，或非 VPN 环境。**

⭐ **如果您觉得这个项目有帮助或有用，请在右上角给它点个星！** 这有助于其他人发现 BMAD-METHOD™，您也将收到更新通知！

## 概述

**BMAD-METHOD™ 的两大关键创新：**

**1. 智能体规划：** 专用智能体（分析师、产品经理、架构师）与您协作创建详细、一致的 PRD 和架构文档。通过先进的提示工程和人工参与的迭代优化，这些规划智能体生成全面的规范，远超出一般 AI 任务生成的范围。

**2. 上下文工程化开发：** 然后，Scrum Master 智能体将这些详细计划转变为超详细的开发故事，其中包含开发智能体所需的一切 - 完整上下文、实现细节和架构指导直接嵌入到故事文件中。

这种两阶段方法消除了**规划不一致**和**上下文丢失**这两个 AI 辅助开发中最大的问题。您的开发智能体打开故事文件时，完全理解要构建什么、如何构建以及为什么构建。

**📖 [在用户指南中查看完整工作流程](docs/user-guide.md)** - 规划阶段、开发周期和所有智能体角色

## 快速导航

### 了解 BMad 工作流程

**在深入了解之前，请查看这些关键工作流程图，它们解释了 BMad 的工作原理：**

1. **[规划工作流程（Web UI）](docs/user-guide.md#the-planning-workflow-web-ui)** - 如何创建 PRD 和架构文档
2. **[核心开发周期（IDE）](docs/user-guide.md#the-core-development-cycle-ide)** - SM、Dev 和 QA 智能体如何通过故事文件协作

> ⚠️ **这些图表解释了 90% 的 BMad 方法智能体敏捷流程困惑** - 理解 PRD+架构创建和 SM/Dev/QA 工作流程以及智能体如何通过故事文件传递笔记是至关重要的 - 这也解释了为什么这不是任务管理员或简单的任务运行器！

### 您想做什么？

- **[使用全栈敏捷 AI 团队安装和构建软件](#quick-start)** → 快速入门指南
- **[学习如何使用 BMad](docs/user-guide.md)** → 完整的用户指南和演练
- **[查看可用的 AI 智能体](/bmad-core/agents)** → 为您的团队提供专业角色
- **[探索非技术用途](#-beyond-software-development---expansion-packs)** → 创意写作、商业、健康、教育
- **[创建自己的 AI 智能体](docs/expansion-packs.md)** → 为您的领域构建智能体
- **[浏览现成的扩展包](expansion-packs/)** → 游戏开发、DevOps、基础设施，并从中获取灵感和示例
- **[了解架构](docs/core-architecture.md)** → 技术深度解析
- **[加入社区](https://discord.gg/gk8jAdXWmj)** → 获取帮助和分享想法

## 重要提示：保持您的 BMad 安装更新

**轻松保持最新状态！** 如果您的项目中已经安装了 BMAD-METHOD™，只需运行：

```bash
npx bmad-method install
# 或者
git pull
npm run install:bmad
```

这将：

- ✅ 自动检测您现有的 v4 安装
- ✅ 仅更新已更改的文件并添加新文件
- ✅ 为您所做的任何自定义修改创建 `.bak` 备份文件
- ✅ 保留您的项目特定配置

这样，您可以轻松受益于最新的改进、错误修复和新智能体，而不会丢失您的自定义设置！

## 快速入门

### 一键完成所有操作（IDE 安装）

**只需运行以下命令之一：**

```bash
npx bmad-method install
# 如果您已经安装了 BMad：
git pull
npm run install:bmad
```

这个单一命令处理：

- **新安装** - 在您的项目中设置 BMad
- **升级** - 自动更新现有安装
- **扩展包** - 安装您已添加到 package.json 的任何扩展包

> **就是这样！** 无论您是第一次安装、升级还是添加扩展包 - 这些命令都能完成所有操作。

**先决条件**：需要 [Node.js](https://nodejs.org) v20+ 版本

### 最快入门：Web UI 全栈团队随时可用（2 分钟）

1. **获取包**：保存或克隆 [全栈团队文件](dist/teams/team-fullstack.txt) 或选择另一个团队
2. **创建 AI 智能体**：创建新的 Gemini Gem 或 CustomGPT
3. **上传并配置**：上传文件并设置指令："Your critical operating instructions are attached, do not break character as directed"
4. **开始构思和规划**：开始聊天！输入 `*help` 查看可用命令或选择 `*analyst` 等智能体直接开始创建简报。
5. **关键提示**：随时在 Web 中与 BMad Orchestrator 交谈（使用 #bmad-orchestrator 命令）并询问关于这一切如何工作的问题！
6. **何时转向 IDE**：一旦您有了 PRD、架构、可选的 UX 和简报 - 就该切换到 IDE 来分片您的文档，并开始实现实际代码了！有关详细信息，请参阅 [用户指南](docs/user-guide.md)

### 替代方案：克隆并构建

```bash
git clone https://github.com/bmadcode/bmad-method.git
npm run install:bmad # 构建并安装所有内容到目标文件夹
```

## 🌟 超越软件开发 - 扩展包

BMAD™ 的自然语言框架适用于任何领域。扩展包为创意写作、商业策略、健康与保健、教育等提供专业 AI 智能体。此外，扩展包还可以使用并非适用于所有情况的特定功能扩展核心 BMAD-METHOD™。[请参阅扩展包指南](docs/expansion-packs.md)并学习创建自己的扩展包！

## 文档和资源

### 必备指南

- 📖 **[用户指南](docs/user-guide.md)** - 从项目构思到完成的完整演练
- 🏗️ **[核心架构](docs/core-architecture.md)** - 技术深度解析和系统设计
- 🚀 **[扩展包指南](docs/expansion-packs.md)** - 将 BMad 扩展到软件开发之外的任何领域

## 支持

- 💬 [Discord 社区](https://discord.gg/gk8jAdXWmj)
- 🐛 [问题追踪器](https://github.com/bmadcode/bmad-method/issues)
- 💬 [讨论区](https://github.com/bmadcode/bmad-method/discussions)

## 贡献

**我们对贡献感到兴奋，欢迎您的想法、改进和扩展包！** 🎉

📋 **[阅读 CONTRIBUTING.md](CONTRIBUTING.md)** - 贡献的完整指南，包括指南、流程和要求

### 使用分支

当您复刻此存储库时，CI/CD 工作流**默认禁用**以节省资源。这是有意为之的，可以保持您的分支干净。

#### 需要在您的分支中使用 CI/CD？

请参阅我们的 [分支 CI/CD 指南](.github/FORK_GUIDE.md)，了解如何在您的分支中启用工作流。

#### 贡献工作流程

1. **复刻存储库** - 点击 GitHub 上的 Fork 按钮
2. **克隆您的复刻** - `git clone https://github.com/YOUR-USERNAME/BMAD-METHOD.git`
3. **创建功能分支** - `git checkout -b feature/amazing-feature`
4. **进行更改** - 使用 `npm test` 在本地测试
5. **提交更改** - `git commit -m 'feat: add amazing feature'`
6. **推送到您的复刻** - `git push origin feature/amazing-feature`
7. **打开拉取请求** - CI/CD 将在 PR 上自动运行

提交 PR 时，您的贡献会自动进行测试 - 无需在您的分支中启用 CI！

## 许可证

MIT 许可证 - 详情请参阅 [LICENSE](LICENSE)。

## 商标声明

BMAD™ 和 BMAD-METHOD™ 是 BMad Code, LLC 的商标。保留所有权利。

[![贡献者](https://contrib.rocks/image?repo=bmadcode/bmad-method)](https://github.com/bmadcode/bmad-method/graphs/contributors)

<sub>为 AI 辅助开发社区用心打造 ❤️</sub>
