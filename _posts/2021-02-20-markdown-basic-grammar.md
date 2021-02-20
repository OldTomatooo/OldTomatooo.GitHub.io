---
layout: post
title: 笔记分享第01期——Markdown基础语法
date: 2020-2-20
categories: blog
tags: [Markdown]
description: 所谓工欲善其事，必先利其器，MD作为优秀的轻量级语言，是我们做笔记的不二之选...
---

# Java学习笔记第01期——Markdown基础语法
**在有关我笔记分享的博客中，我都会将MD笔记文件另外附上，方便朋友们下载学习（粉丝可下载）**

**本期笔记文件下载地址：https://download.csdn.net/download/lbwnbnbnbn/15077490**

**不想去CSDN下载的朋友也可以看我Milestone里发布的百度网盘下载地址**

大家好，我是Tomatooo。所谓工欲善其事，必先利其器，学习的过程中，笔记是必不可少的，MD作为优秀的轻量级语言，是我们做笔记的不二之选，这篇文章就和大家分享Markdown的一些基础语法。

## 标题："\#"+文本 (1个\#为一级标题，2个\#为二级标题，以此类推)
## 字体：
粗体：

文本左右加2个"\*"

 **示例**:**Hello World!**
斜体：

文本左右加1个"\*" 

**示例**:*Hello World!*
加粗斜体：

文本左右加3个"\*"

**示例**:***Hello World!***
删除线：

文本左右加两个"\~" 

**示例**：~~Hello World!~~

## 引用："\>"
**示例**：
>关注Tomatooo，走向人生巅峰
## 分割线："\-\-\-"或"\*\*\*"
**示例**：
***
---
## 插入图片：\!\+\[\+随意名字\+\]\+\(\+图片路径\+\)
注意：一定要在英文状态输入符号，图片路径可以是本地的，也可以是网络上的
**示例**：
![截图](https://i0.hdslb.com/bfs/face/9946287791abe1462bbc09e72fc87a0be54026e8.jpg@85w_85h.jpg)
## 超链接：\[\+文本\+\]+\(\+链接\+\)
**示例**：[点击跳转到百度](www.baidu.com)

## 列表
### 有序列表
1+"."+空格，输入文本,然后回车，自动生成2，3......
**示例**：
1. 关注了吗
2. 关注走向人生巅峰
3. ssd@#￥k6￥%#……￥%@34hdkfl
### 无序列表
"-"+空格，输入文本，然后回车
**示例**：

- 关注了吗
- 关注走向人生巅峰
- ssd@#￥k6￥%#……￥%@34hdkfl
## 表格
XXX\|XXX\|XXX             然后换行
\-\-\|\-\-\|\-\-然后换行
XXX\|XXX\|XXX

**示例**：
姓名|性别|是否犯罪
--|--|--
张三|男|是

## 代码框
三个"\`"后加编程语言种类,换行，加三个点结束
**示例**:
```java 
System.out.prinln("Hello,World!");
```
# 看都看到这儿了，不去Github给我个Star嘛(～￣▽￣)～