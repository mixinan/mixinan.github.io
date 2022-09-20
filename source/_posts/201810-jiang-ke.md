---
title: 10月份讲课笔记
date: 2018-10-26 17:30
---
10 月份的讲课笔记，收录于此。内容包含 Linux 命令、HTML、CSS、Shell 编程等。

<!--more-->

# day01

## 互联网“项目”的运作流程：

```

产品部门	
设计部门
	文档（#ffaa08）
开发部门
	前端部门(网站，web)
	后端部门(访问数据库)
	移动端(Android，iOS)
测试部门
运维部门
	上线、保证正常运转、服务器安全、监控(复用)等
市场部门
运营部门

```

服务器：性能、价格、技术门槛比较高，给企业使用的计算机


计算机，由硬件、软件组成。  
硬件：显示器、键盘、鼠标、硬盘……可以触摸到的物理设备。  
软件：可以控制硬件设备的程序。



windows:
	图形化
	鼠标点击
	收费
	闭源（源代码）
	家庭
	客户端
	
Linux:
	字符界面
	键盘
	免费
	开源
	稳定性
	服务器
	企业使用（技术人员）
	
	
	
# 命令

人与人之间的命令：  
进来、坐下、滚……

人与计算机之间的命令：  
poweroff、reboot、cd...



## 命令的格式：

命令   [选项]    [参数]
滚      翻着     大门口



命令  
poweroff

命令    [选项]
ls      -a (all)


命令    [选项]   [参数]
cat      -n       a.txt


命令     [参数]
touch     a.txt

=========================

## 文件

创建
touch a.txt  
touch b.txt c.txt d.txt
	
ls(查看当前目录里的内容)

删除
rm a.txt   (remove)  
rm -f a.txt  (force)  
rm -f b.txt c.txt d.txt
	
	
	
clear 命令，清理当前窗口的字符。
快捷键：ctrl + l （L）

ctrl + u => 清除光标左侧的字符  
ctrl + w => 清除光标左侧的一个单词  
ctrl + c => 中断当前的进程  
上下方向键 => 可以从历史命令里查找




## 文件夹(目录/路径)

创建
mkdir  Jay  
(make directory)  
mkdir a b c 

mkdir  -p  Michael/Thriller/abc  
(parent)缺啥补啥


删除
rm  -r   Michael  
(recursive) 递归的

rm -rf  Michael  
rm -rf  a music movie



### 练习：
创建文件  1.mp3   2.mp3   3.mp3  1.jpg  2.jpg  
创建文件夹   mp3   picture


date    时间  
可以用于记录故障发生的时间


cal    日历  
(calendar)  
cal 2018    显示2018的日历  
cal 08 2018 显示2018年8月份日历  


## 路径

根目录   /  
/root   根目录下有个文件夹，叫root  
/home/abc/music/a.mp3  


**绝对路径**：以根目录/作为开始的路径  
/root

rm /root/1.mp3

**相对路径**：以当前目录作为开始（参照）

rm 1.mp3  
touch a.txt (和 /root/a.txt 功能一样)




cd   切换文件夹  
（change  directory）  
用法：    
    cd  要切换到的路径

cd  /root
cd  /


pwd  显示当前的路径(我在哪儿)  
(print  working  directory)



rm   remove

不明觉厉  
虽然看不明白，但是觉得很厉害。

	
	
Ctrl + c   中断当前进程




显示当前文件夹里的内容
ls  (list)


<hr>

# day02

ls  路径

ls     默认当前所在的文件夹  (list)  
ls  /  查看根目录里面的内容  
ls  /root  
ls  /root/a.txt  


rm /root/a.mp3  
rm a.mp3


选项：  
ls  -a   (all)  
显示所有的内容（包含隐藏文件）


ls  -l  (long)  
显示内容的长格式（详细信息）

-h  human  
ls -lh   以人能够读懂的格式显示  
h和l配合使用，才有效




ls -l  1.mp3  
查看1.mp3文件的详细信息

ls  -l    music  
查看music文件夹“里面”内容的详细信息

ls  -ld   music  
查看music文件夹“本身”的详细信息  
( d =》 directory 文件夹)


cd  ..  
 切换到“上一层”文件夹（父目录）


### 练习：
创建2个文件夹  picture  music  
在 picture 里创建 1.png 2.jpg 3.gif  
在 music 里创建 a.mp3 b.mp4 c.avi  
把两个文件夹的内容通过 ls 显示在屏幕上  
把它们全部删除



tab 自动补全命令  
如果能够直接匹配准确，自动补全  
否则，按两次tab，提示所有相关的内容  




echo  回声  
echo "hello"  
结果：hello  


输出重定向  
\>   覆盖  
ls > a.txt  
echo hello > a.txt

\>>   追加（ 注意：不是书名号 》）  
ls >> a.txt

	

把 hello world 写入 a.txt  
echo “hello world” > a.txt  
echo 123456 >> a.txt

	
	
	
### 练习：
把当前目录里内容的详细信息，写入a.txt  
追加本月的日历到a.txt



查看文本文件内容  
cat  a.txt  
cat  -n   a.txt  显示内容和行号  
(concatinate)

head  a.txt      显示a.txt前10行（开头）  
head  -3  a.txt  显示a.txt前3行

tail  a.txt      显示a.txt后10行（结尾）  
tail  -3  a.txt  显示a.txt后3行



