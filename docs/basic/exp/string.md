# 字符串

## 字符

在 Java 中，**字符**（`char`）是一种特殊的整数，取值范围为0~65535。

字符能表示 Unicode 第零平面（BMP）中的所有字符，即U+0000~U+FFFF。

字符用半角单引号（`'`）包围，如`'A'`、`'字'`。单引号中只允许存在**一个**字符，超出 BMP 范围则需要用码点表示。

## 码点

码点（Codepoint）是`int`类型。码点能额外表示 Unicode BMP 以外的字符，如 Emoji 等。

## 字符串

**字符串**（String）由多个字符或码点组成。

字符串用半角双引号（`"`）包围，如`"Hello world"`、`"你好"`。

### 转义

对于一些特殊字符，Java 支持用**反斜杠**（`\`）转义（Escape）。

常见的转义字符包括：

- `\"`：双引号
- `\'`：单引号
- `\\`：反斜杠
- `\n`：换行符
- `\r`：回车符
- `\t`：制表符（Tab）
- `\uxxxx`：Unicode 字符，其中`xxxx`为0~9或A~F，不区分大小写

### 拼接

Java 为字符串添加了特殊处理，允许使用加号（+）拼接字符串。

使用加号还能为字符串拼接其他类型，如整数等。

输入`"Hello Java " + 22 + " world"`，得到结果`"Hello Java 22 world"`。

### 文本块

Java 支持多行文本。只需要在开头与末尾各添加三个双引号（`"""`）即可。

文本块前的双引号必须换行，文本块后的则不需要。文本块会根据缩进自动删除各行开头的空格。各行末尾的空格自动删除。

在各行末尾添加反斜杠取消换行。

输入以下代码：

```
"""
Hello
multiline \
string"""
```

得到结果`"Hello\nmultiline string"`。

### 模板

字符串模板曾在 Java 21 和 22 中预览，但在 23 中移除了。本书不讲解。

/// admonition | 你知道吗
    type: tip
Java 22 中的字符串模板长这样：`STR."Hello Java \{22} world"`
///
