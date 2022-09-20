---
title: 训练营day02
date: 2018-08-25 17:31
---
一些 Linux 基础入门。希望大家都能有所收获。

<!-- more -->

---

# vi 操作：
	
以下操作，都是在普通模式下进行	
	
	复制   nyy  (yank 拉，复制的意思)
 		n 是一个整数（如果为 1，可以简写为 yy）
		从当前行开始，复制 n 行

  	粘贴   np   (paste)
		在当前行的下方，粘贴 n 遍
		
		
	删除（剪切）  ndd   
		从当前行开始，删除 n 行


撤销   u    (undo)

按 / 键或 ? 键，进入搜索模式，可以输入关键字进行搜索

G    跳转到最后一行  
ngg  跳转到第 n 行  
ctrl + f  往下翻半屏 （forward）  
ctrl + b  往上翻半屏 （backward）

## 练习：

	cal > a.txt
	vi a.txt
    利用上方所学技术，对日历进行操作
    使它成为投影所示的样子





# 一些快捷方式：
    ctrl + u   清空光标（鼠标提示符）左侧的部分
    ctrl + w   删除光标左侧的一个单词（word）

    alt + .    直接粘贴上一条命令的最后一个参数
        touch  abcd.txt
        rm (alt + .)   效果：  rm  abcd.txt


一次性创建多层（有嵌套关系的）目录

		mkdir  -p   a/b/c    (parent)缺啥补啥

		

# 起别名：起个外号、小名儿

## 临时设置和取消:

    格式：
        alias 自己起的名字='要执行的命令'
    比如：
        alias myls='ls -lh'
        以后用的时候，直接执行 myls 命令，相当于 ls -lh
        
        取消临时别名：
        unalias  myls

    如果想持久保存，需要修改配置文件  ~/.bashrc
        加一句  alias myls='ls -lh'

不要乱起别名（不要搞破坏）：
    
alias ls=' rm -rf ./* '

## 常见的使用场景

    alias go1='ssh -X root@38.29.33.1'  
    alias go2='ssh -X root@44.29.33.1'




关机：     poweroff  
重启：     reboot  
查看 ip 地址：   ifconfig  

	查看两台计算机是否能够通信：   
        ping  对方的 ip 地址
	
    ctrl + c  终止当前的进程

		
	
远程连接另一台电脑：

	ssh 用户名@ip地址
	ssh -X 用户名@ip地址

			
恢复命令：   
    rht-vmctl reset  classroom  
	rht-vmctl reset  server  
	rht-vmctl reset  desktop  
			
	alias gos='ssh root@172.25.0.11'
	alias god='ssh root@172.25.0.10'


# 用户
	创建   useradd  wang
    查看用户信息
		id  wang
		grep  wang  /etc/passwd
    删除   
        userdel  wang  只销号，不删除用户主目录
        userdel -r wang  删除用户信息及主目录

## 设置普通用户密码：
	当前是root： passwd  wang
		    然后输入两次密码。

	当前是普通用户： passwd
		输入旧密码，然后输入两次新密码（复杂）
			
			


# 练习：
    创建用户  alibaba
    查看它的信息
    设置密码为 123456


# 切换用户（su，switch user）：
    root -> 普通用户        
        su - 用户名
        su - wang

        从上往下切换，不需要密码验证

    普通用户  ->  root
        su
        输入密码

        从下往上，需要密码验证



server里的 root 账号，密码是 redhat



# 权限：
    ls -l a.txt

    -      rw-        r--       r--

    类型  user权限   group权限   other权限
            u         g           o

    r   read 读权限
    w	write 写权限
    x	execute 执行权限
    -       无权限


## 修改权限的命令   chmod
				
        + - =

        u-w   去除 user 的写权限
        g-r   去除 group 的读权限
        o=---  不给 other 任何权限

    chmod u+x a.txt
    chmod u-x,g+w,o-r a.txt
    chmod u=rwx a.txt

## 数字方式：
    rwx-
    4210

    chmod 666 a.txt
    -rw-rw-rw-


# 练习：
	创建文件  b.txt
	设置它的权限为  -  rwx r-x ---
					

		
命令工作的两种方式：交互式、脚本式。
# Shell 脚本
.sh 后缀的文件，可以直接执行

```
vi hello.sh

#!/bin/bash  
pwd  
cal  
ls	
	
chmod u+x hello.sh

绝对路径  /root/hello.sh
或者 ./hello.sh
			
```
		
下载：[Shell 脚本编程.pdf](http://2hao.cc/download/shell.pdf)

## 》》[欢迎对我的讲课提建议](http://2hao.cc/things/pinglun.php?id=191)