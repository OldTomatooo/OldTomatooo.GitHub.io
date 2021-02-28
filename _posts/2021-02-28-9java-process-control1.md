# Java 流程控制 Part1

在有关我笔记分享的博文中，我都会将MD笔记文件另外发布，方便朋友们下载学习。
本期笔记文件下载地址：https://download.csdn.net/download/lbwnbnbnbn/15499665
不想去CSDN下载的朋友也可以看我独立博客中Milestone里发布的百度网盘下载地址
Ayo大家好我是Tomatooo，这是我的Java学习笔记第9期，话不多说直插主题——

## 前言

Java中，JVM默认按照从上到下的顺序执行以分号`;`结束的语句。但是，在实际的代码中，程序经常需要做条件判断、循环，流程控制语句应运而生。

本章我们将介绍如`if`,`switch`,`while`等流程控制语句

## 输入和输出

### 输出

先前的代码中，我们总是用`System.out.println();`来进行输出操作，`println()`为print line 的缩写，即表示输出并换行，如果不想换行，可以用`print()`

### 格式化输出

格式化输出存在的意义就是为了让输出的数据变得更易理解

示例：

```java
public class Main {
    public static void main(String[] args) {
        double d = 12900000;
        System.out.println(d); // 1.29E7
    }
}
```



1.29E7这个数能让人很容易理解吗？不能，这时候就要用到格式化输出功能。

格式化输出使用`System.out.printf()`，通过使用占位符`%?`，`printf()`可以把后面的参数格式化成指定格式（这里跟C语言很像）

示例：

```java
public class Main {
    public static void main(String[] args) {
        double d = 3.1415926;
        System.out.printf("%.2f\n", d); // 显示两位小数3.14
        System.out.printf("%.4f\n", d); // 显示4位小数3.1416
    }
}
```

Java的格式化功能提供了多种占位符，可以把各种数据类型“格式化”成指定的字符串：

| 占位符 | 说明                             |
| :----- | :------------------------------- |
| %d     | 格式化输出整数                   |
| %x     | 格式化输出十六进制整数           |
| %f     | 格式化输出浮点数                 |
| %e     | 格式化输出科学计数法表示的浮点数 |
| %s     | 格式化字符串                     |

由于%表示占位符，因此，连续两个%%表示一个%字符本身。

另外，可以把整数转换为十六进制，并且指定输出多少字符：

```java
public class Main {
    public static void main(String[] args) {
        int n = 12345000;
        System.out.printf("n=%d, hex=%08x", n, n); /* 注意，两个%占位符必须传入两个数
        这里`%08x`的意思是输出8个字符，用0来代替其多余的位置*/
    }
}

```

详细的格式化参数请参考JDK官方文档[java.util.Formatter](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Formatter.html#syntax)

### 输入

Java的输入要比输出复杂得多

示例：

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); // 创建Scanner对象(对象后期会讲)
        System.out.print("Input your name: "); // 打印提示
        String name = scanner.nextLine(); // 读取一行输入并获取字符串
        System.out.print("Input your age: "); // 打印提示
        int age = scanner.nextInt(); // 读取一行输入并获取整数
        System.out.printf("Hi, %s, you are %d\n", name, age); // 格式化输出，用println()也可以达到效果
    }
```

首先，我们通过`import`语句导入`java.util.Scanner`，（即导包）`import`是导入某个类的语句，必须放到Java源代码的开头，后面会讲。

然后，创建`Scanner`对象并传入`System.in`（后面会讲）。`System.out`代表标准输出流，而`System.in`代表标准输入流。直接使用`System.in`读取用户输入虽然是可以的，但需要更复杂的代码，而通过`Scanner`就可以简化后续的代码。

要读取用户输入的字符串，使用`scanner.nextLine()`，要读取用户输入的整数，使用`scanner.nextInt()`。`Scanner`会自动转换数据类型，因此不必手动转换。另外还有`nextDouble()`等等。

---**The End**---

# 看都看到这儿了，不去Github给我个Star嘛(～￣▽￣)～
