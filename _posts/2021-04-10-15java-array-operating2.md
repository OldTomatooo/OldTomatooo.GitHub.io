---
layout: post
title: 笔记分享第14期——Java数组操作Part2
date: 2021-4-10
categories: blog
tags: [Java数组操作]
description: 本篇我们将学习数组操作最后一期：多堆数组和命令行参数的基础知识。下期预告：Java面向对象Part1
---
# Java学习笔记第14期——Java数组操作Part2
有关笔记分享的博客中，我都会将md文件下载链接附上，不想在CSDN下载的朋友可以去我独立博客里MileStone中的链接下载
本期笔记下载链接：[https://download.csdn.net/download/lbwnbnbnbn/16607073](https://download.csdn.net/download/lbwnbnbnbn/16607073)
## 前言

本篇我们将学习数组操作最后一期：多堆数组和命令行参数的基础知识。下期预告：Java面向对象Part1

## 多维数组

### 二维数组

二维数组就是数组的数组（套娃）

 ```java
 public class Main {
     public static void main(String[] args) {
         int[][] list = {
             { 1, 2, 3, 4 },
             { 5, 6, 7, 8 },
             { 9, 10, 11, 12 }
         };
         System.out.println(list.length); //3
     }
 }
 
 ```


因为list包含3个数组，因此，list长度为3

访问二维数组的某个元素需要使用`[row][col]`，即第几个维度第几个元素

 ```Java
 System.out.println("list[1][2]");//7
 ```


要打印一个二维数组，可以使用两层嵌套的for循环

 ```java
 for (int[] array1 : array2) {
     for (int n : array1) {
         System.out.print(n);
         System.out.println(', ');
     }
 }
 ```


除此之外，我们还可以使用Java标准库中的`Arrays.deepToString()`

 ```java
 import java.util.Arrays;
 
 public class Main {
     public static void main(String[] args) {
         int[][] list = {
             { 1, 2, 3, 4 },
             { 5, 6, 7, 8 },
             { 9, 10, 11, 12 }
         };
         System.out.println(Arrays.deepToString(list));
     }
 }
 ```


### 三维数组

和二维数组大同小异

 ```Java
 int[][][] list = {
     {
         {1, 2, 3，4},
         {4, 5, 6，7},
         {8, 9}
     },
     {
         {10, 11},
     },
     {
         {99，0},
         {55，56，57}
     }
 };
 ```


如果我们要访问其中的某一个元素如7，与二维数组类似，用`list[0][1][3]`表示即可

理论上无限套娃是可以实现的，但实际应用中除了二维数组以外都很少被使用

---

## 命令行参数

入口方法Main方法可以接受一个命令行参数，它是一个`String`数组

> 这个命令行参数由JVM接收用户输入并传给main方法


 ```java
 public class Main {
     public static void main(String[] args) { //这里的args可以取其他名字
     }
 }
 ```


我们可以根据命令行参数执行不同代码，例如可以结合控制语句，实现一个打印版本号的功能，命令行参数可以再IDE里手动设置，（是不是有点软件开发者的感觉）

 ```Java
 public class Main {
     public static void main(String[] args) {
         for (String arg : args) {
             if ("-version".equals(arg)) {//用了String equals()方法用于比较字符串是否相等
                 System.out.println("Main--version 1.0");
                 break;
             }
         }
     }
 }
 ```


Java基础到这里就结束了，接下来就是面向对象了（难度UP↑）

**The End**
