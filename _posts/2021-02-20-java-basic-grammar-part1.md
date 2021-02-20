---
layout: post
title: 笔记分享第02期——Java基础语法Part1
date: 2021-2-20
categories: blog
tags: [Java基础语法]
description: 这是我的Java学习笔记第2期，话不多说直插主题——
---

# Java 基础语法 Part1

 **在有关我笔记分享的博客中，我都会将MD笔记文件另外发布，方便朋友们下载学习。（粉丝可下载）**

**本期笔记文件下载地址：https://download.csdn.net/download/lbwnbnbnbn/15086171**

---

 Ayo大家好我是Tomatooo，这是我的Java学习笔记第二期，话不多说直插主题——

## 注释

### 注意事项

注释不会执行，是写给程序员看的

### 单行注释

"//"+文本

单行内，双斜杠后面的文本将被视为注释，不被执行

示例：

```java
public class Tomatooo{
    public static void main (String[]args){
        System.out.println("关注Tomatooo");//爷是单行注释
    }
}
```



### 多行注释

"/\*"+文本+"\*/"

/**/内的文本被视为注释，不被执行

示例：

```java
public class Tomatooo{
    public static void main (String[]args) {
        System.out.println("关注Tomatooo");/*爷是多行注释*/
    }
}
```

### 文档注释（暂时仅做了解）

也被称作说明注释，它以 **/\**** 开始，以 ***/**结束。

说明注释允许你在程序中嵌入关于程序的信息。你可以使用 javadoc 工具软件来生成信息，并输出到HTML文件中。使你更加方便的记录你的程序信息。

JavaDoc标签

| **标签**      |                        **描述**                        |                           **示例**                           |
| :------------ | :----------------------------------------------------: | :----------------------------------------------------------: |
| @author       |                    标识一个类的作者                    |                     @author description                      |
| @deprecated   |                 指名一个过期的类或成员                 |                   @deprecated description                    |
| {@docRoot}    |                指明当前文档根目录的路径                |                        Directory Path                        |
| @exception    |                  标志一个类抛出的异常                  |            @exception exception-name explanation             |
| {@inheritDoc} |                  从直接父类继承的注释                  |      Inherits a comment from the immediate surperclass.      |
| {@link}       |               插入一个到另一个主题的链接               |                      {@link name text}                       |
| {@linkplain}  |  插入一个到另一个主题的链接，但是该链接显示纯文本字体  |          Inserts an in-line link to another topic.           |
| @param        |                   说明一个方法的参数                   |              @param parameter-name explanation               |
| @return       |                     说明返回值类型                     |                     @return explanation                      |
| @see          |               指定一个到另一个主题的链接               |                         @see anchor                          |
| @serial       |                   说明一个序列化属性                   |                     @serial description                      |
| @serialData   | 说明通过writeObject( ) 和 writeExternal( )方法写的数据 |                   @serialData description                    |
| @serialField  |             说明一个ObjectStreamField组件              |              @serialField name type description              |
| @since        |               标记当引入一个特定的变化时               |                        @since release                        |
| @throws       |                 和 @exception标签一样.                 | The @throws tag has the same meaning as the @exception tag.  |
| {@value}      |         显示常量的值，该常量必须是static属性。         | Displays the value of a constant, which must be a static field. |
| @version      |                      指定类的版本                      |                        @version info                         |

***

***

***

## 关键字

**Java关键字**

![标识符大全](https://img-blog.csdnimg.cn/20190826103037368.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkyODkzOQ==,size_16,color_FFFFFF,t_70)

---

---

---

## 标识符

类名，变量名，方法名都被称为标识符

注意：

- 关键字不能作为标识符
- 标识符应以字母/美元符号/下划线开始
- 标识符区分大小写
- 可以用中文命名标识符，但不推荐
- 标识符除首字符外，其余字符可以是字母，$，_，数字的任何字符组合


# 看都看到这儿了，不去Github给我个Star嘛(～￣▽￣)～
