# 选择语句

我们注意到，上一节的练习中所有条件都用等号来比较，即在多个选项中选择一个满足的选项。像这样，具有选择关系的条件语句可以用选择语句来表示。

## `switch`语句

在 Java 中，`#!java switch`语句对一个指定的对象选择一个值相同的分支执行。不同的分支用`#!java case`来表示。

```java
switch (对象) {
    case 值1 -> 语句1; // 只有1条语句时可以省略大括号
    case 值2 -> {
        语句2;
        其他语句;
    }
    ...
}
```

用`#!java if`语句来表示相当于

```java
if (对象 == 值1) 语句1;
else if (对象 == 值2) {
    语句2;
    其他语句;
}
// 对字符串:
if (对象.equals(值1)) 语句1;
else if (对象.equals(值2)) {
    语句2;
    其他语句;
}
```

上述代码中，`对象`必须属于基本类型或`String`类型，`值n`必须为字面量。

## 多选一

`#!java case`分支可以包含多个值，表示有一个值满足时执行分支，每一个值之间用逗号分隔开。

```java
switch (对象) {
    case 值1, 值2 -> 语句;
    ...
}
```

## 默认分支

和`#!java if`语句一样，`#!java switch`语句也能在所有值都不相同时选择默认分支。

```java
switch (...) {
    default -> ...
}
```

## `switch`表达式

`#!java switch`除了能作语句之外，还能当成表达式使用。

```java
T v = switch (对象) {
    case 值1 -> 返回值1;
    case 值2 -> {
        语句;
        yield 返回值2;
    }
    ...
};
```

/// admonition | 小技巧
    type: tip
在初始化变量时执行语句：
```java
int k = switch (0) {
    default -> {
        println("创建变量k");
        yield 100;
    }
};
```
///

## 练习

用`#!java switch`语句表示出上一节练习的代码。

/// details | 参考答案
    type: example
```java
switch (today) {
    case Monday, Wednesday, Friday -> eatAtHome();
    case Tuesday, Thursday, Saturday -> eatOut();
    default -> eatTakeaway();
}
```
///
