# 版本控制与发布

BMad Method 使用简化的发布系统，具有手动控制和自动生成发布说明的功能。

## 🚀 发布工作流程

### 命令行发布（推荐）

创建发布并生成美观发布说明的最快方式：

```bash
# 预览发布内容
npm run preview:release

# 创建发布
npm run release:patch    # 5.1.0 → 5.1.1（修复错误）
npm run release:minor    # 5.1.0 → 5.2.0（新功能）
npm run release:major    # 5.1.0 → 6.0.0（破坏性变更）

# 监控发布过程
npm run release:watch
```

### 单行命令发布

```bash
npm run preview:release && npm run release:minor && npm run release:watch
```

## 📝 自动执行的操作

当您触发发布时，GitHub Actions 工作流会自动：

1. ✅ **验证** - 运行测试、代码检查和格式检查
2. ✅ **更新版本号** - 更新 `package.json` 和安装程序版本
3. ✅ **生成发布说明** - 分类自上次发布以来的提交：
   - ✨ **新功能** (`feat:`, `Feature:`)
   - 🐛 **错误修复** (`fix:`, `Fix:`)
   - 🔧 **维护** (`chore:`, `Chore:`)
   - 📦 **其他变更**（所有其他内容）
4. ✅ **创建 Git 标签** - 标记发布版本
5. ✅ **发布到 NPM** - 使用 `@latest` 标签供用户安装
6. ✅ **创建 GitHub 发布** - 包含格式化的发布说明

## 📋 示例发布说明

工作流会自动生成如下专业的发布说明：

````markdown
## 🚀 v5.2.0 中有什么新内容

### ✨ 新功能

- feat: 添加团队协作模式
- feat: 用交互式提示增强 CLI

### 🐛 错误修复

- fix: 解决安装路径问题
- fix: 处理代理加载的边缘情况

### 🔧 维护

- chore: 更新依赖项
- chore: 改进错误消息

## 📦 安装

```bash
npx bmad-method install
```
````

**完整变更日志**：https://github.com/bmadcode/BMAD-METHOD/compare/v5.1.0...v5.2.0

````

## 🎯 用户安装

任何发布后，用户都可以立即使用以下命令获取新版本：

```bash
npx bmad-method install    # 始终获取最新发布
```

## 📊 发布前预览

始终预览将包含在发布中的内容：

```bash
npm run preview:release
```

这显示：

- 自上次发布以来的提交
- 分类的变更
- 估计的下一个版本
- 发布说明预览

## 🔧 手动发布（GitHub UI）

您也可以通过 GitHub Actions 触发发布：

1. 转到 **GitHub Actions** → **Manual Release**
2. 点击 **"Run workflow"**
3. 选择版本更新类型（patch/minor/major）
4. 其他所有内容都会自动发生

## 📈 版本策略

- **Patch**（5.1.0 → 5.1.1）：错误修复，小改进
- **Minor**（5.1.0 → 5.2.0）：新功能，增强功能
- **Major**（5.1.0 → 6.0.0）：破坏性变更，重大重新设计

## 🛠️ 开发工作流程

1. **自由开发** - 将 PR 合并到 main 分支而不触发发布
2. **测试未发布的更改** - 克隆仓库以测试最新的 main 分支
3. **准备就绪后发布** - 使用命令行或 GitHub Actions 发布
4. **用户获取更新** - 通过简单的 `npx bmad-method install` 命令

这使您可以完全控制发布的时间，同时自动执行所有繁琐的部分，如版本更新、发布说明和发布。

## 🔍 故障排除

### 检查发布状态

```bash
gh run list --workflow="Manual Release"
npm view bmad-method dist-tags
git tag -l | sort -V | tail -5
```

### 查看最新发布

```bash
gh release view --web
npm view bmad-method versions --json
```

### 如果需要同步版本

如果发布后您的本地文件与已发布的版本不匹配：

```bash
./tools/sync-version.sh    # 自动将本地文件与 npm 最新版本同步
```

### 如果发布失败

- 检查 GitHub Actions 日志：`gh run view <run-id> --log-failed`
- 验证 NPM 令牌是否已配置
- 确保分支保护允许工作流推送
