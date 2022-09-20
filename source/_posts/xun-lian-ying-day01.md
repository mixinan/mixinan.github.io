---
title: 训练营day01
date: 2018-08-24 17:31
---
一些Linux基础入门。希望大家都能有所收获。

<!-- more -->

---

# 上午

电脑登录：

选择“未列出”  
用户：root  
密码：Taren1（是 yi，不是 L）



```
互联网项目的开发流程：
	需求分析、调研
	产品部门（交互、用户体验）
	设计部门（图、文档）
	开发部门
		前端（网站）
		后端
		移动端（安卓、iOS）
		数据库
	测试部门
	云计算部门（Linux系统运维、安全、数据库、自动化、集群）
	市场部门
    运营部门
```

普通用户（看热闹，只管使用）  
技术人员（看门道，思考实现思路）

---
```
Linux系统
	开源世界、免费
	字符窗口（终端）
	键盘输入
	技术人员（企业）
	稳定（最重要）

Windows系统
	微软、收费、闭源
	鼠标点击
	图形化界面
	小白、男女老少、娱乐
```


# Linux 命令

	生活中的命令：
        站住、吃饭、闭嘴

	Linux 系统里的命令：
        poweroff（关机）、rm（删除）、mv（移动）

	clear  清空屏幕（ctrl + l）
	tab  自动补全命令
    上下方向键  切换历史命令

## 命令格式

		命令   [选项]   [参数]
---
		命令  
            ls   
	
    	命令    参数
		touch  a.txt
	
    	命令    选项
		ls   -a
	
    	命令    选项     参数
		rm   -f   a.txt



## 几个常用的命令
	ls	显示当前目录里的内容（list）
	ls  -a   显示所有的内容（all 包含隐藏文件）
	ls  -l   显示内容的长格式（long，详细信息）
	ls  -h   显示用户易读的格式（15245）
	ls  -lh  选项是可以组合的(-l -h)

    D:/Jay/qilixiang/
    D:/Jay/qilixiang/abc.mp3

    ls  参数（路径）


    路径：
        绝对路径（从根目录 / 开始）  /root/Jay/
            根目录  /   是Linux系统的最外层的文件夹
            /root
            
        相对路径（以当前目录作为开始）  ls  Jay/


        ~   当前用户的主目录
        ls ~

        ..  上层目录（父目录）
        ls  ../..
        ls  ..

        .   当前目录
        ls .


    pwd   显示当前的路径
            print  working  directory


    cd    切换路径
        change directory
        cd  要切换的目标路径

        cd  /
        pwd
        ls

        cd  ~
        pwd

        cd ..
        pwd

        cd ../..
        pwd				




# 文件相关的命令
    创建  
        touch a.txt
        touch b.txt c.txt d.txt

    删除（remove）
        rm  a.txt
        rm  b.txt c.txt
        rm  -f  强制删除，不提示（否则输入 yes 才能删）


# 几种执行次序

A && B  
仅当 A 执行成功，才执行 B  

A || B  
仅当 A 执行失败，才执行 B  

A ; B   
当 A 执行完，执行 B



# 从输入域名到看到网页的流程
www.baidu.com 域名   
把域名转为 ip 地址（比如：47.93.6.163）  
服务端收到客户端发来的请求  
把对应的资源（首页的代码）发给客户端  
客户端收到资源，然后解析，显示给用户


# 下午

	echo 回声
		echo hello
		结果: hello

	输出重定向   
        >    覆盖输入
        >>  追加输入

		echo hello > a.txt
		echo world >> a.txt

	cat  查看文本文件的内容
		cat a.txt

	head  查看文本文件的前10行内容（默认查看10行）
		head  a.txt
		head -5 a.txt（查看头5行）
			
	tail  查看文本文件的后10行内容（默认查看10行）
		tail  a.txt
		tail -5 a.txt（查看末尾5行）

	less   分页查看
            less a.txt


    date   查看时间
        date +%Y
        date +%m
        date +%d
        date +%Y-%m-%d
        date +%F

    cal    查看日历（calendar）

    
    管道  |
        把一个命令的执行结果，通过“管道”传递给后面的命令，去处理
        ls | head
        cal | tail -2




## 与“文件夹”相关的命令
    创建  mkdir  Jay
        make directory
        
        mkdir  Eminum  Jaz

    删除
        rm -rf music/  遍历删除（格杀无论）



# 练习
    创建两个目录，分别是 mp3 和 txt
    进入 mp3 目录，创建a.mp3 b.mp3 c.mp3
    进入 txt 目录，创建a.txt b.txt c.txt

    把 mp3 里的内容，显示在窗口里
    把 txt 里的内容，显示在窗口里
				

用户主目录（家目录）的地址

	root  /root
	普通用户  /home/Jay

		

通配符   *   ?   []   {}

    *  可以匹配任意长度的字符
    ?  只能匹配一位字符
    
    rm  -rf  *.txt
    a.txt   dasfddsa.txt   ddd.txt

    rm -rf  ?.txt
    a.txt   b.txt
    
    rm -rf  a?.txt

    删除所有名字以a结尾的文件(有后缀)    rm -rf  *a.*

			
    []  表示一个匹配的范围
    ls  [7-9].mp3
    7.mp3 8.mp3 9.mp3

    {}  表示从一组选项里选择包含的内容，用逗号(,)隔开
    ls {1,4}.mp3
    1.mp3  4.mp3





## 文件的复制、移动、压缩、解压
			
    cp  复制文件到某个路径(copy)
        cp  a.txt  /home/b.txt
        cp  a.txt  /home/

        cp  文件1  文件2  文件3...  目标路径
				

    mv  移动文件到某个路径（move）
        mv  a.txt  test/
        mv  a.txt  test/b.txt
        mv  a.txt  b.txt


# 练习
创建 5 个 .txt 文件，3个 .png 文件，2个 .gif 文件  
把它们分门别类地存放在 txt、pic、gif 文件夹里



	tar  压缩、解压、打包、展开

    打包  
        tar -cvf  a.tar  music/ txt/
        
        -c  创建一个文档 create
        -v  显示打包的内容 view
        -f  后面紧接着最后的压缩文件名 file
    
    展开
        tar -xvf  a.tar

    打包并压缩	
        tar  -zcvf  a.tar.gz  music/  txt/
    
    解压并展开
        tar  -zxvf  a.tar.gz


    比较“压缩”与“不压缩”的文件大小
	ls  -lh  a.tar  a.tar.gz


Linux 系统里，一切皆文件。对后缀没有要求。
				


# vi 的使用
    vi 是 Linux 系统里的编辑工具。
    
    用法：
        vi a.txt
        如果 a.txt 存在，则打开。否则，先创建，再打开。

## vi 的三种模式

    编辑（插入）模式   
        在普通模式下，按 i 键(insert)进入
        按 Esc 键，退出编辑模式，进入普通模式

    普通（一般）模式
        通过 vi 命令进入后，就是普通模式，无法编辑、保存

    命令模式 
        在普通模式下，按英文的冒号(:)进入命令模式
        :w	  保存（write）
        :q    退出（quit）				
        :wq   保存并退出（write + quit）
            :x  保存并退出（不建议使用）
        :q!   强制退出
		
# 练习
创建文件 hello.txt，写入一句古诗，保存并退出。把诗句显示在窗口里。
