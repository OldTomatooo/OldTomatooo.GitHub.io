---
layout: post
title: 笔记分享第06期——Java基础语法Part5
date: 2021-2-20
categories: blog
tags: [Java基础语法]
description: 这是我的Java学习笔记第6期，话不多说直插主题——
---

# Java 基础语法 Part5

**Ayo大家好我是Tomatooo，这是我的Java学习笔记第6期，话不多说直插主题——**

**在有关我笔记分享的博文中，我都会将MD笔记文件另外发布，方便朋友们下载学习。**
**本期笔记文件下载地址：https://download.csdn.net/download/lbwnbnbnbn/15364021**
**不想去CSDN下载的朋友也可以看我Milestone里发布的百度网盘下载地址**

## 浮点数运算
### 误差
浮点数运算只能进行加减乘除这些数值计算，不能做位运算和移位运算。
浮点数虽然表示的范围大，但是浮点数常常无法精确表示，会有误差，例如十进制中的0.1转换成二进制是一个无限循环小数。
误差示例：
```java
public class Main {
    public static void main(String[] args) {
        double x = 1.0 / 10;
        double y = 1 - 9.0 / 10;
        // 观察x和y是否相等:
        System.out.println(x);//0.1
        System.out.println(y);//0.09999999999999998
    }
}
```
### 类型提升
如果参与运算的两个数其中一个是整型，那么整型可以自动提升到浮点型
**注意：需要特别注意，在一个复杂的四则运算中，两个整数的运算不会出现自动提升的情况。**示例：
```java
double d = 1.2 + 24 / 5; // 5.2
```
编译器计算`24 / 5`这个子表达式时，按两个整数进行运算，结果仍为整数`4`
### 溢出
整数运算在除数为`0`时会报错，而浮点数运算在除数为`0`时，不会报错，但会返回几个特殊值：

- `NaN`表示Not a Number
- `Infinity`表示无穷大
- `-Infinity`表示负无穷大
### 强制类型转换

浮点数可以强制转换成整数，转换时小数部分会被丢掉，如果转型后超过了整型能表示的最大范围，将返回整型的最大值。

如果要进行四舍五入，可以对浮点数加上0.5再强制转型。

## 布尔运算

布尔类型只有`true`和`false`两个值。

### 关系运算符

布尔运算是种关系运算，关系运算符包括：

- 比较运算符：`>`，`>=`，`<`，`<=`，`==`，`!=`
- 与运算 `&`
- 或运算 `|`
- 非运算 `!`

### 短路运算

如果一个布尔运算表达式能提前确定结果，则后续的计算不再执行，直接返回结果。

短路与：`&&`

短路或：||

### 三元运算符

三元运算符也叫三目运算符`b ? x : y`，它根据第一个布尔表达式的结果，分别返回后续两个表达式之一的计算结果。(三元运算也是“短路运算”)

```java
public class demo {
    public static void main(String[] args) {
        int x = -100;
        int b = x >= 0 ? x : -x;
        System.out.println(b);
    }
}

```

上述语句判断`b >= 0`是否成立，如果为`true`，则返回`n`，否则返回`-n`。

**三元运算`b ? x : y`会首先计算`b`，如果`b`为`true`，则只计算`x`，否则，只计算`y`。**

**另外，`x`和`y`的类型必须相同**

# 看都看到这儿了，不去Github给我个Star嘛(～￣▽￣)～

