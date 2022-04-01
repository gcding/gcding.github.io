---
title: hexo写博客
date: 2022-04-01 11:21:34
updated: 2022-04-01
tags: 
- hexo
categories: 
- 开发
description: 点击详情查看如何新建第一个自己的博客
---

Hexo 写博客可以理解为写遵从Hexo博客规范的Markdown（其实也没啥规范），下面以写此博客为例简述如何在配置好hexo和next的情况下写博客。

## 新建文档
新建文档，名字为：hexo写博客：
``` bash
$ hexo new "hexo写博客"
```
上述命令会在``~/source/_posts``下创建一个``hexo写博客.md``文件，你可以自由移动到``_post``下你自己创建的文件夹下面。

我本人是使用VsCode的，所以直接打开即可编辑，你也可以用自己觉得舒服的编辑器进行编辑。

## 文档格式
文档格式在~/scaffolds/post.md里面定义，以下是我的定义方式：
``` bash
---
title: {{ title }}
date: {{ date }}
tags:
categories: 
---
```

在生成文档后我们就可以在``---``后面愉快的写博客内容了（Markdown语法）。

## 生成文件
为了避免不必要的错误，在生成静态文件前，强烈建议先运行以下命令：
``` bash
$ hexo clean
```

然后按照之前本地调试的方法进行调试，调试无误后提交即可。

## 快速流程

### 生成新博客

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### 本地调试运行server

``` bash
$ hexo server
$ hexo server --debug (debug 模式)
```

More info: [Server](https://hexo.io/docs/server.html)

### 生成静态文件

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### 部署

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)
