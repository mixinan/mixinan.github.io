---
title: ftp 服务器操作指南
date: 2019-06-15 07:30
---

给 web 班学员写了一个在 windows 上操作 ftp 服务器的手册

<!-- more -->

---

## 一、环境介绍
- Linux 服务器：用来存储文件，提供 ftp 服务，给用户访问
- windows 电脑：用来上传文件到服务器

为方便操作，windows 电脑需要安装软件：
```
Xshell
一款可以在 Windows 界面下远程控制服务器的软件
```

## 二、需要用到的 Linux 命令

#### 1. 远程连接服务器
```shell
ssh   用户名@ip地址  端口号
```
案例：以 root 身份登录 ip 为 176.4.13.29 的主机，访问端口为 2222（默认为 22，不需要写。如果服务器指定了其它端口，就必须写）
```shell
ssh  root@176.4.13.29  2222
之后输入密码：Taren1（最后一位是数字1）
```

#### 2. 检查 ftp 服务的状态
```shell
//查看状态
systemctl  status  vsftpd

//vsftpd 是 ftp 服务的名字

//启动服务
systemctl start vsftpd

//关闭服务
systemctl stop vsftpd

//重启服务
systemctl restart vsftpd

//把服务设置为开机自启动
systemctl enable vsftpd
```

#### 3. ftp 的默认路径：/var/ftp

第一个 / 表示根目录。在根目录下，有个 var 文件夹，在它内部有个 ftp 文件夹  
把文件传到 ftp 文件夹后，用户就可以通过网络访问了

#### 4. 在服务器里的相关操作

列出文件夹里的内容
```shell
ls              
//后面不写参数，默认列出当前目录下的内容
//list

ls  路径        
//列出指定路径下的内容

ls  -l   路径  
//列出指定路径下内容的详细信息
//long

ls  -lh   路径  
//以人类易读的方式，列出指定路径下内容的详细信息 
//human-readable
```
切换文件夹
```shell
pwd             
//查看当前路径 
//print  working  directory

cd
//后面不写参数的话，默认切换到当前用户的家目录
//change  directory

cd  /var/ftp    
//切换到 /var/ftp 文件夹
```

文件、文件夹的创建、删除
```
touch  a.txt  b.txt
//创建文件 a.txt  b.txt

rm  a.txt
//删除 a.txt
//remove

rm  -f  b.txt
//强制删除文件 b.txt（不再让用户选择是否删除）
//force 强制

mkdir  abc  ddd
//创建文件夹 abc  ddd
//make directory

mkdir  -p   a/b/c
//创建嵌套目录
//parent

rm  -rf    abc/
//强制删除文件夹 abc
//recursive 递归
//使用 rf 选项之前，必须谨慎检查参数
//它威力巨大，使用不当，可能产生无法挽回的损失
```

文件的复制、移动、重命名
```
cp   a.txt  aabb.txt
//把 a.txt 在当前目录下复制一份，命名为 aabb.txt

cp   a.txt  abc/
//把 a.txt 复制到文件夹 abc 下，名字还是 a.txt 不变
//copy

cp   a.txt  abc/abc.txt
//把 a.txt 复制到文件夹 abc 下，命名为 abc.txt

mv   b.txt  abc/
//把 b.txt 移动（剪切）到文件夹 abc 下，名字还是 b.txt 不变
//move

mv   a.txt  abc/aaa.txt
//把 a.txt 移动到文件夹 abc 下，命名为 aaa.txt

mv   a.txt  b.txt
//把 a.txt 重命名为 b.txt
//把 a.txt 移动到当前目录下的 b.txt
//位置没有变，名字变了，相当于重命名。也可以用于文件夹
```

#### 5. 与服务器之间传输文件
1. 在 windows 电脑安装 Xshell 软件
2. ssh 远程连接好服务器，切换到对应目录
3. 在服务器里安装 lrzsz 软件( yum -y install lrzsz )
4. 直接用鼠标把文件从 windows 窗口拖动到 Xshell 界面，上传
5. 在服务器里，执行 sz a.txt，把 a.txt 下载到 windows

#### 6. 用户访问 ftp 服务
如果服务已开启，用户就可以在资源管理器、浏览器通过 ftp://ip地址 来访问
```
ftp://176.4.13.29
//该地址，对应服务器里的 /var/ftp 目录

ftp://176.4.13.29/web1903
//该地址，对应服务器里的 /var/ftp/web1903 目录
```
