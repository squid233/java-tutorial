# 布尔值

**布尔值**（`boolean`）的取值为`false`和`true`，区分大小写。

## 数的比较

通过比较两个整数或浮点数的大小，可以得到布尔值。

类似于不等式，符号有：

- `>`、`<`、`>=`、`<=`：大于、小于、大于或等于、小于或等于
- `==`：等于（注意有两个等号）
- `!=`：不等于

## 布尔值的比较

布尔值的比较有：等于（`==`）、不等于（`!=`）、逻辑与（`&&`）、逻辑或（`||`）、按位与（`&`）、按位或（`|`）、非（`!`）、异或（`^`）。[整数](integer.md)一节已讲过运算结果，这里不再重复。

### 短路运算

我们发现与、或有逻辑、按位之分。输入以下代码，得到结果：

```
false && (0/0 > 0) == false
true  || (0/0 > 0) == true
```

上面的代码中出现除零却不出错，这是因为逻辑运算具有短路运算的特点。

短路运算是指在逻辑与、或运算过程中，如果先计算的表达式能确定整条表达式的结果，则后续不再计算。

如果把上述代码改为使用按位运算，则会出错：

```
jshell> false & (0/0 > 0) == false
|  Exception java.lang.ArithmeticException: / by zero
```
