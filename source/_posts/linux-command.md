title: Linux基本命令
date: 2018-04-19 08:30:00
categories: 教程
tags: Linux
---
使用Linux系统，第一件事当然是学Linux命令。本篇罗列了一些基本命令。
<!--more-->

## 文件
- 创建 touch
```
    用法：touch a.txt
    touch  a.txt  b.txt  c.txt
```
- 删除 rm
```
    用法：rm a.txt
    rm a.txt b.txt c.txt
```
- 查看文本内容 
```
    cat 查看全部
    用法：cat a.txt

    head 查看前10（默认）行
    用法：head a.txt

    head -n a.txt 
    查看前 n 行

    tail 查看末尾10（默认）行
    用法：tail a.txt

    tail -n a.txt 
    查看末尾 n 行
```
## 文件夹
- 创建 mkdir
```
    用法：mkdir music

    mkdir  music  movie  picture
```
- 删除 rm -r
```
    用法：rm -r music

    rm -r  music movie  picture
```
> 未完待续