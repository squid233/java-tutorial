---
comments: true
---

# 强制转换

`(T) 表达式`可将表达式的类型强制转换（Cast）为类型`T`。注意：若转换后类型不兼容，运行时会抛出`ClassCastException`异常。

```
jshell> (int) 3.14
$1 ==> 3

jshell> (int) true
|  错误:
|  不兼容的类型: boolean无法转换为int
|  (int) true
|        ^--^
```
