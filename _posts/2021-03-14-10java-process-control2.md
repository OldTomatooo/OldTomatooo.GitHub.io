---
layout: post
title: 笔记分享第10期——Java流程控制Part2
date: 2021-3-14
categories: blog
tags: [Java流程控制]
description: 这是我的Java学习笔记第10期，话不多说直插主题——
---

# Java 流程控制 Part2

在有关我笔记分享的博文中，我都会将MD笔记文件另外发布，方便朋友们下载学习。
本期笔记文件下载地址:
[https://download.csdn.net/download/lbwnbnbnbn/15786781](https://download.csdn.net/download/lbwnbnbnbn/15786781)
不想去CSDN下载的朋友也可以看我独立博客中Milestone里发布的百度网盘下载地址
Ayo大家好我是Tomatooo，这是我的Java学习笔记第10期，话不多说直插主题——

## if 语句

Java中，如果要根据条件来决定是否执行某一段代码，使用`if`语句是方法之一。

一个 `if` 语句包含一个布尔表达式和一条或多条语句。

```java
if (布尔表达式) {
    // 条件满足时执行
}
```

根据结果的`true`还是`false`，JVM决定是否执行`if`语句块。

示例：

```java
public class Main {
    public static void main(String[] args) {
        int age = 18;
        System.out.prinln("开始检测");
        if (n >= 18) {
            System.out.println("成年");
            System.out.println("检测结束");
        }
    }
}
```

当`if`语句块只有一行语句时，可以省略花括号，不过不推荐大家这样做，第一，不方便阅读，第二，如果给该if语句增加语句时，又肯会忘记加上花括号导致bug的产生。总之，大家写代码时要严格遵循规则规范。

## if...else语句

if 语句后面可以跟 else 语句，当 if 语句的布尔表达式值为 false 时，else 语句块会被执行。用法如下：

```java
if(布尔表达式){
   //如果布尔表达式的值为true
}else{
   //如果布尔表达式的值为false
}
```

## if...else if...else 语句

这种情况在开发中用到的次数是最多的。

```java
if(布尔表达式 1){
   //如果布尔表达式 1的值为true执行代码
}else if(布尔表达式 2){
   //如果布尔表达式 2的值为true执行代码
}else if(布尔表达式 3){
   //如果布尔表达式 3的值为true执行代码
}else {
   //如果以上布尔表达式都不为true执行代码
}
```

## if语句嵌套

顾名思义，就是if语句套if语句

示例：

```java
if(布尔表达式 1){
   ////如果布尔表达式 1的值为true执行代码
   if(布尔表达式 2){
      ////如果布尔表达式 2的值为true执行代码
   }
}
```

同理，也可以做到if else嵌套

## 样例

我们可以通过上一期讲到的通过`import`语句导入`java.util.Scanner`，结合条件语句做出一个简易的密码验证程序

```java
import java.util.Scanner;
public class Main {
    public static void main(String[]args){
        Scanner scanner = new Scanner(System.in);
        System.out.print("请输入密码：");
        int password = scanner.nextInt();
        if (password == 123456){
            System.out.println("密码正确");
        }else{
            System.out.println("密码错误");
        }
    }
}
```
---
<font size=9>**The End**</font>

---

# 看都看到这儿了，不去Github给我个Star嘛(～￣▽￣)～
