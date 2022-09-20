---
title: Linux基本命令
date: 2018-04-19 08:30
---
使用Linux系统，第一件事当然是学Linux命令。本篇罗列了一些基本命令。
<!--more-->

---

## 列出内容 ls

> ( list 列表、列出 )

常用的选项：

```shell
-A  (all，显示所有，包含隐藏内容)  
-s  (size，显示内容的大小)
-l  (long，显示长格式，详细信息)
-r  (reverse，倒序排列)
-S  (sort=size，按大小排列)
-t  (time，按最后修改时间排列)
```

选项可以组合使用：

```shell
 ls  -lt
 ls  -lS
 ls  -lr
 ```
 

## 文件
- 创建 touch
```shell
    touch  a.txt
    touch  a.txt  b.txt  c.txt
```
- 删除 rm
```shell
    rm a.txt
    rm a.txt b.txt c.txt
```
- 查看文本内容 
```shell
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
```shell
    mkdir  music
    mkdir  music  movie  picture
```
- 删除 rm -r
```shell
    rm -r  music
    rm -r  music movie  picture
```
