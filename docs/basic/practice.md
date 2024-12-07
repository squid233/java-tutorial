---
comments: true
---

# 章后练习

## 身体质量指数

身体质量指数（BMI）是国际上常用的衡量人体胖瘦程度以及是否健康的一个标准。编写一个程序，读取用户输入，计算 BMI 的值并按下表输出其值（允许精度误差）和类别：

| 类别  | 范围          |
|-----|-------------|
| 偏瘦  | <= 18.4     |
| 正常	 | 18.5 ~ 23.9 |
| 过重  | 24.0 ~ 27.9 |
| 肥胖  | >= 28.0     |

计算公式为

$$
{\rm BMI} = w/h^2
$$

其中$w$为体重（kg)，$h$为身高（m）。

参考数据：

| h   | w  | BMI  | 类别 |
|-----|----|------|----|
| 1.6 | 45 | 17.6 | 偏瘦 |
| 1.8 | 70 | 21.6 | 正常 |
| 1.7 | 70 | 24.2 | 过重 |
| 1.6 | 80 | 31.3 | 肥胖 |

/// admonition | 提示
    type: tip
使用`Double.parseDouble(s)`来把字符串`s`转为`#!java double`。
///

/// details | 额外提示
    type: tip
1. 使用`readln`读取输入。
2. 使用条件语句。
///

/// details | 参考答案
    type: example
```java
void main() {
    double h = Double.parseDouble(readln("身高（m）："));
    double w = Double.parseDouble(readln("体重（kg）："));
    double bmi = w / (h * h);
    String type;
    if (bmi < 18.5) {
        type = "偏瘦";
    } else if (bmi < 24.0) {
        type = "正常";
    } else if (bmi < 28.0) {
        type = "过重";
    } else {
        type = "肥胖";
    }
    println("BMI: " + bmi);
    println("类别：" + type);
}
```
///

## 购物车（基础版）

某人要购买$n$个物品。现给以下物品标上序号：

1. 水
2. 面包
3. 书本

请你编写一个程序，读取用户输入的$n$个序号并逐个输出其对应的名称，没有编号的输出`未知`。要求使用到数组的遍历。

/// admonition | 提示
    type: tip
使用`Integer.parseInt(s)`来把字符串`s`转为`#!java int`。
///

/// details | 额外提示
    type: tip
1. 使用循环语句。
2. 使用`#!java switch`语句。
3. 不一定要把物品的序号转为`#!java int`。
///

/// details | 参考答案
    type: example
```java
void main() {
    int n = Integer.parseInt(readln("物品数："));
    String[] items = new String[n];
    for (int i = 0; i < n; i++) {
        items[i] = readln("序号：");
    }
    for (String item : items) {
        println(switch (item) {
            case "1" -> "水";
            case "2" -> "面包";
            case "3" -> "书本";
            default -> "未知";
        });
    }
}
```
///