管道   |  
ls | head | tail -2  
把管道前面的结果，输送给后面进行操作  
cat -n a.txt | head | tail -2





查看文件权限  
ls -l a.txt

### 权限  
\-       rw- r-- r--  
类型     权限

类型：  
文件    -  
文件夹  d  
链接    l






权限  
rw-    r--      r--  
user   group    others  
u      g        o


r    read    读  
w    write   写  
x    execute 执行  
\-    无


修改权限  
chmod  

\+   u+x    给user增加执行权限  
\-   o-r    给others取消读权限  
=   u=rwx  给user设置rwx权限

chmod  u+x  a.txt  
chmod  g-w  a.txt  
chmod  o=---  a.txt  

chmod  u+x,g-w,o=---  a.txt  

ls -l a.txt




以“数字”形式修改权限  
rwx-  
4210

chmod 666 a.txt  
rw-  rw-  rw-
	  
	  
### 练习：
新建文件 test.sh  
查看 test.sh 的权限  
修改 test.sh的权限为  
\-   rwx---rw-
		
chmod  706  test.sh
	




## 编辑文件：  vim

用法：  
vim   a.txt  
如果文件已存在，则打开  
如果不存在，创建并打开
	
```	

编辑模式：
	可以修改内容
	在一般模式下，按 i 进入
	(insert)
	按 Esc 键，退出编辑模式
	
一般模式：
	通过vim进入后的状态
	在编辑模式下，按 ESC 
	
命令模式:
	在一般模式下，按英文冒号 :
	可以执行相关命令
	保存        :w  (write)
	退出        :q  (quit)
	保存并退出  :wq (write  quit)
				:x  不推荐使用
	强制退出    :q!
	设置行号    :set nu   显示行号
				:set nonu 不显示行号
	自动缩进    :set ai   缩进
				:set noai 不缩进

```			
				
复制：nyy （n可以是整数，比如2,3,4）  
	从当前行开始，复制n行

粘贴：np   （paste）   
	在当前行下方，粘贴n次

剪切（删除）： ndd  
	从当前行开始，剪切n行

	
	
	
跳转行：  
ngg   跳到第n行  
G     跳到最后一行





ctrl + u  往上翻半页(up)  
ctrl + d  往下翻半页(down)


查找：  
在一般模式下，/ 或 ? 进入查找状态  
输入关键字，按回车，可以查找对应内容  
/ 从上往下找  
? 从下往上找

如果匹配项比较多，按 n 切换下一个(next)  

替换：  
:%s/old/new/g



读取“别的文件”内容，到当前行下方  
:r  1.txt

另存为  
:w  2.txt




ifconfig  查看ip地址  
ifconfig | head -2


远程连接：  
ssh  root@远程机的ip地址  
以root身份远程登录

ssh  -X  root@远程机的ip地址  
支持远程操作图形化界面


<hr>

# day03

文件的复制 cp 

用法：

cp  要复制的内容  要复制到的地方(copy)  
cp  b.txt   /  
cp  b.txt   /c.txt  
cp  -r  music   /

验证有没有复制成功：  
ls   /  
查看 / 根目录里的内容


ctrl + (ctrl shift +) 放大字体  
ctrl -                缩小字体




文件的剪切（移动） mv  (move)  
mv  要移动的文件   要移动到的地方  
mv  b.txt  /home  
mv  b.txt  c.txt

ls  
ls  /home





### tar 打包、展开、压缩、解压    

打包：  
tar   -cvf   test.tar   要打包的内容

选项：  
c (create)  创建一个文档    
v (view)    可视的  
f (file)    文件


打包并压缩：  
tar   -zcvf   test.tar.gz   a.txt  b.txt  c.txt


展开：  
tar   -xvf   test.tar   -C   /home

-C 选项，可以指定要展开到哪儿，后面跟"路径"

展开并解压：  
tar   -zxvf   test.tar.gz




在Linux里，对文件后缀，不做要求  
但是，为了更好和别人协作，命名尽量规范







alias 别名  

临时设置（关闭终端，则失效）：

alias 别名='命令......'  
alias gos='ssh   root@172.25.0.11'  
alias xxxx='ls -l'  

xxxx a.txt


取消别名  
unalias xxxx

xxxx  
报错：命令找不见




通过命令设置的内容，都是临时生效
重启终端，失效
想要永久生效，需要修改配置文件

.bashrc

alias gos="ssh -X root@172.25.0.11"





## 用户相关命令

创建用户  
useradd  Michael

cat   /etc/passwd   查看所有内容  

tail  /etc/passwd  末尾10行  
head  /etc/passwd  开头10行

ls /home



查看用户相关id信息  
id   wang



grep 查找符合条件的行,并显示  
grep   wang   /etc/passwd  
从 /etc/passwd 文件里，找到包含wang的行




删除用户  
userdel  li  
不删除li的用户主目录 /home/li  
rm  -rf  /home/li


userdel  -r  wang  
直接删除wang用户相关的所有内容



不能删除当前登录的用户（不能自杀）










## 修改用户密码：
当前是root，给wang设置密码  
passwd  wang  
如果提示密码太简单，不用理会

当前是普通用户，给自己重置密码  
passwd  
先输入当前的密码，再输入新密码  
密码的复杂度，必须符合系统要求才行



su 切换用户(switch user)  
当前是root，切换到普通用户  
su - wang

当前是普通用户，切换到root管理员  
su  
输入root的密码进行验证











man    ls  
(manual 手册、说明书)  
help   pwd











