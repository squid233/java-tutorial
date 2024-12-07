---
comments: true
---

# 数组

## 情境导入

假设你的公司有5位员工，记录他们的年龄（`int`类型）。

我们能创建5个`int`：

```java
int age0 = 22;
int age1 = 25;
int age2 = 23;
int age3 = 30;
int age4 = 28;
```

那如果有100位、1000位呢？显然，我们不想（也不能）创建多个`int`。这时，就需要用到数组了。

**数组**（Array）包含零个或多个变量。数组中的变量称为组件（Component）。

## 创建数组

创建数组和创建变量使用的语句相同，区别在于数组的类型为`组件类型[]`。

$$
\begin{align}
C[] \space a &= {\rm new} \space C[l];\\
C[] \space a &= {\rm new} \space C[]\{v_0,\space v_1, \space..., \space v_{l-1}\};\\
C[] \space a &= \{v_0, \space v_1, \space..., \space v_{l-1}\};
\end{align}
$$

上述语句中，$C$为组件类型，$l$为数组的长度，$v_n$为第$n$个组件的初始值。

在$(2)(3)$式中，数组$a$的长度会由 Java 自动确定。数组一经创建，其长度就不可改变。

## 访问组件

数组中每一个组件都是变量，因此获得数组的组件后可以按变量的方式赋值等。

获取数组的组件需要用访问语句

$$
C \space c = a[i];
$$

其中$i$称为索引（Index），${\rm int} \space i \in [0,l)$。索引从`0`开始，即第1个组件索引为0，第2个组件索引为1，以此类推。

## 边界

数组的长度通过`.length`获取，其类型为`int`，如`c.length`。

如果索引小于0或大于等于数组的长度，则会抛出`ArrayIndexOutOfBoundsException`异常。
