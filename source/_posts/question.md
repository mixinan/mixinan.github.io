---
title: 博客问题
date: 2018-07-29 09:28
---

这几天博客环境出现问题，有很多话想写，但却无法发布，憋得相当难受。我甚至考虑用回其它博客了。今天来上班的路上，心想还是把问题解决掉吧，正面应对，而不是逃避。刚才搜了一些帖子，解决好了，记录一下。
<!--more--> ​​​​

---

***

报错如下，并且在 cmd 窗口 ping github.com 显示“请求超时”

```

Connection reset by 13.250.177.223 port 22
fatal: The remote end hung up unexpectedly
fatal: The remote end hung up unexpectedly
FATAL Something's wrong. Maybe you can find the solution here: http://hexo.io/docs/troubleshooting.html
Error: Connection reset by 13.250.177.223 port 22
fatal: The remote end hung up unexpectedly
fatal: The remote end hung up unexpectedly

    at ChildProcess.<anonymous> (F:\blog\node_modules\hexo-util\lib\spawn.js:37:17)
    at emitTwo (events.js:126:13)
    at ChildProcess.emit (events.js:214:7)
    at ChildProcess.cp.emit (F:\blog\node_modules\cross-spawn\lib\enoent.js:40:29)
    at maybeClose (internal/child_process.js:925:16)
    at Process.ChildProcess._handle.onexit (internal/child_process.js:209:5)

```

## 解决办法

#### 一、类似以下这种错误

```

FATAL Something's wrong. Maybe you can find the solution here: http://hexo.io/docs/troubleshooting.html
Error: fatal: Not a git repository (or any of the parent directories): .git

    at ChildProcess.<anonymous> (F:\blog\node_modules\hexo-util\lib\spawn.js:37:17)
    at emitTwo (events.js:87:13)
    ……
    (F:\blog\node_modules\hexo-util\lib\enoent.js:40:29)
    at maybeClose (internal/child_process.js:827:16)
    at Socket.<anonymous> (internal/child_process.js:319:11)
    at emitOne (events.js:77:13)
    at Socket.emit (events.js:169:7)
    at Pipe._onclose (net.js:477:12)

```
在网上看到的解决办法（我是照做了，最终解决问题时不知道有没有这一步的作用）：

把 .deploy_git 文件夹手动删除，重新 hexo deploy 一次，让它再自动生成。


#### 二、修改 hosts 文件

路径 C:\Windows\System32\drivers\etc\hosts

用记事本打开，在末尾添加内容：

```

192.30.253.113    github.com
192.30.252.131 github.com
185.31.16.185 github.global.ssl.fastly.net
74.125.237.1 dl-ssl.google.com
173.194.127.200 groups.google.com
192.30.252.131 github.com
185.31.16.185 github.global.ssl.fastly.net
74.125.128.95 ajax.googleapis.com

```

保存（以管理员身份），重新运行 cmd 再ping，可以通。

#### 三、推送时出现 "fatal: The remote end hung up unexpectedly " 错误


原因是推送的文件太大。

解决方案：修改 .git 目录下的 config 文件，在末尾增加如下内容：

```

[http]
postBuffer = 524288000

```

即修改提交缓存大小为500M

---

解决以上问题以后，执行 hexo d 重新推送