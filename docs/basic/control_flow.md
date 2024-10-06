# 流程控制

为了加强程序的功能，我们需要进行流程控制（Control flow）。

## 条件：`if`语句

`if`语句允许当指定的布尔值为`true`时执行块中的语句，如果不为`true`且有`else`块则跳到`else`。

```java
void main() {
    if (condition1) {
        statement1;
    } else if (condition2) {
        statement2;
    } else {
        statement3;
    }
}
```

上面的代码是顺序执行的，满足`condition1`则执行`statement1`，如果不满足，检查是否满足`condition2`，是则执行`statement2`，否则执行`statement3`。

`if`语句能嵌套，提供我们编写复杂程序的基础。

### 三元运算符

有时我们需要按条件返回表达式，这时可用三元运算符。三元运算符的格式是`condition ? expression1 : expression2`。

```java
void main(String[] args) {
    println(
        (args.length > 0 && "human".equals(args[0])) ?
        "You are human" :
        "You are not human"
    );
}
```

不建议嵌套三元运算符，若嵌套过多会导致程序极难阅读，此时应替换成`if`语句。

## 选择：`switch`表达式/语句

当我们需要在多个数中选择一个时，`if`链会变得极长。这时，`switch`表达式就非常合适。

`switch`表达式允许输入一个表达式，并根据给定的可能结果选择合适的分支执行。使用`case`关键字添加分支。当所有给定的分支都不符合时，跳到`default`分支。

`switch`属于表达式，因此能作为参数传入方法或赋值给变量。

`switch`作为表达式时必须有`default`分支，且所有分支都要返回值。

`case`分支省略大括号时，箭头（`->`）所指的内容即为返回的表达式。大括号包围时则需要用`yield`关键字返回。

`switch`内的表达式为`null`时默认会抛出异常（无视`default`分支），添加`case null`分支可进行特殊处理。

```java
void main(String[] args) {
    switch (args.length) {
        case 0 -> println("No argument");
        default -> {
            switch (args[0]) {
                case "human" -> {
                    println("You are human");
                    var bool = switch (args[1]) {
                        case "yes" -> true;
                        case null, default -> {
                            println("Fallback to false");
                            yield false;
                        }
                    };
                }
                case null -> println("You are unknown");
                default -> println("You are not human");
            }
        }
    }
}
```

/// admonition | 小技巧
    type: tip
使用`switch`表达式能在声明变量或传入参数时执行语句，具体操作如下：
```java
int i = switch (0) {
    default -> {
        println("created i");
        yield 42;
    }
};
```
///

## 循环

循环语句能重复执行相同的语句。

### `while`

`while`语句允许满足条件时执行语句，不满足时自动退出。

`do...while`与`while`类似，区别是`while`先判断后执行，`do...while`先执行后判断。

```java
void main() {
    while (condition) {
        statement;
    }
    
    do {
        statement;
    } while (condition);
}
```

### `for`

`for`语句允许创建一个局部变量，并在满足条件时执行语句与修改变量。局部变量的作用域为`for`语句内。

`for`语句的语法为：`for (变量; 条件; 修改)`。

```java
void main(String[] args) {
    for (int i = 0; i < args.length; i++) {
        println(args[i]);
    }
    // 等效于：
    int i = 0;
    while (i < args.length) {
        println(args[i]);
        i++;
    }
}
```

试一试：已知以下公式，请创建一个方法`long sum(long i, long n)`，要求返回的值与公式的值相同：`sum(i, n) = i + (i + 1) + ... + n`

/// details | 答案
    type: tip
```java
long sum(long i, long n) {
    long num = 0; 
    for (long j = i; j <= n; j++) {
        num += j;
    }
    return num;
}
```
///

### `for each`

对一个数组循环还能用`for each`循环。

`for each`循环的语法为：`for (类型 名称 : 数组)`。

```java
void main(String[] args) {
    for (var s : args) {
        println(s);
    }
}
```

### `continue`

在循环块内调用`continue`语句可跳过该次循环。

## `break`

在循环块内调用`break`语句可退出循环。

注意`continue`和`break`只能用于跳过或退出离上述两个语句最近的循环。若要跳过或退出外部循环则需要使用标签。

## 标签

标签（Label）可用于标记语句或块。

标签标记循环语句时与`continue`和`break`语句配合使用，标记其他语句或块时则与`break`配合使用。

标签标记块时，调用`break`语句能退出块。

```java
void main(String[] args) {
    int[] arr = new int[]{1, 2, 3, 4, 5};
    loop:
    for (var s : args) {
        for (var i : arr) {
            if ("exit".equals(s)) {
                break loop;
            }
            println(i);
        }
    }
}
```

/// admonition | 问题：以下代码能否编译？
    type: note
```text
void main(String[] args) {
    https://squid233.github.io/java-tutorial/basic/control_flow/
    if (args.length > 0 && "human".equals(args[0])) {
        println("You are human");
    }
}
```
///
