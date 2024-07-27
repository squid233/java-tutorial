# 源文件

先在`src`文件夹下创建一个空文件（`New -> File`），取名为`HelloWorld.java`。不要创建`Java Class`，我们暂时用不到它。

## 主方法

所有 Java 程序都有主方法。主方法即名称为`main`且无返回值的方法。

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

这时调用主方法没有任何意义，因为它创建的`s`变量不会自动输出。要在终端显示我们想要的内容，就需要使用`System.out.println`方法。

`println`允许输出参数并自动换行；类似地，`print`允许输出参数且不换行。

```java
void main() {
    String s = "Hello world";
    System.out.println(s);
}
```

## 运行

点击主方法左边的绿色三角形，选择`Run`。这时 IDE 会帮我们编译并运行程序。

运行程序，得到结果`Hello world`。

右上角会多出一个配置，我们点击三角形就能运行。

## 程序参数

为了给我们的程序传入参数，我们需要给主方法添加`String[]`参数。我们能按照普通数组的操作方式读取参数。

```java
void main(String[] args) {
    System.out.println("Hello " + args[0]);
}
```

这时，我们需要点击右上角的`HelloWorld`，选择`Edit Configurations...`，并在`Program arguments`中填入我们需要的参数。有空格需要用半角双引号包围。完成后运行即可。

## 全局变量

在方法外创建的变量，源文件中的所有方法都能访问。

```java
String s = "Hello ";

void greet() {
    s += "world";
}

void main() {
    greet();
    System.out.println(s);
}
```

## 注释

Java 支持行注释和块注释。用`//`或`/**/`添加注释。块注释不支持嵌套。

```java
void main() {
    // 行注释
    /* 块注释 */
    System.out.println("Hello world");
}
```
