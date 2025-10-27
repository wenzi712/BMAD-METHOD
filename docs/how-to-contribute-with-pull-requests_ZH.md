# 如何通过拉取请求进行贡献

**对GitHub和拉取请求不熟悉？** 本指南将逐步引导您了解基础知识。

## 什么是拉取请求？

拉取请求（PR）是您在GitHub上向项目提出更改的方式。可以将其视为说"这是我想做的一些更改，请审核并考虑将它们添加到主项目中"。

## 开始之前

⚠️ **重要提示**：请保持您的贡献小巧且集中！我们更喜欢许多小而明确的更改，而不是一个大规模的更改。

**提交PR前的要求**：

- **对于错误修复**：使用[错误报告模板](https://github.com/bmadcode/bmad-method/issues/new?template=bug_report.md)创建一个问题
- **对于新功能**：
  1. 在Discord [#general-dev频道](https://discord.gg/gk8jAdXWmj)中讨论
  2. 使用[功能请求模板](https://github.com/bmadcode/bmad-method/issues/new?template=feature_request.md)创建一个问题
- **对于大型更改**：始终先打开一个问题进行讨论对齐

## 分步指南

### 1. 复刻仓库

1. 访问[BMad-Method仓库](https://github.com/bmadcode/bmad-method)
2. 点击右上角的"Fork"按钮
3. 这将创建项目的您自己的副本

### 2. 克隆您的复刻

```bash
# 将YOUR-USERNAME替换为您的实际GitHub用户名
git clone https://github.com/YOUR-USERNAME/bmad-method.git
cd bmad-method
```

### 3. 创建一个新分支

**永远不要直接在`main`分支上工作！** 始终为您的更改创建一个新分支：

```bash
# 创建并切换到新分支
git checkout -b fix/typo-in-readme
# 或者
git checkout -b feature/add-new-agent
```

**分支命名提示**：

- `fix/description` - 用于错误修复
- `feature/description` - 用于新功能
- `docs/description` - 用于文档更改

### 4. 进行更改

- 编辑您想要更改的文件
- 保持更改小巧且集中于一件事
- 尽可能测试您的更改

### 5. 提交您的更改

```bash
# 添加您的更改
git add .

# 使用清晰的消息提交
git commit -m "Fix typo in README.md"
```

**好的提交消息**：

- "Fix typo in installation instructions"
- "Add example for new agent usage"
- "Update broken link in docs"

**不好的提交消息**：

- "stuff"
- "changes"
- "update"

### 6. 推送到您的复刻

```bash
# 将您的分支推送到您的复刻
git push origin fix/typo-in-readme
```

### 7. 创建拉取请求

1. 前往GitHub上的您的复刻
2. 您将看到一个绿色的"Compare & pull request"按钮 - 点击它
3. 选择正确的目标分支：
   - 大多数贡献（功能、文档、增强）选择**`next`分支**
   - 仅关键修复选择**`main`分支**
4. 使用CONTRIBUTING.md中的模板填写PR描述：
   - **What**: 1-2句话描述更改内容
   - **Why**: 1-2句话解释原因
   - **How**: 2-3个关于实现的要点
   - **Testing**: 您如何测试
5. 引用相关问题编号（例如，"Fixes #123"）

### 8. 等待审核

- 维护者将审核您的PR
- 他们可能会要求更改
- 耐心等待并对反馈做出回应

## 什么是好的拉取请求？

✅ **好的PR**：

- 一次只更改一件事
- 有清晰、描述性的标题
- 在描述中解释什么和为什么
- 仅包含需要更改的文件

❌ **避免**：

- 更改整个文件的格式
- 在一个PR中包含多个不相关的更改
- 将您的整个项目/仓库复制到PR中
- 没有解释的更改

## 常见错误

1. **不要重新格式化整个文件** - 只更改必要的内容
2. **不要包含不相关的更改** - 每个PR坚持一个修复/功能
3. **不要在问题中粘贴代码** - 而是创建一个适当的PR
4. **不要提交您的整个项目** - 贡献特定的改进

## 需要帮助？

- 💬 加入我们的[Discord社区](https://discord.gg/gk8jAdXWmj)获取实时帮助：
  - **#general-dev** - 技术问题和功能讨论
  - **#bugs-issues** - 在提交问题前获取错误帮助
- 💬 在[GitHub讨论](https://github.com/bmadcode/bmad-method/discussions)中提问
- 🐛 使用[错误报告模板](https://github.com/bmadcode/bmad-method/issues/new?template=bug_report.md)报告错误
- 💡 使用[功能请求模板](https://github.com/bmadcode/bmad-method/issues/new?template=feature_request.md)建议功能
- 📖 阅读完整的[贡献指南](../CONTRIBUTING.md)

## 示例：好的PR vs 差的PR

### 😀 好的PR示例

**标题**："修复指向安装指南的损坏链接"
**更改**：一个文件，更改了一行
**描述**："README.md中的链接指向错误的文件。更新为指向正确的安装指南。"

### 😞 差的PR示例

**标题**："更新"
**更改**：50个文件，整个代码库重新格式化
**描述**："做了一些改进"

---

**记住**：我们随时为您提供帮助！不要害怕提问。每个专家都曾经是初学者。