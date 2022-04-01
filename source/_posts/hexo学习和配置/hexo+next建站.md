---
title: hexo + next 建站记录
date: 2021-11-02 19:53:24
updated: 2022-04-01
tags: 
- hexo
- next
categories:
- 开发
description: Hexo建站记录，需要提前配置好GitHub，同时对npm和git使用有一定的了解
comments: true
---



## Hexo
第一次尝试使用Hexo建站，感觉还可以，本条博文留着用来记录我在搭建博客过程中的问题，流程预计如下：
### node + nvm
由于有其他使用node的需要，所以使用了nvm管理node版本，本博客使用的是v16.13.0。
有关NVM安装和使用主要参考:

[NVM安装](https://segmentfault.com/a/1190000018110318)

[NVM使用](https://www.jianshu.com/p/e21e3783304f)

主要使用的命令如下: 
``` bash
$ nvm ls (列出本地所有的node的版本)
$ nvm use v16.13.0 (切换到所需的版本)
```

### GitHub建站
代码已经被托管到GitHub上，其中main（主分支）分支是托管编译后的界面页面，gh-dev分支托管的是源码。
主分支配置已经写好在 _config.yml 中 每次写完只需要运行以下三行命令即可
``` bash
$ hexo clean
$ hexo g
$ hexo d
```
如何想要本地调试的话使用
``` bash
$ hexo s
$ hexo s --debug (debug模式)
```
对于源码部分因为我是两台机器同时写源码，所以由以下操作：
如果是新机器需要下载源码：
``` bash
$ git clone -b "分支名" "仓库名"
```
提交：
``` bash
$ git add "修改的文件名"
$ git commit -m "一些描述"
$ git push origin "分支名"
```
每次修改前都要去GitHub上拉取最新的版本
``` bash
$ git pull origin "分支名"
```

## Next的安装与使用
我自己的主题很简单，推荐的Hexo的NexT主题设置：
- [NexT主题官方文档](https://theme-next.iissnan.com/getting-started.html)
- [NexT主题设置-博客1](https://blog.csdn.net/as480133937/article/details/100138838)