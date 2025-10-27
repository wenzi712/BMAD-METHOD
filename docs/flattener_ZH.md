# 代码库扁平化工具

BMAD-METHOD™ 包含一个强大的代码库扁平化工具，专为在上传到网络AI工具时准备项目文件以供AI模型使用而设计。该工具将整个代码库聚合到单个XML文件中，使您可以轻松地与AI助手共享项目上下文，以便进行分析、调试或开发协助。

## 功能

- **AI优化输出**：生成专为AI模型消费设计的干净XML格式
- **智能过滤**：自动尊重`.gitignore`模式以排除不必要的文件，另外提供可选的项目级`.bmad-flattenignore`用于额外排除（如果计划扁平化现有存储库以进行外部更新和分析）
- **二进制文件检测**：智能识别并排除二进制文件，专注于源代码
- **进度跟踪**：实时进度指示器和全面的完成统计
- **灵活输出**：可自定义输出文件位置和命名

## 使用方法

```bash
# 基本用法 - 在当前目录创建flattened-codebase.xml
npx bmad-method flatten

# 指定自定义输入目录
npx bmad-method flatten --input /path/to/source/directory
npx bmad-method flatten -i /path/to/source/directory

# 指定自定义输出文件
npx bmad-method flatten --output my-project.xml
npx bmad-method flatten -o /path/to/output/codebase.xml

# 组合输入和输出选项
npx bmad-method flatten --input /path/to/source --output /path/to/output/codebase.xml
```

## 示例输出

该工具将显示进度并提供全面的摘要：

```text
📊 完成摘要：
✅ 成功将156个文件处理到flattened-codebase.xml中
📁 输出文件：/path/to/your/project/flattened-codebase.xml
📏 总源码大小：2.3 MB
📄 生成的XML大小：2.1 MB
📝 总行数：15,847
🔢 估计令牌数：542,891
📊 文件明细：142个文本文件，14个二进制文件，0个错误
```

生成的XML文件包含您项目的基于文本的源文件，采用AI模型可以轻松解析和理解的结构化格式，非常适合代码审查、架构讨论或获取AI对您的BMAD-METHOD™项目的协助。

## 高级用法和选项

- CLI选项
  - `-i, --input <path>`：要扁平化的目录。默认值：当前工作目录或在交互式运行时自动检测的项目根目录。
  - `-o, --output <path>`：输出文件路径。默认值：所选目录中的`flattened-codebase.xml`。
- 交互模式
  - 如果您不传递`--input`和`--output`，且终端是交互式的（TTY），工具将尝试检测您的项目根目录（通过查找`.git`、`package.json`等标记）并提示您确认或覆盖路径。
  - 在非交互上下文中（例如CI），它会静默地优先使用检测到的根目录；否则它会回退到当前目录和默认文件名。
- 文件发现和忽略
  - 在git存储库内使用`git ls-files`以提高速度和正确性；否则回退到基于glob的扫描。
  - 应用您的`.gitignore`加上一组精选的默认忽略模式（例如`node_modules`、构建输出、缓存、日志、IDE文件夹、锁文件、大型媒体/二进制文件、`.env*`和之前生成的XML输出）。
  - 支持在项目根目录使用可选的`.bmad-flattenignore`文件进行额外的忽略模式（gitignore风格）。如果存在，其规则将在`.gitignore`和默认规则之后应用。

## `.bmad-flattenignore`示例

在项目根目录创建一个`.bmad-flattenignore`文件，以排除必须保留在git中但不应包含在扁平化XML中的文件：

```text
seeds/**
scripts/private/**
**/*.snap
```

- 二进制文件处理
  - 二进制文件被检测并从XML内容中排除。它们会在最终摘要中计数，但不会嵌入到输出中。
- XML格式和安全性
  - UTF-8编码的文件，根元素为`<files>`。
  - 每个文本文件作为`<file path="relative/path">`元素发出，其内容包装在`<![CDATA[ ... ]]>`中。
  - 工具通过拆分CDATA来安全处理内容中的`]]>`出现，以保持正确性。
  - 文件内容按原样保留，并在XML中缩进以提高可读性。
- 性能
  - 并发根据您的CPU和工作负载大小自动选择。无需配置。
  - 在git存储库中运行可提高发现性能。

## 最小XML示例

```xml
<?xml version="1.0" encoding="UTF-8"?>
<files>
  <file path="src/index.js"><![CDATA[
    // 您的源代码内容
  ]]></file>
</files>
```