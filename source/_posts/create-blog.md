---
title: 本博客的创建流程
date: 2018-04-20 09:30
---

表达想法、总结新知识、收录问题解决方案、记录繁琐的流程（比如教程类文章）等，**写博客** 都是一个非常好的途径。成熟的博客平台有很多，但还是偶尔能看到有些写作者拥有自己的博客网站。感觉很厉害，我特别好奇他们是怎么做到的...

<!--more-->

---

2016年初我曾用 `阿里云主机 + wordpress` 搭建过个人博客，并更新过一些东西。后来接触到云服务器，我就开始用它鼓捣各种技术了，不惜放弃我的博客。

去年我知道用GitHub可以生成个人主页，特别简单，所以 **王晓洋** 给我推荐搭建博客的方案时，我看他提到了GitHub，以为还是那种形式，就完全没有在意（虽然我回复他说“厉害厉害”）。前几天突然想起来，又去问了他那个框架名字，试着找了几个帖子搭了一遍。因为流程比较多，经过一通折腾把东西搞出来，挺有满足感。网上教程很多，但我还是想梳理并分享一下。

## 需要用到的东西

|技术|描述|
|-|-|
|**markdown**| `编写博文样式要用的语言` |
|**GitHub**| `博客代码和内容的托管平台`|
|**Git**| `发布本地内容到GitHub的工具`|
|**Node.js**| `服务器语言`|
|**hexo**| `著名的博客框架`|



# 基本流程

- [注册GitHub账号，验证邮箱](#a1)
- [下载并安装 Git客户端、Node.js语言包](#a2)
- [关联本地计算机和GitHub账号](#a3)
- [在GitHub创建“username.github.io”仓库](#a4)
- [用 npm 安装 hexo](#a5)
- [在电脑盘里创建 blog 文件夹，下载 hexo 组件](#a6)
- [修改hexo的配置文件 _config.yml](#a7)
- [安装 hexo-deployer-git](#a7)
- [在source/_posts文件夹下创建xx.md文件，编写文章](#a8)
- [使用hexo命令发布博文](#a9)
- [访问 username.github.io](#a10)
- [配置自己的域名](#a11)
- [使用cnpm下载exo-renderer-sass](#a12)


# 详细流程

## 1. <span id="a1">注册GitHub</span>

可以到 https://github.com 注册账号，并验证邮箱(否则无法创建代码仓库)

## 2. <span id="a2">下载并安装 Git客户端、Node.js语言包</span>

自己百度对应官网，下载符合自己电脑版本的软件。按默认“下一步”安装即可。

之后可运行“cmd”进入命令行窗口，执行node -v，npm -v，git --version 验证是否成功

## 3. <span id="a3">关联本地计算机和GitHub账号</span>

可参考 =》 [Git基本使用](https://github.com/mixinan/mygit)

## 4. <span id="a4">在GitHub创建“username.github.io”仓库</span>

需要强调的是，项目的命名格式，必须是 `你的用户名.github.io`


## 5. <span id="a5">用 npm 安装 hexo</span>

运行“cmd”进入命令行窗口，分别执行（需要等待下载）
```
	npm install hexo-cli -g
	npm install hexo --save
```

如果卡住不动，可能是网络原因，Ctrl+c 以后，重新执行命令去下载

## 6. <span id="a6">在电脑盘里创建blog文件夹，下载hexo组件</span>

在你的电脑盘里新建文件夹"blog"(别的名称也行，但别用中文)，进入此文件夹

右键，选择“Git Bash Here”，开启Git终端，执行：
```
	hexo init
```

它可以下载hexo博客框架的组件。下载过程需要等待一两分钟。

同上，如果卡住不动，可能是网络原因，Ctrl+c 以后，重新执行命令去下载

## 7. <span id="a7">修改hexo的配置文件 “_config.yml”</span>

第6步下载完成后，会发现blog文件夹多出一些新文件。 

“_config.yml”是博客框架的配置文件，可以用编辑工具打开，更改对应参数。 

其中，\#site 部分，为博客信息，可以更改作者、语言、个性签名等。

翻到文件末尾，deploy 部分需要修改（**注意**：写下方键值对的时候，冒号后面必须加一个空格），使它跟GitHub代码仓库产生关联：
```
	deploy:
		type: git
		repo: 在GitHub创建的项目地址
		branch: master
```

修改完毕后，重启终端（cmd 或者 Git Bash 都行），执行：

```
	npm install hexo-deployer-git --save
```

它可以下载相关的部署工具


## 8. <span id="a8">在 source/_posts 文件夹下创建 xx.md 文件</span>

每个.md 后缀的文件，相当于是一篇博文。也可以直接使用以下命令生成博文:
```
	hexo new blogName
```
博文基本结构：

第一部分叫 `front-matter`，声明这篇博文的基本信息，比如：

```
	title: 文章标题
	date: 文章的时间
	tags: 文章的标签
	categories: 文章的归类
	description: 文章的概要(在主页显示的片段)
	---
	文章的主体内容
```

中间以三个“-”做分隔，下面写文章的正文。

正文格式，主要是markdown，学习 =》 [markdown基本语法](../markdown)

## 9. <span id="a9">使用 hexo命令 发布博文</span>

```
	最常用的几条命令

	hexo clean
	更改完配置，重新部署之前，清除之前生成的网页文件，以便重新生成
	
	hexo generate （可简写为 hexo g） 
	用md文件生成网页文件

	hexo deployer （可简写为 hexo d）
	把你的更新，发布到GitHub
```

### 在文章中插入图片

- 把配置文件 _config.yml 里的 post_asset_folder 选项设为true
- 执行命令 `npm install hexo-asset-image --save`
	下载安装一个可以上传本地图片的插件
- 运行 `hexo n "xxxx"`生成md博文时，/source/_posts文件夹内除了xxxx.md文件，还有一个同名文件夹
- 把图片复制到xxxx文件夹，然后在xxxx.md中使用markdown格式引入图片，路径为`xxxx/图片名.jpg`



### 在hexo环境下创建草稿

```
	//新建
	$ hexo new draft "new draft"
	会在source/_drafts目录下生成一个new-draft.md文件
	但这个文件不在页面上显示，链接也访问不到
	如果你想把某篇文章移除，可以把它移动到_drafts目录里
```


## 10. <span id="a10">访问 username.github.io</span>

GitHub默认以这个地址为项目首页

## <span id="a11">11. 配置自己的域名</span>

有人可能觉得使用默认的 username.github.io 域名没有逼格。也可以配置自己的域名（类似 blog.xx.com）。以阿里云域名来说，进入域名控制台，添加解析，填写：
```
记录类型：A
主机记录：blog
解析线路：默认
记录值：GitHub的ip地址 192.30.252.153 或 192.30.252.154
```
接着，在hexo的source目录下创建 CNAME 文件，写入 blog.xx.com 即可。

## <span id="a12">12. 使用cnpm下载exo-renderer-sass</span>
npm install cnpm@7.1.0 -g —registry=https://registry.npm.taobao.org
npm config set registry https://registry.npm.taobao.org 
cnpm install hexo-renderer-sass —save 
