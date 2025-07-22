# 浮点数

/// admonition | 本节前置知识
    type: tip
IEEE 754
///

浮点数有两种类型，分别为`#!java float`和`#!java double`。`#!java float`的精度比`#!java double`小。

浮点数的字面量和数学中的小数一样。`#!java float`的字面量需要在数字后加上`F`或`f`后缀。

浮点数遵守 IEEE 754 标准。

浮点数支持科学记数法，只要把&times;10替换成`E`或`e`即可（这也是你计算器里的表示），如下。

```java
1.0e10  2e+3    3e-4
```
