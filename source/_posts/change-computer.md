---
title: 换个电脑写博客
date: 2018-07-13 15:40
---
经过一番折腾，我终于能够在另外一台电脑上更新博客了。

思路：为 github 博客项目新建一个分支，利用它来管理hexo源文件

<!--more-->

---

## 具体操作

安装 Node.js 、Git

安装 hexo，执行命令：

```
npm install -g hexo
```

模块安装，执行命令：

```
npm install
npm install hexo-deployer-git --save
npm install hexo-generator-feed --save
npm install hexo-generator-sitemap --save
```

克隆 gitHub 项目到本地：

```
git clone git@github.com:mixinan/mixinan.github.io.git
```

在克隆到本地的文件夹里，除了.git 文件夹以外，其它的都删掉。不需要再做 hexo init初始化

将原来电脑上使用hexo写博客的整个目录（所有文件）搬过来

里面应该有一个叫.gitignore的文件，如果没有就输入 touch .gitignore，创建一个

.gitignore文件里应该是这些内容 

```
.DS_Store 
Thumbs.db 
db.json 
*.log 
node_modules/ 
public/ 
.deploy*/ 
```


创建并切换到hexo分支 

```
git checkout -b hexo
```

提交复制过来的文件到暂存区

```
git add .
```

提交

```
git commit -m "new branch hexo"
```

推送分支到github

```
git push --set-upstream origin hexo
```

到这里基本上就搞定了，以后再推就可以直接git push了，hexo的操作跟以前一样。

今后无论什么时候想要在其他电脑上面用hexo写博客，就直接把创建的分支克隆下来，npm install安装依赖之后就可以用了。

克隆分支的操作

```
git clone -b hexo git@github.com:mixinan/mixinan.github.io.git
```

因为上面创建的是一个名字叫hexo的分支，所以这里-b后面的是hexo

这样做完了以后，每次写完博客发布之后不要忘了还要git push把源文件推到分支上


---

### 使用hexo报与换行符有关的警告

不同操作系统，所使用的换行符是不一样的，下面罗列一下三大主流操作系统的换行符：

Uinx/Linux采用换行符LF表示下一行（LF：LineFeed，中文意思是换行）；

Dos和Windows采用回车+换行CRLF表示下一行（CRLF：CarriageReturn LineFeed，中文意思是回车换行）；

Mac OS采用回车CR表示下一行（CR：CarriageReturn，中文意思是回车）。



在Git中，可以通过以下命令来显示当前你的Git中采取哪种对待换行符的方式

$ git config core.autocrlf

此命令会有三个输出，“true”，“false”或者“input”

为true时，Git会将你add的所有文件视为文本文件，将结尾的CRLF转换为LF，而checkout时会再将文件的LF格式转为CRLF格式。

为false时，line endings不做任何改变，文本文件保持其原来的样子。

为input时，add时Git会把CRLF转换为LF，而check时仍旧为LF，所以Windows操作系统不建议设置此值。



解决办法：

将core.autocrlf设为 false 即可解决这个问题。注意：如果你和你的伙伴只工作于Windows平台或者Linux平台，没问题；不过如果存在跨平台的话，还是需要考虑一下。

但当 core autocrlf为true时，还有一个需要慎重的地方，当你上传一个二进制文件，Git可能会将二进制文件误以为是文本文件，从而也会修改你的二进制文件，从而产生隐患。


附上修改autocrlf的命令，以改为true为例：

```
$ git config --global core.autocrlf true   
```

可以把上面的参数true，换成false或input
