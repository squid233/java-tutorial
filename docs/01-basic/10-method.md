# 方法

随着程序逻辑变得复杂，如果所有代码都堆在 `main` 方法中，会变得难以维护。**方法 (Method)** 允许我们将一段功能独立的代码块封装起来，并起一个名字。

## 方法的定义

在 Java 25 的简易程序模型（隐式类）中，定义方法非常简单。一个完整的方法通常包含：**返回类型**、**方法名**、**参数列表**和**方法体**。

### 基本语法

```java
返回类型 方法名(参数类型 参数名) {
    // 执行逻辑
    return 结果; // 如果返回类型不是 void，则必须 return
}
```

## 无返回值的方法 (void)

如果一个方法只是执行动作（如打印信息），不需要返回数据，返回类型使用 `void`。

```java
// 定义方法：打印一条装饰过的消息
void printWelcome(String name) {
    IO.println("**********");
    IO.println("欢迎你, " + name + "!");
    IO.println("**********");
}

void main() {
    printWelcome("Alice"); // 调用方法
    printWelcome("Bob");   // 再次复用
}
```

## 有返回值的方法

如果方法计算出一个结果并需要交给调用者，必须指定返回类型。

```java
// 定义方法：计算圆的面积
double calculateArea(double radius) {
    double area = 3.14159 * radius * radius;
    return area; // 将计算结果“吐”出来
}

void main() {
    double result = calculateArea(5.0); // 接收返回值
    IO.println("半径为 5 的圆面积是: " + result);
}
```

## 为什么要使用方法？

1. **消除重复**：同样的操作写一次，多处调用。
2. **提高可读性**：通过方法名（如 `saveData`, `sendEmail`）就能知道代码在干什么，而不需要看具体的实现细节。
3. **便于维护**：如果逻辑需要修改，只需改动方法内部的一处代码，所有调用它的地方都会自动更新。

## 方法的重载 (Overloading)

在同一个程序中，可以定义多个**同名**的方法，只要它们的**参数列表不同**（参数个数或类型不同）。

```java
int add(int a, int b) {
    return a + b;
}

double add(double a, double b) {
    return a + b;
}

void main() {
    IO.println(add(10, 20));      // 调用第一个 add
    IO.println(add(1.5, 2.5));    // 调用第二个 add
}
```

## 作用域提醒

在方法内部声明的变量是**局部变量**，它们只在该方法内有效。一旦方法执行完毕，这些变量就会被销毁。

## 动手练习：计算平均分

编写一个方法 `getAverage`，接收一个 `int` 数组作为参数，并返回这些分数的平均值（`double`）。

```java
double getAverage(int[] nums) {
    int sum = 0;
    for (int n : nums) {
        sum += n;
    }
    return (double) sum / nums.length;
}

void main() {
    int[] myScores = {80, 90, 85, 70};
    double avg = getAverage(myScores);
    IO.println("我的平均分是: " + avg);
}
```

## 变长参数 (Varargs)

有时候，你无法预先确定调用者会传入多少个参数。例如，你可能想写一个计算多个数字总和的方法，它可能接收 2 个数字，也可能接收 10 个。

在 Java 中，你可以使用 `...` 语法来定义变长参数。

### 基本语法

```java
返回类型 方法名(参数类型... 变量名) {
    // 在方法内部，变量名被当作“数组”来处理
}
```

### 示例：计算任意数量数字的和

```java
// 使用 ... 表示可以接收 0 个或多个 int 类型的参数
int sumAll(int... numbers) {
    int total = 0;
    // numbers 在这里就是一个 int[] 数组
    for (int n : numbers) {
        total += n;
    }
    return total;
}

void main() {
    // 你可以传入任意数量的参数
    IO.println(sumAll(1, 2, 3));             // 输出 6
    IO.println(sumAll(10, 20, 30, 40, 50));  // 输出 150
    IO.println(sumAll());                    // 输出 0（不传也可以）
}
```

### 使用规则与注意事项

1. **位置限制**：变长参数必须是方法参数列表中的**最后一个**。
    * `void test(int... nums, String s)` ❌ (编译错误)
    * `void test(String s, int... nums)` ✅
2. **唯一性**：一个方法最多只能有一个变长参数。
3. **底层原理**：Java 编译器实际上会将变长参数转换为一个**数组**。因此，你也可以直接传入一个对应类型的数组给变长参数方法。

## 动手练习：字符串拼接器

编写一个方法 `joinWords`，接收一个分隔符和任意数量的单词，将它们拼接成一个字符串。

```java
String joinWords(String delimiter, String... words) {
    String result = "";
    for (int i = 0; i < words.length; i++) {
        result += words[i];
        // 如果不是最后一个单词，就加上分隔符
        if (i < words.length - 1) {
            result += delimiter;
        }
    }
    return result;
}

void main() {
    String sentence = joinWords("-", "Java", "is", "cool");
    IO.println(sentence); // 输出: Java-is-cool
}
```

## 本节小结

我们学习了方法的定义、调用、重载以及变长参数，并通过“计算平均分”和“字符串拼接器”两个程序巩固了方法的用法。

**第一章：Java 基础语法到这里就圆满结束了！**

通过这一章的学习，你已经掌握了 Java 编程最核心的“零件”：

1. **环境**：安装了 JDK 25 和 IntelliJ IDEA。
2. **数据**：学习了变量、基本类型和数组。
3. **逻辑**：掌握了算术运算、条件判断和循环。
4. **封装**：学会了如何编写和调用方法。

---

**接下来，我们将开启第二章：面向对象编程 (OOP)。** 这是 Java 的精髓所在，我们将学习如何定义类、创建对象，并模拟现实世界中的复杂系统。
