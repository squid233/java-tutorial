# 流程控制：条件判断

默认情况下，程序是按照代码顺序从上到下执行的。但现实中的逻辑往往需要分情况讨论。在 Java 中，我们主要使用 `if` 结构和 `switch` 结构来实现分支。

## if 语句

`if` 语句根据布尔表达式（`true` 或 `false`）的结果来决定是否执行某段代码。

### 基础结构

```java
void main() {
    int score = 85;

    if (score >= 60) {
        IO.println("及格了！");
    } else {
        IO.println("还要努力哦。");
    }
}
```

### 多重分支 (if-else if)

当有多个条件需要判断时，可以使用 `else if`：

```java
void main() {
    int temperature = 28;

    if (temperature > 30) {
        IO.println("天气炎热，注意防暑。");
    } else if (temperature >= 20) {
        IO.println("天气凉爽，适合出游。");
    } else {
        IO.println("天气较冷，多穿衣服。");
    }
}
```

## switch 结构

当一个变量有多个固定取值时，使用 `switch` 会比一连串的 `if-else` 更加清晰。

### 现代写法：Switch 表达式 (Java 25)

在现代 Java 中，推荐使用 `->` 语法，它更简洁且不需要手动编写 `break` 来防止“穿透”。

```java
void main() {
    int day = 3;
    
    String dayName = switch (day) {
        case 1 -> "周一";
        case 2 -> "周二";
        case 3 -> "周三";
        case 4, 5 -> "工作日快结束了";
        default -> "周末或无效输入";
    };

    IO.println("今天是：" + dayName);
}
```

## 三元运算符 (Ternary Operator)

对于非常简单的“二选一”逻辑，可以使用三元运算符来简化代码：
**语法：** `条件 ? 结果A : 结果B`

```java
void main() {
    int age = 20;
    String status = (age >= 18) ? "成年人" : "未成年人";
    IO.println(status);
}
```

---

## 变量的作用域 (Scope)

注意：在 `{}` 大括号内部声明的变量，在括号外部是无法访问的。这被称为变量的**作用域**。

```java
void main() {
    if (true) {
        int tempValue = 100;
        IO.println(tempValue); // 正确
    }
    // IO.println(tempValue); // 错误！找不到该变量
}
```

## 动手练习：简易打分器

编写一个程序，根据用户的分数（定义一个变量 `int score`），输出对应的等级：

* 90-100: 优秀
* 80-89: 良好
* 60-79: 及格
* 0-59: 不及格

```java
void main() {
    int score = 88;
    
    if (score >= 90) {
        IO.println("等级：优秀");
    } else if (score >= 80) {
        IO.println("等级：良好");
    } else if (score >= 60) {
        IO.println("等级：及格");
    } else {
        IO.println("等级：不及格");
    }
}
```

## 本节小结

本节我们学习了`if`、`if-else`、`switch`语句以及三元运算符，了解了变量的作用域。我们还运用`if-else`语句编写了一个简易打分器。

**条件判断让程序有了“脑子”。** 那么如果我们需要让程序重复执行某项任务（比如打印 100 遍“你好”），该怎么办呢？

**下一节我们将学习流程控制：循环。**
