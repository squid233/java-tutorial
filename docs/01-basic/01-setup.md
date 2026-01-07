# 配置开发环境

在开始编写代码之前，我们需要理解 Java 的核心概念并安装必要的工具。

## 核心概念辨析

在学习 Java 时，你会经常听到几个缩写。理清它们的关系是迈向专业开发的第一步。

| 概念       | 全称                            | 说明                                                    |
|----------|-------------------------------|-------------------------------------------------------|
| **Java** | **Java Programming Language** | **本书的重点**。一种面向对象的编程语言，由我们编写源代码（`.java` 文件）。           |
| **JVM**  | **Java Virtual Machine**      | **Java 虚拟机**。负责运行字节码（`.class` 文件），实现“一次编写，到处运行”。      |
| **JDK**  | **Java Development Kit**      | **Java 开发工具包**。包含编译器（`javac`）、调试器和 JVM。**开发者必须安装此项**。 |
| **JRE**  | **Java Runtime Environment**  | **Java 运行时环境**。仅包含运行 Java 程序所需的组件。                    |

/// admonition | 关于 JRE 的特别说明
    type: note
从 Java 11 开始，Oracle 不再提供独立的 JRE 下载包。现在的 JDK 已经包含了完整的运行时环境。如果你要开发或运行 Java 25 程序，直接安装 JDK 25 即可。
///


## 下载并安装 JDK

由于 Java 25 是（编写时的）最新版本，建议从官方渠道或受信的开源发行版下载。

1. **访问下载页面**：前往 [Oracle 官网](https://www.oracle.com/java/technologies/downloads/) 或 [Adoptium (OpenJDK)](https://adoptium.net/)。
2. **选择版本**：选择 **Java 25** 以及对应的操作系统（Windows, macOS 或 Linux）。
3. **下载安装包或压缩包**。若在 Windows 上选择了压缩包，则需要手动配置环境变量。
4. **执行安装**：运行安装程序，按照提示点击“下一步”。建议记录安装路径（例如 `C:\Program Files\Java\jdk-25`）。

## 配置环境变量 (Windows)

为了在命令行（终端）中随处运行 Java 命令，需要将 JDK 的路径添加到系统的环境变量中。

1. **打开环境变量设置**：右键点击“此电脑” -> 属性 -> 高级系统设置 -> 环境变量。
2. **新建 JAVA_HOME**：
    * 在“系统变量”下新建。
    * 变量名：`JAVA_HOME`
    * 变量值：你的 JDK 安装路径（如 `C:\Program Files\Java\jdk-25`）。
3. **编辑 Path 变量**：
    * 在系统变量中找到 `Path`，点击编辑。
    * 点击“新建”，输入 `%JAVA_HOME%\bin`。
    * （可选）置顶该条目以确保优先调用。

## 验证安装

配置完成后，打开你的终端（Windows 下为 `CMD` 或 `PowerShell`，macOS/Linux 下为 `Terminal`），输入以下命令：

```bash
java -version
```

**预期输出：**
如果你看到类似下方的文字，说明环境配置成功：

```text
java version "25" 2025-09-16
Java(TM) SE Runtime Environment (build 25+33-LTS)
Java HotSpot(TM) 64-Bit Server VM (build 25+33-LTS, mixed mode)
```

## 本书重点

虽然我们安装了整个 JDK 工具箱，但本教程的**核心目标是教会你 Java 编程语言**的语法、逻辑和设计模式。JVM 和 JDK 的底层原理将在后续章节作为辅助知识点提及。

## 本节小结

本节我们了解了 Java 等概念，安装了 JDK 并配置了环境变量，为 Java 开发打下基础。
