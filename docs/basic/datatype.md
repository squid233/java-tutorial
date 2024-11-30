# 数据类型

Java 是静态类型语言，同时也是强类型语言，意味着 Java 中[变量](variable.md)和表达式的类型在运行时不可变，且其值与对其的操作受到类型限制。

Java 有两种数据类型，分别为原始类型和引用类型。第一章主要介绍原始类型。

**原始类型**（Primitive type，又称基本类型）包括数值类型和布尔类型。下面我们来看8种原始类型的名称和其值的范围。

## 整数

5种整数的类型名称和值的范围如下表所示，其中`[a, b]`表示`a <= 类型取值 <= b`：

| 名称      | 范围                                          | 二进制位数 |
|---------|---------------------------------------------|-------|
| `byte`  | [-128, 127]                                 | 8     |
| `short` | [-32768, 32767]                             | 16    |
| `int`   | [-2147483648, 2147483647]                   | 32    |
| `long`  | [-9223372036854775808, 9223372036854775807] | 64    |
| `char`  | ['\u0000', '\uffff'] 或 [0, 65535]           | 16    |

`byte`、`short`、`int`、`long`的值用整数[字面量](exp/literal.md)表示，在二进制形式中有符号的2的补码。

`char`的值用字符字面量表示，为16位无符号整数，用于表示 UTF-16 代码单元。

/// admonition
    type: tip
通过查询互联网，了解二进制的详细信息。
///

## 浮点数

Java 中的浮点数遵守 IEEE 754 标准，`float`为32位浮点数、`double`为64位浮点数。

## 布尔类型

布尔类型的值称为布尔值，即`boolean`。`boolean`的值只有`true`和`false`，表示真或假。

## 初始值

数值类型的初始值为0，布尔类型的初始值为`false`，引用类型的初始值为`null`。