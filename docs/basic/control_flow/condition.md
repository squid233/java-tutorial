# 条件语句

在生活中，我们经常需要根据不同条件做不同的事。例如，假设我们周一、三、五在家吃饭，周二、四、六在外面吃饭，周日点外卖。上述动作，用“如果……否则……”的形式写出，就是：

1. 如果今天是周一、三、五，那么在家吃饭；
2. 否则，如果今天是周二、四、六，那么在外面吃饭；
3. 否则点外卖。（一周只有七天）

## `if`语句

上面的场景中，我们用“如果……否则……”的句子来表示条件。同样地，在 Java 中，`#!java if`语句也能表示条件。

```java
if (条件) {
    分支
}
```

上述代码在`条件`满足时执行分支。

当分支只有一条语句时，大括号可以省略。

```java
if (条件) 语句;
```

## `else`语句

如果要在`条件`不满足时执行其他分支，则需要在`#!java if`分支后接上`#!java else`语句。

```java
if (条件) {
    分支1
} else {
    分支2
}
```

`#!java else`后面加上`#!java if`时可以指定额外的条件。

```java
if (条件1) {
    分支1
} else if (条件2) {
    分支2
}
```

一个`#!java if`分支后面可加上多个`#!java else if`分支和一个`#!java else`分支。`#!java else`分支后不能添加其他`#!java else (if)`分支。

## 三元运算符

有时我们需要按条件返回值，这时可用三元运算符

```java
C ? A : B
```

相当于以下代码

```java
T v;
if (C) v = A;
else v = B;
```

其中`C`为条件。

/// admonition | 注意
    type: note
三元运算符嵌套过多时会增加阅读难度。
///

## 练习

用本节所学内容表示出本节开头所提到的场景。形式可自由发挥。

/// details | 参考答案
    type: example
```java
if (today == Monday || today == Wednesday || today == Friday) {
    eatAtHome();
} else if (today == Tuesday || today == Thursday || today == Saturday) {
    eatOut();
} else {
    eatTakeaway();
}
```
///
