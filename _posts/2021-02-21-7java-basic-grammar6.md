---
layout: post
title: 笔记分享第07期——Java基础语法Part6
date: 2021-2-21
categories: blog
tags: [Java基础语法]
description: 这是我的Java学习笔记第7期，话不多说直插主题——
---

# Java 基础语法 Part6

Ayo大家好我是Tomatooo，这是我的Java学习笔记第8期，话不多说直插主题——

在有关我笔记分享的博文中，我都会将MD笔记文件另外发布，方便朋友们下载学习。本期笔记文件下载地址：
https://download.csdn.net/download/lbwnbnbnbn/15406191
不想去CSDN下载的朋友也可以看我独立博客中Milestone里发布的百度网盘下载地址

## 字符和字符串

### 字符类型char

字符类型`char`是基本数据类型之一，是`character`的缩写。

一个`char`保存一个`Unicode`字符。

Java在内存中总是使用Unicode表示字符，一个英文字符和一个中文字符都用一个`char`类型表示，它们都占用两个字节。

如果要显示一个字符的Unicode编码，只需将`char`类型直接赋值给`int`类型即可。

示例：

```java
int c1 = 'A'//字母“A”的Unicodde编码是65

int c2 = '中'// 汉字“中”的Unicode编码是20013
```

还可以直接用转义字符`\u`+Unicode编码来表示一个字符：（“这里注意Unicode编码是16进制”）

```java
char c3 = '\u0041'; // 'A'，因为十六进制0041 = 十进制65
char c4 = '\u4e2d'; // '中'，因为十六进制4e2d = 十进制20013
```

### 字符串类型

字符串类型`String`不是基本数据类型而是引用类型，用双引号表示字符串。一个字符串可以存储任意个字符。

注意：Java是大小写敏感的，`String`的`S`一定要大写

那么如何将含有双引号的字符赋值给`String`类型呢？

```java
String s = "Java is" the best language."//这里会报错，因为编译器不知道双引号从那里结束
```

这时候就要用到转义字符`\`了

```java
String s = "Java is \" the best language."
```

这样就不会报错了。

常见的转移字符有：

- `\"` 表示字符`"`
- `\'` 表示字符`'`
- `\\` 表示字符`\`
- `\n` 表示换行符
- `\r` 表示回车符
- `\t` 表示Tab
- `\u####` 表示一个Unicode编码的字符

**那么如何连接字符串呢？**

Java的编译器对字符串做了特殊照顾，可以使用`+`连接任意字符串和其他数据类型

如果用`+`连接字符串和其他数据类型，会将其他数据类型先自动转型为字符串，再连接

```java
public class Main {
    public static void main(String[] args) {
        int age = 25;
        String s = "age is " + age;
        System.out.println(s);
    }
}
```

**怎样表示多行字符串呢？**

如果我们要表示多行字符串，使用+号连接会非常不方便，从Java 13开始，字符串可以用`"""  """`表示多行字符串（Text Blocks）了

示例：（格式原因可能显示有误，望谅解，`"""` `"""`中每个单词独占一行）

```java
public class Main {
    public static void main(String[] args) {
        String s = """
                    Java
                    Is
                    The
                    Best
                    Language
                   """;
        System.out.println(s);
    }
}
```

上述多行字符串实际上是6行,

如果我们不想多这一行，就需要把后面的`"""`与上面代码中的"Language"放在同一行。

还需要注意到，多行字符串前面共同的空格会被去掉。如果多行字符串的排版不规则，那么总是以最短的行首空格为基准。

**字符串的不可变特性**

Java的字符串除了是一个引用类型外，还有个重要特点，就是字符串不可变。

```java
public class Main {
    public static void main(String[] args) {
        String s = "hello";
        System.out.println(s); // 显示 hello
        s = "world";
        System.out.println(s); // 显示 world
    }
}

```

s这个变量看似是变了，对不对？实则不然，是变量s的`指向`变了。

执行`String s = "hello";`时，JVM虚拟机先创建字符串`"hello"`，然后，把字符串变量`s`指向它：

```ascii
      s
      │
      ▼
┌───┬───────────┬───┐
│   │  "hello"  │   │
└───┴───────────┴───┘
```

紧接着，执行`s = "world";`时，JVM虚拟机先创建字符串`"world"`，然后，把字符串变量`s`指向它：

```ascii
      s ──────────────┐
                      │
                      ▼
┌───┬───────────┬───┬───────────┬───┐
│   │  "hello"  │   │  "world"  │   │
└───┴───────────┴───┴───────────┴───┘
```

原来的字符串`"hello"`其实还在，只是我们无法通过变量`s`访问它而已。因此，字符串的不可变是指字符串内容不可变。

**空值**

引用类型的变量可以指向一个空值`null`，它表示不存在，即该变量不指向任何对象。

注意要区分空值`null`和空字符串`""`，空字符串是一个有效的字符串对象，它不等于`null`。

# 看都看到这儿了，不去Github给我个Star嘛(～￣▽￣)～

