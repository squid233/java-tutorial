# 变量

## 标识符

标识符（Identifier）简单来说就是一串用来标记的字符序列。

标识符的规则为：

- 开头为字母、`_`或`$`
- 中间和末尾为字母、数字、`_`或`$`
- 不允许为保留关键字
    - 不允许全为下划线

标识符区分大小写，支持汉字。

## 关键字

**关键字**（Keyword）是 Java 保留的具有特殊意义的字符序列。其中，保留关键字（Reserved keyword）不可作为标识符，上下文关键字（Contextual
keyword）则在特定场合下具有特殊意义。

[JLS 22](https://docs.oracle.com/javase/specs/jls/se22/html/jls-3.html#jls-3.9) 规定了 51 个保留关键字和 17
个上下文关键字，分别如下：

| 保留关键字     |          |            |              |              |   
|-----------|----------|------------|--------------|--------------|
| abstract  | continue | for        | new          | switch       |
| assert    | default  | if         | package      | synchronized |
| boolean   | do       | ~~goto~~   | private      | this         |
| break     | double   | implements | protected    | throw        |
| byte      | else     | import     | public       | throws       |
| case      | enum     | instanceof | return       | transient    |
| catch     | extends  | int        | short        | try          |
| char      | final    | interface  | static       | void         |
| class     | finally  | long       | ~~strictfp~~ | volatile     |
| ~~const~~ | float    | native     | super        | while        |
| _ （下划线）   |          |            |              |              |

| 上下文关键字     |          |            |      |       |
|------------|----------|------------|------|-------|
| exports    | opens    | requires   | uses | yield |
| module     | permits  | sealed     | var  |       |
| non-sealed | provides | to         | when |       |
| open       | record   | transitive | with |       |

划删除线的是无实际意义或废弃的关键字。

## 变量概述

**变量**（Variable）就是用标识符标记了一个表达式，且能改为标记其他表达式。

### 声明

通过`类型 标识符`声明（Declare）新变量。标识符不得与使用过的重复。

声明变量后，变量的类型**不会且不能**改变。

#### 初始化

使用未初始化的变量会出错。通过`类型 标识符 = 表达式`声明并初始化（Initialize）新变量。

输入`int i = 42`，此时 JShell 就保存了变量`i`。

### 赋值

通过`标识符 = 表达式`修改**已有**变量，这种操作叫做赋值（Assign）。

输入`i = 43`，此时`i`的值为`43`。

对于支持`+`、`-`、`*`、`/`、`&`、`|`的类型，Java 还允许在`=`前加上这些操作符进行计算并赋值。

输入`i += 2`，此时`i`的值为`45`。

### 使用

变量可作为表达式使用。

尝试：输入以下代码，计算结果：

```
String s = "Hello Java "
int i = 22
s + i
```

### 常量

声明变量时在类型前添加`final`可声明常量（Constant）。不允许对常量赋值。

输入`final String s = "Hello"`。此时如果执行`s = "world"`，JShell 仍会修改常量的值，这是因为 JShell 不检查变量是否不可修改。

## JShell 中的临时变量

你是否注意到每次输入表达式后，返回的结果左边有类似于`$n ==>`这样的提示？
