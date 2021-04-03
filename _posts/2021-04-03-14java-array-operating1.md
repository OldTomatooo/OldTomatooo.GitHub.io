---
layout: post
title: 笔记分享第13期——Java数组操作Part1
date: 2021-4-3
categories: blog
tags: [Java数组操作]
description: 这是我的Java学习笔记第13期
---

# Java学习笔记第13期——Java数组操作Part1

有关我笔记分享的文章，我都会附上下载链接，不想去CSDN下载的朋友可以去看我独立博客的Milestone里放的百度网盘下载链接
本期笔记下载链接：[https://download.csdn.net/download/lbwnbnbnbn/16392174](https://download.csdn.net/download/lbwnbnbnbn/16392174)
Ayo大家好我是Tomatooo，这是我的笔记分享的13期，直插主题——

# Java数组操作Part1

## 遍历数组

之前介绍过数组的基本知识，有了数组，我们还要操作它，而最常见的数组就是遍历。

通过`for`循环就可以遍历数组。示例：

 ```java
 public class Main {
     public static void main(String[] args) {
         int[] list = { 1, 4, 9, 16, 25 };
         for (int i=0; i<list.length; i++) {
             int n = list[i];
             System.out.println(n);
         }
     }
 }
 ```


第二种方式是使用`for each`循环

 ```Java
 public class Main {
     public static void main(String[] args) {
         int[] list = { 1, 4, 9, 16, 25 };
         for (int n : list) {
             System.out.println(n);
         }
     }
 }
 ```


> 这一种循环更加简洁，但是for each循环无法拿到数组的索引，因此到底用哪一种取决于个人需求


## 打印数组内容

直接打印数组变量，得到的是数组在JVM中的引用地址，示例：

 ```java
 int[] list = { 1, 1, 2, 3, 5, 8 };
 System.out.println(list);
 ```


多数情况下，这显然没有什么意义，因为我们希望打印的数组的元素内容。这时就需要使用for each循环来打印它

 ```java
 int[] ns = { 1, 1, 2, 3, 5, 8 };
 for (int n : list) {
     System.out.print(n + ", ");
 }
 
 ```


使用for each循环打印也很麻烦。我们可以使用Java标准库提供的`Arrays.toString()`来快速打印数组内容。

 ```java
 import java.util.Arrays;
 
 public class Main {
     public static void main(String[] args) {
         int[] list = { 1, 1, 2, 3, 5, 8 };
         System.out.println(Arrays.toString(list));
     }
 }
 
 ```


## 数组排序

熟悉的冒泡排序：

 ```java
 import java.util.Arrays;
 
 public class Main {
     public static void main(String[] args) {
         int[] list = { 28, 12, 89, 73, 65, 18, 96, 50, 8, 36 };
         // 排序前:
         System.out.println(Arrays.toString(list));
         for (int i = 0; i < list.length - 1; i++) {
             for (int j = 0; j < list.length - i - 1; j++) {
                 if (list[j] > list[j+1]) {
                     int a = list[j];
                     list[j] = list[j+1];
                     list[j+1] = a;
                 }
             }
         }
         // 排序后:
         System.out.println(Arrays.toString(list));
     }
 }
 
 ```


Java的标准库已经内置了排序功能，我们只需要调用JDK提供的`Arrays.sort()`就可以排序:

 ```java
 import java.util.Arrays;
 
 public class Main {
     public static void main(String[] args) {
         int[] list = { 28, 12, 89, 73, 65, 18, 96, 50, 8, 36 };
         Arrays.sort(list);
         System.out.println(Arrays.toString(list));
     }
 }
 ```


 ```纯文本
 对数组排序实际上修改了数组本身。例如，排序前的数组是：
 int[] list = { 9, 3, 6, 5 };
 在内存中，这个整型数组表示如下：
         ┌───┬───┬───┬───┐
 list───>│ 9 │ 3 │ 6 │ 5 │
         └───┴───┴───┴───┘
 当我们调用Arrays.sort(list);后，这个整型数组在内存中变为：
 
 ┌───┬───┬───┬───┐
 │ 3 │ 5 │ 6 │ 9 │
 └───┴───┴───┴───┘
 即变量list指向的数组内容已经被改变了。
 
 如果对一个字符串数组进行排序，例如：
 
 String[] list = { "banana", "apple", "pear" };
 排序前，这个数组在内存中表示如下：
 
                        ┌──────────────────────────────────┐
                    ┌───┼──────────────────────┐           │
                    │   │                      ▼           ▼
              ┌───┬─┴─┬─┴─┬───┬────────┬───┬───────┬───┬──────┬───┐
 list   ─────>│░░░│░░░│░░░│   │"banana"│   │"apple"│   │"pear"│   │
              └─┬─┴───┴───┴───┴────────┴───┴───────┴───┴──────┴───┘
                │                 ▲
                └─────────────────┘
 调用Arrays.sort(list);排序后，这个数组在内存中表示如下：
 
                      ┌──────────────────────────────────┐
                  ┌───┼──────────┐                       │
                  │   │          ▼                       ▼
            ┌───┬─┴─┬─┴─┬───┬────────┬───┬───────┬───┬──────┬───┐
 list ─────>│░░░│░░░│░░░│   │"banana"│   │"apple"│   │"pear"│   │
            └─┬─┴───┴───┴───┴────────┴───┴───────┴───┴──────┴───┘
              │                              ▲
              └──────────────────────────────┘
 原来的3个字符串在内存中均没有任何变化，但是数组的每个元素指向变化了。
 ```

**The End**
