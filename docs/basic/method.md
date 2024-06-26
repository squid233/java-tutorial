# 方法

## 语句

前面我们讲到了变量的声明、赋值以及数组内容的修改，它们实际上是**语句**（Statement）。

语句必须以半角分号（`;`）结尾；在 JShell 中，单条语句可省略分号。

## 概述

为了减少重复工作，我们需要使用方法。**方法**（Method）负责执行一串语句。

### 声明

声明方法的语法如下：

```java
返回类型 方法名(参数类型 参数名, ...) {
    一些语句...
    return 返回值;
}
```

其中，返回类型为`void`时方法无返回值，可省略`return`语句。方法参数可为空。

输入以下代码，创建`cube`方法：

```java
double cube(double a) {
    return a * a * a;
}
```

### 调用

调用方法也属于语句。调用方法的语法为`方法名(参数, ...);`。

特别地，调用有返回值的方法可视为表达式。

输入`cube(3)`，得到结果`27.0`。

### 局部变量

在方法内声明变量，可用`var 标识符`的语法来让 Java 自动推断类型。

```java
int f() {
    var k = 1;
    return k * 2;
}
```

## 字符串的比较

我们知道数和布尔值都能用`==`比较，那么字符串是否能这样比较呢？

输入以下代码：

```
String s = "hello "
"hello world" == s + "world"
```

结果为`false`。这说明字符串不能用`==`比较。我们需要使用`equals`方法。

使用`equals`：`"hello world".equals(s + "world")`
