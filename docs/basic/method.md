---
comments: true
---

# 方法

## 情境导入

我们每天都要进行`eat`、`drink`、`work`、`sleep`4个动作。如果每次都写出这些动作的名称就比较麻烦，因此我们把这些动作统一成`live`。

上述5个动作我们称之为方法。**方法**（Method）负责执行一串语句，用于减少重复工作。

## 创建方法

创建方法需要使用声明语句

```java
方法类型 方法名(参数类型 参数名, ...) {
    一些语句...
    return 返回值;
}
```

其中，圆括号里为方法的参数列表。方法可以不含参数、不含返回值。

`#!java return`语句负责调用方法后返回一个值。方法类型为`#!java void`时方法没有返回值，此时可省略`#!java return`语句。

例如以下代码创建`cube`方法：

```java
double cube(double a) {
    return a * a * a;
}
```

## 调用

调用方法的语句为`方法名(参数, ...);`。

特别地，调用有返回值的方法可视为表达式。

输入`#!java double v = cube(3);`，得到结果`27.0`。

## 输出内容

无返回值的方法内运算的结果不会自动输出。调用`IO.println(消息)`能输出消息并换行，`IO.print(消息)`则不换行。

在 Java 23 中需要启用预览功能。

```
jshell> /env --enable-preview

jshell> IO.println("Hello world");
Hello world
```

## 本地变量

方法的大括号里的语句为方法体。在方法体内声明的变量为本地变量（Local variable）。本地变量的类型为`#!java var`时，Java 会自动推断类型。

```java
int f() {
    var k = 1;
    return k * 2;
}
```

注意`k`固定为`#!java int`类型，它的类型不会改变，也不能强行赋值一个`#!java boolean`或其他类型。

## 字符串的比较

我们知道数和布尔值都能用`==`比较，那么字符串是否能这样比较呢？

在 JShell 输入以下代码：

```java
String s = "hello "
"hello world" == s + "world"
```

结果为`false`。这说明字符串不能用`==`比较。为了比较字符串，我们需要使用`equals`方法。

```java
"hello world".equals(s + "world") == true
```

我们将在第二章了解`==`对引用类型的作用。

## 可变参数

若在方法的**最后一个**参数的类型名后添加三个点号（`...`），则该参数为可变参数（Variable arity parameter）。

可变参数本质是一个数组，但允许以普通参数的方式传入，不需要显式创建数组。没有参数传入时，可变参数为空数组。

```java
int f(int... args);
int g() { return f(1, 2, 3); }
```

---

JShell 的使用到此为止。之后的章节中我们将在源文件中编写代码。
