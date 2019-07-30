---
title: vmware-ubuntu
date: 2018-08-02 14:11
---
使用 vmware 虚拟机，安装 ubuntu 系统的流程及可能出现的问题。

<!-- more -->

---

## 安装 ubuntu 系统

    安装 vmware
    下载 ubuntu 的iso镜像
    

在 vmware 里新建虚拟机，选择 自定义(高级)，按默认下一步，选择 稍后安装操作系统。选择 Linux，底下选择 ubuntu，接着选择 安装位置，注意必须输入一个已存在的目录，不然后面会报错。按默认下一步，选择 将虚拟机存储为单个文件。然后下一步，点击 自定义硬件，选择 提前下载好的 iso 镜像。



## 显示屏幕太小的问题

可以通过在VMware里安装“VMware Tool”插件解决，安装步骤记录一下。



1. 更改ISO文件路径



安装VMware Tool需要用到虚拟光驱，加载一个ISO文件，在安装的时候加载的是ubuntu安装文件 “ubuntu-16.04.2-desktop-amd64.iso”，如果不更改这个加载路径，相当于在虚拟机的虚拟光驱里一直存在这个ubuntu的安装“光盘”，无法加载其他的文件，如下图所示：





需要把这个ubuntu光盘弹出，弹出的方法就是更改ISO映像文件的路径。



在VMware菜单栏上选择虚拟机->设置->CD/DVD(SATA)，更改连接里ISO文件的路径，修改为VMware的安装路径下的一个名称为linux.iso的文件，我的路径是“C:\Program Files (x86)\VMware\VMware Workstation”：









2.  加载“VMware Tool”安装文件



在VMware菜单栏上选择 虚拟机->安装 VMware Tools，点击ubuntu左侧列表里的DVD图标，就会出现VMware Tools的安装文件VMwareTools-10.1.6-5214329.tar.gz：









3. 拷贝并解压VMwareTools-10.1.6-5214329.tar.gz



复制VMwareTools-10.1.6-5214329.tar.gz文件到本地目录，如下载文件夹，并解压:





解压出来可以看到有一个vmware-install.pl的文件，这个文件就是安装VMware Tools的脚本文件：







4. 通过终端安装VMware Tools



打开终端（命令行），进入到vmware-install.pl文件所在的目录下（或直接在当前文件夹下右键打开终端），运行命令：sudo perl vmware-install.pl

之后就会出现很多条提示信息，可以直接按回车略过，N个提示信息之后，就会自动安装VMware Tools：







5. 调整虚拟机窗口大小



在VMware菜单栏点击 查看->自动调整大小->自动适应窗口：