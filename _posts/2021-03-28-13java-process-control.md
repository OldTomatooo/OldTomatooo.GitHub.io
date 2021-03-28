---
layout: post
title: 笔记分享第12期——Java流程控制Part4
date: 2021-3-28
categories: blog
tags: [Java流程控制]
description: 这是我的Java学习笔记第12期，话不多说直插主题——
---
# Java流程控制Part4
这期讲讲循环

有关我笔记分享的文章，我都会附上下载链接，不想去CSDN下载的朋友可以去看我独立博客的Milestonr里放的百度网盘下载链接。
本期笔记下载链接：https://download.csdn.net/download/lbwnbnbnbn/16183946

Ayo大家好我是Tomatooo，这是我的笔记分享的12期，直插主题——
## While循环

`while`是最基本的循环，它的结构为：

```Java
while(布尔表达式){
  //循环体
}
```

只要布尔表达式为 `true`，循环就会一直执行下去，如果结果为`false`，那就直接跳到`while`循环的末尾，继续往下执行。

1加到100就可以这样写：

```java
public class Main {
    public static void main(String[] args) {
        int sum = 0;
        int n = 0;
        while (n <= 100) {
            n ++; //n的值加1
            sum = sum + n;
        }
        System.out.println(sum);
    }
}
```

这里可能不太好理解，多花点时间想一想就好

死循环：

```java
public class Main {
    public static void main(String[] args) {
        int sum = 0;
        int n = 1;
        while (n > 0) {
            n ++;
            sum = sum + n;
        }
        System.out.println(n); // -2147483648
        System.out.println(sum);//-1073741824
    }
}

```

上面的while循环是一个死循环，但是，Java的int类型有最大值，达到最大值后，再加1会变成负数，就退出了while循环。

## do while循环

```Java
do {
       //代码语句
}while(布尔表达式);
```

do…while 循环和 while 循环相似，不同的是，do…while 循环至少会执行一次，因为do while循环是先执行再判断的，与`while`大同小异

## for循环

Java使用最广泛的是for循环。

for循环执行的次数是在执行前就确定的。语法格式如下：

```Java
for(初始化; 布尔表达式; 更新表达式) {
    //代码语句
}
```

把1到100求和用for循环改写一下：

```Java
public class Main {
    public static void main(String[] args) {
        int sum = 0;
        for (int i=1; i<=100; i++) {
            sum = sum + i;
        }
        System.out.println(sum);
    }
}

```

使用for循环时，切记不要在循环体内修改计数器！在循环体中修改计数器常常导致莫名其妙的逻辑错误。

for循环还可以缺少初始化语句、循环条件和每次循环更新语句，通常不推荐这样写，但是，某些情况下，是可以省略for循环的某些语句的。

for循环经常用来遍历数组，因为通过计数器可以根据索引来访问数组的每个元素

[Java Basic Grammar](https://www.wolai.com/e36U7L8NxcgWk62xePUfHP)

## 增强 for 循环

Java5 引入了一种主要用于数组的增强型 for 循环（即for each循环），它可以更简单地遍历数组，Java 增强 for 循环语法格式如下:

```java
for(声明语句 : 表达式)
{
   //代码句子
}
```

遍历数组：

```Java
public class Main {
   public static void main(String args[]){
      int [] numbers = {10, 20, 30, 40, 50};
 
      for(int x : numbers ){
         System.out.print( x );
         System.out.print(",");
      }
      System.out.print("\n");
      String [] names ={"James", "Larry", "Tom", "Lacy"};
      for( String name : names ) {
         System.out.print( name );
         System.out.print(",");
      }
   }
}
```



## break

无论是`while`循环还是`for`循环，有两个特别的语句可以使用，就是`break`语句和`continue`语句。`break`语句可以跳出当前执行的循环：

```java
public class Main {
    public static void main(String[] args) {
        int sum = 0;
        for (int i=1; ; i++) {
            sum = sum + i;
            if (i == 100) {
                break;
            }
        }
        System.out.println(sum);
    }
}

```

要特别注意，`break`语句总是跳出自己所在的那一层循环。

## continue

与`break`不同，`continue`则是提前结束本次循环，直接继续执行下次循环，在多层嵌套的循环中，`continue`语句同样是结束本次自己所在的循环。

**注意**：continue只继续内层循环

---

The End

