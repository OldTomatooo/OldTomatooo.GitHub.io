---
layout: post
title: 笔记分享第15期——Java面向对象Part1
date: 2021-4-24
categories: blog
tags: [Java面向对象操作]
description: 在之前的学习中，我们学习了Java的一些基础语法，这篇文章我们就来学习Java语言的一个难点——面向对象(OOP)
---
# Java学习笔记第15期——Java 面向对象 Part1
有关笔记分享的博客中，我都会将md文件下载链接附上，不想在CSDN下载的朋友可以去我独立博客里MileStone中的链接下载
本期下载链接：[https://download.csdn.net/download/lbwnbnbnbn/16794968](https://download.csdn.net/download/lbwnbnbnbn/16794968)

# 前言

在之前的学习中，我们学习了Java的一些基础语法，这篇文章我们就来学习Java语言的一个难点——面向对象(OOP)

# 什么是面向对象？

Java是一种面向对象的编程语言。面向对象编程，英文是Object-Oriented Programming，简称OOP。

如果你以前没有接触过面向对象的编程语言，那可能需要先了解一些面向对象语言的一些基本特征，在头脑里头形成一个基本的面向对象的概念，这样有助于你更容易的学习 Java 的面向对象编程

Java作为一种面向对象语言，支持以下基本概念：

- 多态

- 继承

- 封装

- 抽象

- 类

- 对象

- 实例

- 方法

- 重载

回归正题。

现实世界中，我们定义了“人”这种概念，而具体的人有“Linus”、“MJ”、“川普”等一个个具体的人。所以，“人”可以视作为一个类（class），而具体的人就是实例（instance）

| 现实世界 | 计算机模型 | 代码                          |
| -------- | ---------- | ----------------------------- |
| 人間     | 类         | class Person { }              |
| Linus    | 实例       | Person linus = new Person（） |
| MJ       | 实例       | Person mj = new Person（）    |
| 川普     | 实例       | Person trump = new Person（） |

![emmmmm](https://img-blog.csdnimg.cn/20210421175643534.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xid25ibmJuYm4=,size_16,color_FFFFFF,t_70#pic_center)


看完这张图应该就明白类，实例，和对象的关系了

所以，只要理解了类和实例的概念，基本上就明白了什么是面向对象编程。

# 定义类

 ```java
 class Person {
     public String name;
     public int age;
 }
 ```


一个`class`可以包含多个字段（`field`），字段用来描述一个类的特征，也就是上面那张图的Property。上面的，我们定义了两个`field`，一个是`String`类型的，命名为`name`，另一个是`int`类型的命名为`age`。通过`class`，把一组数据汇集到一个对象上，实现了**封装**。

`class`前面可以加上`public`。 `public`是用来修饰字段的，它表示这个字段可以被外部访问。与其对应的是`private`,之后细讲

记得之前提到的`String`类型吗？这就是JDK源码中定义的类型。定义`class`其实就是定义了一种数据类型。

# 创建实例

如果要根据对象创建出对象实例，就得用new操作符。(就是常说的new一个对象[doge] )

拿懂王举例子：

 ```Java
 Person trump = new Person（）;
 ```


上述代码创建了一个Person类型的实例，并通过变量trump指向该实例。

有了trump这个变量，我们就可以操作这个实例：

 ```java
 /* main方法啥的就省了哈 */
 Person trump = new Person（）;
 trump.name = "Donald Trump"; // 对field name赋值
 trump.age = 74; // 对field age赋值
 System.out.println(trump.name); // 访问field name
 
 ```


 ```纯文本
             ┌─────────────────────┐
 trump ─────>│Person instance      │
             ├─────────────────────┤
             │name = "Donald Trump"│
             │age = 74             │
             └─────────────────────┘
 
 ```


每个instance拥有class定义的name和age字段，且各自都有一份独立的数据，互不干扰。就像两只狗类，每只狗有各自的毛发颜色，品种。

# 小结

定义`class`就是定义了一种数据类型，对应的`instance`是这种数据类型的实例；

`class`定义的`field`，在每个`instance`都会拥有各自的`field`，互不干扰；

通过`new`操作符创建`instance`，然后让一个变量指向它，即可通过变量来引用这个`instance`；

访问实例字段的方法是`变量名.字段名;`

指向`instance`的变量都是引用变量。

<center><b>時辛丑年叁月拾日</center>
<center><b>寫於公元貳零貳壹年肆月貳拾壹日
<center><b>The end
