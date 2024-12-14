# 源文件

先在`src`文件夹下创建一个空文件（`New -> File`），取名为`HelloWorld.java`。不要创建`Java Class`，我们暂时用不到它。

## 主方法

所有的 Java 程序都有主方法。主方法即名称为`main`、类型为`#!java void`的方法。

```java
void main() {
}
```

## 输出内容

在主方法中添加代码如下：

```java
void main() {
    String s = "Hello world";
}
```

这时调用主方法没有任何意义，因为它创建的`s`变量不会自动输出。要在终端显示我们想要的内容，就需要使用我们先前学过的`IO.println`或`IO.print`方法。不在类中定义的方法里`IO.`前缀可以省略。

```java
void main() {
    String s = "Hello world";
    println(s);
}
```

## 运行

点击主方法左边的绿色三角形，选择`Run`。这时 IDE 会帮我们编译并运行程序。

运行程序，得到结果`Hello world`。

右上角会多出一个配置，我们点击三角形就能运行。

## 输入内容

除了输出以外，我们也可以通过`readln(提示词)`从控制台获取输入的内容，其类型为`String`。

[//]: # (TODO JDK 24 IO::readln without argument)

```java
void main() {
    var name = readln("What's your name? My name is: ");
    println("Your name is: " + name);
}
```

## 程序参数

为了给我们的程序传入参数，我们需要给主方法添加`String[]`参数。我们能按照普通数组的操作方式读取参数。

```java
void main(String[] args) {
    println("Hello " + args[0]);
}
```

这时，我们需要点击右上角的`HelloWorld`，选择`Edit Configurations...`，并在`Program arguments`中填入我们需要的参数。有空格的参数需要用半角双引号包围。完成后运行即可。

## 全局变量

在方法外创建的变量，源文件中的（不在类里定义的）所有方法都能访问。这些变量不在方法体内，因此不能声明类型为`#!java var`。

```java
String s = "Hello ";

void greet() {
    s += "world";
}

void main() {
    greet();
    println(s);
}
```

## 注释

Java 支持行注释和块注释。用`// 内容`或`/* 内容 */`添加注释。块注释不支持嵌套。

```java
void main() {
    // 行注释
    /* 块注释
     * 换行 */
    println("Hello world");
}
```
