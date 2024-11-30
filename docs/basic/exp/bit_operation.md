# 位运算

位运算只适用于整数。本节所讲的位是指二进制位（Bit）。

## 取反

在整数前添加一元操作符`~`可对其按位取反。

```
jshell> ~0b1
$1 ==> -2
```

## 按位与、或、异或

使用`&`、`|`、`^`等二元操作符可对两个整数进行按位与、或、异或操作。计算式子`A 操作符 B`，对于整数的每一位，有以下结果：

| A | B | A & B | A \| B | A ^ B |
|---|---|:-----:|:------:|:-----:|
| 0 | 0 |   0   |   0    |   0   |
| 0 | 1 |   0   |   1    |   1   |
| 1 | 0 |   0   |   1    |   1   |
| 1 | 1 |   1   |   1    |   0   |

```
jshell> 0b101 | 0b010
$1 ==> 7
```

## 移位

使用`<<`、`>>`、`>>>`等二元操作符可对一个整数进行左移、有符号右移、无符号右移操作（left/signed right/unsigned right shift），格式为`n 操作符 s`，其会将`n`的二进制位整体移动`s`位。有符号右移会保留符号位。

```
jshell> 0b100 >> 2
$1 ==> 1
```

## 位标志

把上述操作符结合起来，不难实现利用1个`int`存储32个`boolean`。将一个整数的每一位都看作一个布尔值，则该整数可称作位标志（Flags）。

若把一个整数`n`的第一位命名为`doEat`，第二位为`doPlay`，第三位为`doSleep`，要获取每一位的值，可用与运算：

- 获取`doEat`：`(n & 0b001) != 0`
- 获取`doPlay`：`(n & 0b010) != 0`
- 获取`doSleep`：`(n & 0b100) != 0`

要创建整数`n`则可用或运算：

```java
0b001 | 0b010 // doEat && doPlay
```