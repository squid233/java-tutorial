# 快速实验工具：JShell

在正式进入繁琐的项目结构和 IDE 之前，JShell 是让新手快速获得成就感的最佳工具。

在传统的 Java 开发中，即使只想测试一行代码，也需要创建类、编写 `main` 方法、编译再运行。为了简化这一过程，Java 引入了 **JShell**。

## 什么是 JShell？

JShell 是一个 **REPL** (Read-Eval-Print Loop，读取-求值-打印-循环) 工具。它允许你直接输入 Java 代码并立即看到运行结果，而无需编写完整的类结构。

**它的主要用途包括：**

* 快速验证简单的语法或算法。
* 测试 Java 标准库的新函数（如 Java 25 的新特性）。
* 作为初学者学习变量和表达式的“草稿本”。

## 如何使用 JShell

由于你已经在上一节配置好了环境变量，现在可以直接在终端（CMD 或 Terminal）中启动它。

### 启动与退出

1. **启动**：在终端输入 `jshell` 并回车。
2. **退出**：输入 `/exit` 并回车。

### 基本操作示例

一旦进入 JShell 提示符（`jshell>`），你就可以像写数学题一样写 Java 代码：

```java
jshell> 1 + 1
$1 ==> 2

jshell> String message = "Hello Java 25"
message ==> "Hello Java 25"

jshell> IO.println(message.toUpperCase())
HELLO JAVA 25

```

/// admonition | 小技巧
    type: tip
在 JShell 中，分号 `;` 通常是可以省略的。
///


## 从 JShell 到 IDE

虽然 JShell 非常适合零碎的代码测试，但在实际开发中，我们要编写成千上万行代码，涉及多个文件、复杂的依赖关系和调试需求。这时，我们就需要 **IDE (Integrated Development Environment，集成开发环境)**。

IDE 就像是给程序员准备的“全能工作台”，它集成了以下功能：

* **代码编辑器**：支持高亮、自动补全和语法检查。
* **构建工具**：一键编译和运行复杂的项目。
* **调试器 (Debugger)**：逐行检查代码运行状态，寻找错误。

### 推荐的 IDE

对于 Java 25 的开发，我们推荐以下主流工具：

1. **IntelliJ IDEA**（首选）：目前 Java 业界最智能、市场占有率最高的 IDE。
2. **Visual Studio Code (VS Code)**：轻量化，配合 Java 扩展包使用体验极佳。
3. **Eclipse**：老牌开源 IDE，在特定企业级开发中仍在使用。

## 本节小结

JShell 是我们探索 Java 语法的“实验室”，而 IDE 则是我们构建大型应用的“建筑工地”。
