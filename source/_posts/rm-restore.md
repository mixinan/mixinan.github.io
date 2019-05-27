---
title: rm-restore
date: 2019-05-24 11:44:39
tags:
---

lsof 命令的输出信息

```shell
COMMAND   PID  USER  FD  TYPE  DEVICE  SIZE/OFF  NODE    NAME
rsyslogd  406  root  4w  REG   253,1   111276   1052346  /var/log/messages (deleted)
```

各字段意思

```
COMMAND：进程的名称 
PID：进程标识符
USER：进程所有者
FD：文件描述符，应用程序通过文件描述符标识文件
TYPE：文件类型
DEVICE：指定磁盘的名称
SIZE：文件的大小
NODE：索引节点（文件在磁盘上的标识）
NAME：文件名称
```

## 恢复已删除的文件（风险极大，谨慎操作，建议在不用的虚拟机里做！不保证每次都成功，只用于“死马当活马医”的情况）

在 Linux 系统中，每个运行的程序都有一个宿主进程，这些进程之间彼此隔离，以 “/proc/进程号” 来体现

```shell
# 查看进程 PID 为 13067 的进程信息  
ls  -l  /proc/13067 
```

当程序运行时，操作系统会专门开辟一块内存区域，提供给当前进程使用。对于该程序依赖的文件，操作系统会发放一个文件描述符，以便通过它来读写文件数据。

当我们执行 rm -f 删除文件时，其实只是删除了文件的目录索引节点，该文件虽然对于“文件系统”不可见了，但对于“打开它的进程”依然可见，也就是说，还可以通过之前的文件描述符读写文件。

利用此原理，我们可以使用“重定向”的方式来恢复文件。

P.S.

我自己创建了两个文件，通过 "lsof | grep 文件名" 没有数据  
用系统的 /var/log/messages 测试，有数据  
目前不太清楚自己创建的文件为什么没数据，继续研究中...

## 实验步骤

```shell
$ ls -l  /var/log/messages 
-rw------- 1 root root 510377 5月  24 11:10 /var/log/messages

$ rm -f  /var/log/messages

$ lsof | grep /var/log/messages
rsyslogd   406  root  4w  REG   253,1  111276  1052346  /var/log/messages (deleted)

$ lsof | head -1
COMMAND   PID(TID)  USER  FD  TYPE  DEVICE  SIZE/OFF  NODE   NAME

$ ls /proc/406/fd/4    # 路径格式： /proc/PID号/fd/FD号
/proc/406/fd/4

$ cat /proc/406/fd/4
...
大量的日志记录
大量的日志记录
大量的日志记录
...

$ cat /proc/406/fd/4 > /var/log/messages  # 重定向到新的文件

$ ls -l /var/log/messages
```
