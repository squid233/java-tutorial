# 逻辑运算

逻辑运算是指对若干个表达式进行判断从而得到一个布尔值的运算。

## 不等式

两个表达式可用`==`（相等）或`!=`（不相等）比较。

两个数还可用`<`（小于）、`<=`（小于或等于）、`>`（大于）、`>=`（大于或等于）比较。

特别地，`NaN`不等于任何数（包括它自己），即`NaN != NaN`。

/// admonition | 注意
    type: note
在 Java 中，比较两个表达式是否相等用的是两个等号！
///

## 取反

在布尔值前加`!`操作符可对其逻辑取反。`!`属于**一元操作符**（Unary operator），其只要求一个表达式 。

由一元操作符和表达式组成的式子叫做一元表达式（Unary operator expression）。

对真表达式取反得到`false`，对假表达式取反得到`true`。

## 条件与、或

使用`&&`、`||`等二元操作符可对两个布尔值进行条件与（and）、或（or）操作。

`&&`：两个布尔值为真时结果为真。  
`||`：一个布尔值为真时结果为真。

特别地，条件与中，若左边的表达式为假，则右边的表达式不会被执行。

## 逻辑与、或、异或

使用`&`、`|`、`^`等二元操作符可对两个布尔值进行逻辑与、或、异或（exclusive or/xor）操作。

`&`：两个布尔值为真时结果为真。  
`^`：两个布尔值不同时结果为真。  
`|`：两个布尔值为假时结果为假。

逻辑与、或会执行两个表达式，如果不必须执行则应该用条件与、或。

```
jshell> true | (0 / 0) == 0
|  异常错误 java.lang.ArithmeticException：/ by zero
|        at (#1:1)
```
