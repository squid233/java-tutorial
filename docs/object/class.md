# 类

**类**（Class）是 Java 中所有引用类型的基本单元。

我们在[源文件](../basic/source_file.md)一节中曾用到没有类的源文件。本节，我们将创建第一个 Java 类。

## 创建类

创建一个类需要用`#!java class`关键字。因为创建类是频繁操作，所以 IDE 为我们写好了模板，我们只需要对包名右击，选择`New->Java Class->Class`，并输入类名，就能生成一个普通的 Java 类。

例如，在`com.example.myproject.animal`包下创建`Dog`类，创建好的类如下：

```java title="Dog.java"
package com.example.myproject.animal;

public class Dog {
}
```

其中`#!java package`语句用于指定类所属的包。

## 访问权限

类和其成员有一定的访问权限。用不同关键字修饰可得到不同结果：

| 关键字                     | 同类访问             | 子类访问             | 同包访问             | 跨包访问                             |
|-------------------------|------------------|------------------|------------------|----------------------------------|
| `#!java public`         | :material-check: | :material-check: | :material-check: | :material-check:                 |
| `#!java protected`      | :material-check: | :material-check: | :material-check: | :octicons-horizontal-rule-24:^1^ |
| 无（`package-private`^2^） | :material-check: | :material-close: | :material-check: | :material-close:                 |
| `#!java private`        | :material-check: | :material-close: | :material-close: | :material-close:                 |

<div style="font-size: .64rem" markdown>
1. 只有子类才能跨包访问。
2. 对于接口的成员，没有关键字修饰则为`#!java public`。
</div>

需要注意的是，顶部类（即直接声明在源文件中的类）不能用`#!java protected`或`#!java private`修饰。用`#!java public`修饰的顶部类，文件名和类名必须一致。

## 实例成员

类的实例成员，就是只能通过类的实例访问的字段和方法。

### 实例字段

声明在类中的变量我们称其为**字段**（Field）。字段可以被类中的方法访问。

在`Dog`类中创建实例字段字符串`name`和整数`age`如下：

```java
public class Dog {
    public final String name;
    public int age;
}
```

### `this`对象

在类的实例方法中，当方法的参数名、局部变量名或其他方法名与实例成员名冲突时，我们可以使用`#!java this`访问其他实例成员。

```java
public class Dog {
    // ...

    public void setAge(int age) {
        this.age = age;
    }
}
```

## 构造器

为了在接下来创建实例时给类传入参数，我们需要用到一种特殊的方法：**构造器**（Constructor，又称构造方法、构造函数）。构造器没有返回值，名称和类名相同。

在`Dog`类的构造器中传入`name`和`age`并初始化字段：

```java
public class Dog {
    // ...

    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

## 静态成员

与实例成员不同，静态成员不需要通过类的实例访问，可以直接通过类名访问。也就是说，静态成员与类的实例无关。类的静态成员用关键字`#!java static`修饰。

### 静态方法

在`com.example.myproject`包下创建一个`Main`类。在类中输入`psvm`并让 IntelliJ IDEA 自动补全：

```java title="Main.java"
package com.example.myproject;

public class Main {
    public static void main(String[] args) {
    }
}
```

上面代码声明的`main`方法就是[主方法](../basic/source_file.md#主方法)的完整形式，包括`#!java public`访问权限、`#!java static`修饰符、`#!java void`返回类型、`main`名称和一个`String[]`参数。

### 静态字段

静态字段与类的实例无关，因此在不同的地方访问一个静态字段，无论类创建了多少个实例，访问到的永远是同一个字段。

## 输出内容

要在类中输出内容，就需要用到`System.out`。`out`是`System`类中的一个静态字段，代表输出流，它的类型是`java.io.PrintStream`。`PrintStream`类中为我们提供了写入内容的方法：

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}
```

`println`和`print`都支持输出多种类型的内容。

此外，输入`sout`，IntelliJ IDEA 可以自动补全为`System.out.println`。

## 导入

### 导入类

引用其他包中的类时，为了避免每次都要写出包名，需要使用`#!java import`语句。Java 默认导入了`java.lang`包。

用星号能导入包中所有类。

```java
import com.example.myproject.animal.Dog; // 导入 Dog 类
import com.example.myproject.animal.*; // 导入 com.example.myproject.animal 中所有类

public class Main {
    // ...
}
```

### 静态导入

`#!java import static`语句能导入类中一个或所有静态成员。

=== "Main.java"

    ```java
    import static com.example.myproject.animal.Dog.of;
    
    public class Main {
        public static void main(String[] args) {
            var dog = of();
        }
    }
    ```

=== "Dog.java"

    ```java
    public class Dog {
        public static Dog of() {
            // ...
        }
    }
    ```

## 创建实例

我们在[数组](../basic/array.md)一节中其实已经创建过实例，只是本节我们创建的是类的实例。`#!java new`语句创建类的实例，并调用构造器：

```java
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog("Dog A", 2);
    }
}
```

我们现在可以通过`dog`来访问`Dog`类的实例成员：

=== "Main.java"

    ```java
    public class Main {
        public static void main(String[] args) {
            Dog dog = new Dog("Dog A", 2);
            dog.printInfo();
        }
    }
    ```

=== "Dog.java"

    ```java
    public class Dog {
        // ...

        public void printInfo() {
            System.out.println("Name: " + name);
            System.out.println("Age: " + age);
        }
    }
    ```

## 重载

Java 类中的方法参数不同时可以有相同的名称，称为重载（Overloads）。方法重载与返回类型无关，参数相同、返回类型不同的方法不能重载，编译器会报错。

```java
public class Dog {
    // ...

    public void eat() {
        System.out.println("Eat");
    }
    
    public void eat(String food) {
        System.out.println("Eat " + food);
    }
}
```
