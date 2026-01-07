# 流程控制：循环

在编程中，我们经常需要重复执行某段代码。例如，打印 100 份文档、遍历一个列表或持续监听用户的输入。Java 提供了三种主要的循环结构：`for`、`while` 和 `do-while`。

## for 循环

`for` 循环最适合用于**已知循环次数**的场景。

### 基础语法

```java
for (初始化语句; 循环条件; 迭代语句) {
    // 循环体（重复执行的代码）
}
```

**示例：打印 1 到 5**

```java
void main() {
    for (int i = 1; i <= 5; i++) {
        IO.println("当前数字是: " + i);
    }
}
```

* **初始化 (`int i = 1`)**：只在循环开始前执行一次。
* **循环条件 (`i <= 5`)**：每次循环前都会检查，如果为 `true` 则继续，`false` 则退出。
* **迭代语句 (`i++`)**：每次循环体执行完毕后执行。

## while 循环

`while` 循环最适合用于**不确定循环次数**，只知道循环结束条件的场景。

### 基础语法

```java
while (循环条件) {
    // 循环体
}
```

**示例：猜数字逻辑模拟**

```java
void main() {
    int energy = 3;
    while (energy > 0) {
        IO.println("正在进行游戏... 剩余体力: " + energy);
        energy--; // 消耗体力
    }
    IO.println("体力耗尽，游戏结束。");
}
```

## do-while 循环

`do-while` 与 `while` 类似，但它保证循环体**至少会执行一次**，然后再进行条件判断。

```java
void main() {
    int count = 10;
    do {
        IO.println("即使条件不满足，我也运行了这一遍。");
    } while (count < 5);
}
```


## 循环控制：break 与 continue

有时候我们需要提前跳出循环，或者跳过某一次迭代：

* **`break`**：立即终止整个循环。
* **`continue`**：跳过本次循环剩余代码，直接开始下一次逻辑判断。

```java
void main() {
    for (int i = 1; i <= 10; i++) {
        if (i == 5) {
            continue; // 跳过数字 5
        }
        if (i == 8) {
            break;    // 到 8 时彻底停止循环
        }
        IO.println("数字: " + i);
    }
}
```

## 增强型 for 循环 (for-each)

虽然我们还没正式讲到数组，但这是 Java 中非常常用的循环方式，用于遍历集合中的每一个元素：

```java
void main() {
    String[] fruits = {"苹果", "香蕉", "橙子"};
    for (String fruit : fruits) {
        IO.println("水果篮里有: " + fruit);
    }
}
```

## 动手练习：计算累加和

编写一个程序，使用 `for` 循环计算从 1 加到 100 的总和。

```java
void main() {
    int sum = 0;
    for (int i = 1; i <= 100; i++) {
        sum += i; // 累加
    }
    IO.println("1 到 100 的累加和是: " + sum);
}
```

## 本节小结

我们学习了`for`、`while`、`do-while`和for-each循环以及`break`与`continue`语句，通过计算累加和的简单程序巩固了`for`循环的用法。
