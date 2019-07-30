---
title: CSD1706班的数据库
date: 2017-10-09 23:28
---

动手搭建了 C++ 第四阶段课程要用的 Oracle 环境

<!-- more -->

---

## 开启学生电脑的 telnet客户端 功能

开始-控制面板-程序和功能-打开或关闭 Windows 功能-勾选“Telnet客户端”

在虚拟机左侧栏，右键系统镜像名称，选择网络适配器（Network Adapter），选择右侧“桥接模式（Bridged）”

如果无法选择：

关机，选择虚拟机菜单栏“编辑（Edit）”-Virtual Network Editor-把VMnet0设置为“桥接模式”。如果不能设置，选择左下角“恢复默认”，然后Add Network.

在终端窗口输入：telnet 服务器ip地址
1. 会显示 Connected to ip...
2. 等待几秒钟，会让输入账号密码（服务器主机的开机账号密码, 分别为tarena, 123456）, 登录到远程主机
3. 登录数据库，输入：sqlplus  system/123456

---

大家好，

我在中心的一台 windows 电脑里装好了 oracle，执行群里的 sql 脚本，布置好了数据。作为服务器。

在其它电脑可用两种方式操作数据库：

方式一：在 windows 系统的 cmd 窗口，或者 ubuntu 的终端窗口，通过 telnet 远程登录的方式；

方式二：在 windows 系统里用 sqldeveloper 软件。

我们的学生电脑系统是 windows，虚拟机里运行 ubuntu，可以满足咱们教学需要吧，是不是只要能操作数据就可以？
