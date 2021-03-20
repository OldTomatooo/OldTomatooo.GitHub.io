---
layout: post
title: 笔记分享第11期——Java流程控制Part3
date: 2021-3-20
categories: blog
tags: [Java流程控制]
description: 这是我的Java学习笔记第11期，话不多说直插主题——
---
# Java流程控制Part3

在有关我笔记分享的博文中，我都会将MD笔记文件另外发布，方便朋友们下载学习。本期笔记文件下载地址：[https://download.csdn.net/download/lbwnbnbnbn/15970774](https://download.csdn.net/download/lbwnbnbnbn/15970774)
不想去CSDN下载的朋友可以看完独立博客的`milestone`里放的百度网盘下载链接
Ayo大家好我是Tomatooo，这是我的Java学习笔记第11期，话不多说直插主题——

## Switch语句

`switch`语句可以跳转到匹配的`case`结果，然后继续执行后续语句，直到遇到`break`语句停止

不解代码之意，必不能善编程。先从字面意思上看：switch有选择之意（才不是你想的那个任天堂switch），break有中断之意，而default的意思之一是默认（值），case的意思是箱子，盒子。接下来看一个示例：

```java
public class Switch {
    public static void main(String[] args) {
        int choice = 1;
        switch (choice) {
        case 1:
            System.out.println("U chose 1");
            break;
        case 2:
            System.out.println("U chose 2");
            break;
        case 3:
            System.out.println("U chose 3");
            break;
        default:
            System.out.println("U chose default");
            break;
        }
    }
}

```

`case`相当于一个盒子，放着一堆代码，通过`switch`来选择执行一个`case`

`break`可以让程序中断，如果将`break`都去掉，那么执行`case2`中的代码后就会继续向下执行`case3`......这就是`case`的“穿透性”

`default`相当于默认值，如果上述代码中的`choice`=99，而99匹配不到对应的`case`，那么程序执行`default`中的代码。

如果上述代码用`if`语句表示就是：

```java
public class SwitchIf {
    public static void main(String[] args) {
        int choice = 1;
        if (choice == 1) {
            System.out.println("U chose 1");
        } else if (choice == 2){
            System.out.println("U chose 2");
        } else if (choice == 3){
            System.out.println("U chose 3");
        } else {
            System.out.println("U chose default");
        }
    }
}
```

对于多个`==`判断的情况，使用`switch`结构更加清晰。

如果几个`case`中的语句相同，可以这样写：

```java
int choice = 2;
        switch (choice) {
        case 1:
            System.out.println("U chose 1");
            break;
        case 2:
        case 3:
            System.out.println("U chose 2&3");
            break;
        default:
            System.out.println("U chose noting");
            break;
        }
```



使用`switch`语句时，只要保证有`break`，`case`的顺序不影响程序的逻辑，也就是说先写`case1`还是`case3`都没关系。（还是建议按照顺序排列，便于查找和阅读）

另外，`switch语句`也可通过字符串类型`String`来匹配`case`

`switch`语句也可使用枚举类型，枚举类型在后面讲解

这下就理解了`switch`语句的基本语法了吧？

## switch 表达式

前面提到过，遗漏`switch`的后果很严重，从Java 12开始，`switch`语句有了为更简洁的表达式语法，使用类似模式匹配（Pattern Matching）的方法，这做到了不需要`break`语句就能确保只有一种路径被执行。示例如下：

```java
public class PatternMatching {
    public static void main(String[] args) {
        int choice = 4;
        switch (choice) {
        case 1 -> System.out.println("U chose 1");
        case 2,3 -> System.out.println("U chose 2 or 3");
        case 4  -> {
            System.out.println("U chose 4");
            System.out.println("U are sensible!");
        }
        default -> System.out.println("There isn't a choice like that");
        }
    }
}
```

如`case2,3`可以在一句语句中设立两个`case`,用逗号分隔

如`case4`，如果有多条语句，需要用`{}`括起来。

如今很多企业依旧在用JDK8，原因无需多说，所以会写这种写法就好

## yield关键字

`yield`是java13的新关键字（如有错误欢迎广大网友指正），了解就好

多数情况下，在`switch`语句中，我们会返回简单的值。

也有需要复杂语句的情况，我们就可以用`yield`，看个例子：

```java
public class yield {
    public static void main(String[] args) {
        String number = "nine";
        int opt = switch (number) {
            case "one" -> 1;
            case "two", "tu" -> 2;
            default -> {
                int code = number.hashCode();//hashcode函数，暂时无需了解，了解yield就好
                yield code; // switch语句返回值
            }
        };
        System.out.println("opt = " + opt);
    }
}
```

---

<font size=6>The End</font>
