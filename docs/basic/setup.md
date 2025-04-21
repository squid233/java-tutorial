# 配置环境

在开始前，我们先理清以下概念：

- Java：Java 编程语言。由 [JLS（Java Language Specification）](https://docs.oracle.com/javase/specs/jls/se23/html/) 定义。
    - Java 源文件：使用 Java 编写的文件，后缀名是`.java`。
- JVM：Java 虚拟机（Java Virtual Machine），可运行字节码文件。
    - 字节码：[JVM Specification（Java Virtual Machine Specification）](https://docs.oracle.com/javase/specs/jvms/se23/html/)
      规定的一系列指令，用单个或多个字节（Byte）表示。
- JDK：Java 开发包（Java Development Kit），包含 Java 的编译器和运行时。
    - 编译器：把 Java 源文件转换为字节码文件，后缀名是`.class`。
- JRE：Java 运行时环境（Java Runtime Environment），现已不可单独下载，可用`jlink`程序自行制作。

Java 与 JVM 没有直接关系。JVM 能运行任何符合规范的字节码文件。

本书重点讲解 **Java 编程语言**，其他内容不过多说明。

## 下载 JDK

为了编译 Java 文件，我们需要下载 JDK。

世界上一些公司和组织根据 OpenJDK 开发出了自己版本的 JDK，我们把这些公司和组织称为供应商。

不同供应商发布的 JDK 可在 [SDKMAN!](https://sdkman.io/jdks) 找到，可以根据自己喜好下载，本书不作推荐。

## 环境变量

一般下载到的 JDK 都是压缩包，解压后还需要配置环境变量。

根据自己的操作系统配置，把`JAVA_HOME`设置为解压到的路径，该路径下应有`bin`、`lib`等文件夹。

/// details | 以 Windows 10 为例
    type: tip
1. 打开设置，搜索环境变量，选择编辑系统环境变量，点击环境变量按钮。
2. 这时，请无视**用户变量**中的任何内容。点击**系统变量**下的**新建**按钮。
3. 在**变量名**内填入`JAVA_HOME`，点击**浏览目录**，选择你刚刚下载的 JDK 的目录（**不包括**`bin`！）。
4. 找到变量 **`Path`**，点击**编辑**按钮。
5. 在弹出的窗口中，点击**新建**按钮，输入`%JAVA_HOME%\bin\`。
6. 确定。
///

## 测试

启动终端，运行`javac --version`。输出类似`javac 24`的内容时，说明配置成功了。如果提示找不到文件，请检查环境变量是否正确配置。

/// details | Windows 10 的终端
    type: tip
1. 打开开始菜单。
2. 搜索`终端`。
3. 打开 Windows Terminal、Windows PowerShell 或命令提示符。
///
