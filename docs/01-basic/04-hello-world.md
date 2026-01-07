# 你好，世界！

现在环境已经配置完成，是时候编写并运行你的第一个 Java 程序了。我们将对比“传统写法”与 Java 25 推荐的“现代写法”。

## 编写代码

在 IntelliJ IDEA 项目的 `src` 目录下，右键点击 **新建 (New) -> Java 压缩文件 (Java Compact File)**。

### 方式 A：现代写法 (推荐)

Java 25 进一步优化了初学者的入门体验。你不再需要编写复杂的类定义，也不需要 `static` 关键字。

创建一个名为 `HelloWorld.java` 的文件，输入以下内容：

```java
void main() {
    IO.println("Hello, World!");
}

```

/// admonition | 关于 java.lang.IO
在 Java 25 中，`IO` 类位于 **`java.lang`** 包下。由于 `java.lang` 是 Java 默认自动导入的包，你可以直接使用 `IO.println` 而无需任何 `import` 声明。这是目前 Java 最简单、最直观的输出方式。
///

### 方式 B：传统写法

在大型项目或旧版本代码中，你仍会看到这种严谨的结构：

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

## 运行程序

在 IntelliJ IDEA 中运行程序：

1. **点击绿箭头**：在代码 `void main()` 左侧的行号处，点击绿色的“播放”图标。
2. **查看控制台**：窗口下方会弹出 **运行 (Run)** 面板，你将看到输出结果：
```text
Hello, World!
```

## 代码拆解

即便代码只有几行，也包含了编程的核心逻辑：

* **`void main()`**：程序的**入口点**。JVM 启动时会寻找这个方法开始执行。
* **`IO.println(...)`**：调用 `java.lang.IO` 类中的 `println` 方法，将信息打印到控制台。
* **`"..."`**：双引号包裹的内容被称为**字符串 (String)**。
* **`;`（分号）**：代表一条指令的结束。

## 动手练习

尝试利用我们在上一节学到的 **`iop` 补全**，编写以下代码：

```java
void main() {
    IO.println("你好，Java 25！");
    IO.println("我正在学习 java.lang.IO 的用法。");
}
```

## 本节小结

我们编写并运行了第一个 Java 程序，巩固了 `IO.println` 的用法。
