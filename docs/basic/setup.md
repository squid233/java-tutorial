# 配置环境

在开始前，我们先理清以下概念：

- Java：Java 编程语言。
    - Java 源文件：使用 Java 编写的文件。文件后缀名是`.java`。
- JVM：Java 虚拟机（Java Virtual Machine），可运行字节码文件。
    - 字节码：[JVM Specification](https://docs.oracle.com/javase/specs/jvms/se22/html/index.html)
      规定的一系列指令，用单个或多个字节（Byte）表示。
- JDK：Java 开发包（Java Development Kit），包含 Java 的编译器和运行时。
    - 编译器：把 Java 源文件转换为字节码文件。字节码文件的后缀名是`.class`。
- JRE：Java 运行时环境（Java Runtime Environment），现已不可单独下载，可用`jlink`程序自行制作。

Java 与 JVM 无直接关系。JVM 能运行任何规范的字节码文件。

本书重点讲解 **Java 编程语言**，其他不作赘述。

## 下载 JDK

JDK 根据供应商不同分为 Oracle JDK 和 OpenJDK，由 Oracle 发布的称为 Oracle JDK；
其他供应商则基于 OpenJDK 开发了自己的版本。

OpenJDK 的供应商可在 [SDKMAN!](https://sdkman.io/jdks) 找到。

## 环境变量

一般下载到的都是压缩包，解压后还需要配置环境变量。

根据自己的操作系统配置。

!!! tip "以 Windows 10 为例"
    1. 右击开始按钮，点击设置→系统→关于→高级系统设置→环境变量。
    2. 这时，请无视**用户变量**中的任何内容。
    3. 点击**系统变量**下的**新建**按钮。
    4. 在**变量名**内填入`JAVA_HOME`，点击浏览**目录**，选择你刚刚下载的 JDK 的目录（**不包括**`bin`！）。
    5. 找到变量 **`Path`**，点击**编辑**按钮。
    6. 在弹出的窗口中，点击**新建**按钮，输入`%JAVA_HOME%\bin\`。
    7. 确定。

## 测试

启动终端，运行`javac --version`。输出类似`javac 22`的内容时，说明配置成功了。
如果提示找不到文件，请检查环境变量是否正确配置。

!!! tip "Windows 10 的终端"
    1. 右击开始菜单。
    2. 点击命令提示符。
