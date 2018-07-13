---
title: 使用VS Code编写C语言程序
date: 2018-06-07 13:49:04
tags: VS_Code
categories: 教程
---
VS Code 是微软开发的编辑器。打开速度很快，支持的功能也非常丰富——有各种各样的插件。本篇介绍如何用它编写C语言程序。

<!--more-->

## 准备工作

先下载 VS Code、MinGW 等软件。
VS Code 不是IDE（集成开发环境）。它只是一个编辑器，所以编译器要自己安装。
MinGW 的默认安装目录是 C:\MinGW，安装完要配置环境变量：把 bin 目录放入 PATH 中。然后在 cmd 窗口执行 gcc -v 测试。

## （一）运行环境搭建

先新建一个用于放置 C语言 源文件的目录，比如 D://workspace
用 VS Code 打开该目录，新建 test.c 文件，编写代码。
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

回到 C语言程序界面，按F5，报错提示，选择“配置任务”，选择第一项，会在”.vscode”文件夹自动生成tasks.json文件，用以下内容代替原有内容：

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

 C语言程序界面，按F5，就可以运行了。

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