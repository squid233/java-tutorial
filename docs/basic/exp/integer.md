# 整数

## 整数的取值范围

Java 中的**整数**（Integer）和数学意义上的整数类似，不同的是 Java 中的整数有特定的取值范围。

下表是 Java 中各种整数的取值范围：

| 类型    | 范围                                 |
|-------|------------------------------------|
| byte  | -2<sup>7</sup> ~ 2<sup>7</sup>-1   |
| short | -2<sup>15</sup> ~ 2<sup>15</sup>-1 |
| int   | -2<sup>31</sup> ~ 2<sup>31</sup>-1 |
| long  | -2<sup>63</sup> ~ 2<sup>63</sup>-1 |

一般情况下使用`int`即可。

## 整数的运算

### 四则运算

Java 支持四则运算，即加减乘除，其运算顺序为先乘除、后加减，且可用圆括号（`()`）改变运算顺序。

需要注意的是，Java 中乘法、除法分别用**星号**（`*`）和**斜杠**（`/`）表示。

在 JShell 中输入`2*3+8/4-(9-(1-2))`，得到结果`-2`。

### 取舍

如果两个整数除不尽怎么办？Java 会直接舍弃小数部分，只保留整数部分，且不进行四舍五入。

输入`3/2`，得到结果`1`。

### 溢出

两个整数相加、减或乘，如果超出取值范围，Java 会按二进制方式处理。
例如，假设一个`byte`为127，加2，则会发生以下情况：

```
127     = 0b 0111 1111
127 + 2 = 0b 0111 1111
        + 0b 0000 0010
-127    = 0b 1000 0001
```

!!! note
    本书不讲解二进制的四则运算。

简单来说，请看下图：

![int-circle](https://mermaid.ink/svg/pako:eNo9TjFuhDAQ_Ara2iDD2hhcXJV0lybpIjcWmAMJ45PPKLkg_h7H3GWL2R3tzGg26FxvQMIwu69u1D5k53e1ZHFoluenrExYJczxWA92vCgQsMZbPfUxZvvzKgijsUaBjGdvBr3OQYFa9ihdr70O5rWfgvMgBz3fDAG9BvdxXzqQwa_mKXqZ9MVr-68yyfR29E21CVz18umcfRojBbnBN8iyZgW2LeOMljU2vKwJ3EFihQVnoqZVhbXgjImdwE9KoAVvGKIQgrbYNAKRgHfrZXwU2H8BuM1WbQ)

在上图中，给定一个数为2，加1时向右移一位溢出，变为-3。其他类型的整数同理。
