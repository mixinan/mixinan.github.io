---
title: VSCode相关
date: 2018-06-07 13:49
---

VSCode 是微软开发的编辑器。打开速度很快，支持的功能也丰富——有各种插件。本篇介绍如何使用。

<!--more-->

---

# 快捷方式

## 查找文件
按 `ctrl + p` 可以查找文件。它的查找功能相当灵活，不区分大小写，甚至字母不相连也能匹配，比如搜“ab”关键字，候选项里也会出现名字是“acdbe.txt”的文件。

## 查找命令
按功能键 F1 也可以查找，与它功能一样的，还有个组合键 `ctrl + shift + p` ，但它们是`查找命令`，不是查找文件。不过不要紧，在弹出的命令搜索框里，删掉左侧的 > 符号，就会变成`查找文件`的功能了。

## 拖动内容
alt + 上下方向键

## 复制内容到它上(下)方
shift + alt + 上(下)方向键

## 复制当前行
ctrl + c

## 剪切(删除)当前行
ctrl + x

## 选中当前行
ctrl + L

## 注释当前行
ctrl + /

## 在当前行下方插入一行
ctrl + 回车 



# 编写C语言程序

## 准备工作

先下载 VSCode、MinGW 等软件。
VSCode 不是IDE（集成开发环境）。它只是一个编辑器，所以编译器要自己安装。
MinGW 的默认安装目录是 C:\MinGW，安装完要配置环境变量：把 bin 目录放入 PATH 中。然后在 cmd 窗口执行 gcc  -v 测试。


## 运行环境搭建

先新建一个用于放置 C语言 源文件的目录，比如 D://workspace  
用 VSCode 打开该目录，新建 test.c 文件，编写代码。  
按F5，提示选择环境，选C++gdb，会自动生成”.vscode”文件夹，并弹出 launch.json 文件，用以下内容代替：

```
{
   "version": "0.2.0",
    "configurations": [
        {
            "name": "(gdb) Launch", 
            "type": "cppdbg", 
            "request": "launch",
            "targetArchitecture": "x86",
            "program": "${file}.exe", 
            "miDebuggerPath": "c:\\MinGW\\bin\\gdb.exe", // 与本机MinGw的路径对应
            "args": [], 
            "stopAtEntry": false, 
            "cwd": "${workspaceRoot}",
            "externalConsole": true, 
            "preLaunchTask": "g++"
        }
    ]
}
```

回到 C 语言程序界面，按F5，报错提示，选择“配置任务”，选择第一项，会在”.vscode”文件夹自动生成tasks.json文件，用以下内容代替原有内容：

```
{
    "version": "0.1.0",
    "command": "g++",
    "isShellCommand": true,
    "showOutput": "always",
    "args": ["-g","${file}","-o","${file}.exe"],
    "problemMatcher": {
        "owner": "cpp",
        "fileLocation": ["relative", "${workspaceRoot}"],
        "pattern": {
            "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
            "file": 1,
            "line": 2,
            "column": 3,
            "severity": 4,
            "message": 5
        }
    }
}
```

 C 语言程序界面，按 F5，就可以运行了。

 ## 乱码问题

在”.vscode”文件夹下新建head.h头文件，并填入以下代码：

```
#include <stdlib.h>
static void before(void) __attribute__((constructor));
static void after(void) __attribute__((destructor));
static void middle(void);
static void before(){
    system("chcp 65001"); //切换字符集
    system("cls");
}
static void after(){
    system("echo.");
    system("pause");
}
```

修改tasks.json，用以下内容替换:

```
{
    "version": "0.1.0",
    "command": "g++",
    "isShellCommand": true,
    "showOutput": "always",
    "args": ["-g","${file}","-include","${workspaceRoot}\\.vscode\\head.h","-o","${file}.exe"], //修改的是这一行，添加了-include命令，预编译头文件
    "problemMatcher": {
        "owner": "cpp",
        "fileLocation": ["relative", "${workspaceRoot}"],
        "pattern": {
            "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
            "file": 1,
            "line": 2,
            "column": 3,
            "severity": 4,
            "message": 5
        }
    }
}
```






