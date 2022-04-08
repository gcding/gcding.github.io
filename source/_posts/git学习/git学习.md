---
title: Git学习
date: 2022-04-01 11:21:34
updated: 2022-04-06
tags: 
- git
categories: 
- 开发
description:
---
本博文主要包含Git+GitHub单人仓库极简配置方法，Git多人协同开发主要命令，Git高级用法和自己部署一个Git，目录如下：
- [Git学习资料整理](#git学习资料整理)
- [Git配置](#git配置)
- [Git基础命令](#git基础命令)
- [Git多人协同开发与branch](#git多人协同开发与branch)
- [Git工具（高级）](#git工具高级)
- [自己部署一个Git（高级）](#自己部署一个git高级)
<!-- more -->

## Git学习资料整理
- 书本资料
  - Git学习资料 [Pro Git中文版](http://iissnan.com/progit/)
- 网页资料
  - ……

## Git配置
此时默认Git已经安装完成，可以通过`` git --version ``判断是否安装成功。
下面以GitHub为例进行Git配置.

**1. 用户信息配置**
``` bash
$ git config --global user.name "your_name"
$ git config --global user.email email@email.com
```
如果用了 ``--global`` 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。如果要在某个特定的项目中使用其他名字或者电邮，只要去掉 ``--global`` 选项重新配置即可。

下面有两个可选择的配置，分别是默认选择的文本编辑器和解决合并冲突时使用哪种差异分析工具。
``` bash
#编辑器，可以用vim
$ git config --global core.editor "your_editor"  
#差异分析工具，可以用vimdiff
$ git config --global merge.tool "your_tool"  
# 查看配置信息
git config --list
```

**2. 配置GitHub**
- 进入GitHub设置 [key](https://github.com/settings/keys)的界面；
- 在本地通过 ``ssh-keygen -t rsa -b 4096 -C "email@email.com"`` 命令生成key。
- 点击 New SSH key，输入你想要的Title，然后将上一步生成的key（保存在``~/.ssh/id_rsa.pub``路径下）粘贴在key里面
- 点击 Add SSH key即可。
- 运行 ``ssh -T git@github.com`` 如果输出以下内容即配置成功。
```
Hi ***! You've successfully authenticated, but GitHub does not provide shell access.
```

下面你就可以愉快地使用Git和GitHub进行代码管理啦！


## Git基础命令
通过这些基础命令你就可以使用GitHub对你自己的代码进行Git管理，如果需要高级功能可以看 [Git多人协同开发与branch](#git多人协同开发与branch)，同时对于想要进阶的选手强烈推荐看学习资料中的 [Pro Git中文版](http://iissnan.com/progit/)。

下面开始介绍Git的基础命令。

**1. 创建一个版本库**

``` bash
# 从工作目录中初始化新仓库
$ git init

# 从git仓库中克隆
$ git clone [url] [wanted_project_name(option)]
```

**2. 记录更新到仓库**
``` bash
# 检查当前文件状态
$ git status

# 跟踪并暂存文件
$ git add [file_name]

# 提交文件
$ git commit -m [stat]

# 移除或移动文件
$ git rm [file_name]  # 移除文件
$ git mv [file_from] [file_to]  #移动文件

# 提交文件
$ git push [remote-name] [branch-name]
```

**3. 拉取最新内容到本地**
强烈建议每次修改本地文件的时候运行此命令。
``` bash
$ git pull [remote-name] [branch-name]
```

  

## Git多人协同开发与branch
以web开发为一个简单的例子去理解git的branch，某公司要给一个web主页新加两个页面，web1和web2，然后现在有2个程序猿去写，分别写这两个页面，这些页面是不相关的（也可以是相关的，这样在合并的时候就需要检查冲突），他们就可以新建两个branch分别是branch1，branch2，这样的话就可以直接在原始主页基础上进行修改，同时不影响主页运行，在测试无误后合并即可。

下面是分支中常用的一些操作和命令：
**1. 新建分支和切换**
``` bash
$ git checkout -b [branch_name]
# 以上命令相当于
$ git branch [branch_name]  # 新建分支
$ git checkout [branch_name]  # 切换分支
```

**2. 分支的合并和删除**
``` bash
# 分支的合并
$ git merge [branch_name]
# 分支的删除
$ git branch -d [branch_name]
```

如果在不同的分支中都修改了同一个文件的同一部分，Git 就无法干净地把两者合到一起。
这时候即使merge了，Git 只是作了合并，但没有提交，它会停下来等你解决冲突。
可以通过`` git status ``查看哪里起了冲突，或者使用图形化界面`` git mergetool ``。

**3. 分支的查看**
通过`` git branch -v ``查看各个分支最后一个提交对象的信息。
通过`` git branch --merged ``查看哪些分支已被并入当前分支。
通过`` git branch --no-merged ``查看哪些分支尚未合并。

**4. 远程分支**
通过`` git fetch origin ``来同步远程服务器上的数据到本地。
通过`` git push [remote-name] [branch-name] ``来推送分支到服务器。

**5. 分支的衍合**
暂时用不到还没学习。

## Git工具（高级）
暂时用不到还没学习。

## 自己部署一个Git（高级）
暂时用不到还没学习。