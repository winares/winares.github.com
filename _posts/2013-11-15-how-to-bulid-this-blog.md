---
layout: post
title: "BLOG搭建手册"
tagline: "how to bulid this blog"
description: "搭建博客的心得"
tags: ["blog"]
categories: ["blog"]
---
{% include JB/setup %}

这篇博文主要是总结自己在github上搭建blog的过程，因为在这其中还是有不少的心得和收获。
另外也是希望可以帮助那些想在github上建blog的同学少走一点弯路。

我想编过程序的人对github一定都或多或少有些了解。它号称程序员的Facebook，有着极高的人气，许多重要的项目都托管在上面。
但是对于一个新手来说，看到一大堆源码，只会让人头晕脑涨，不知何处入手。他希望看到的是，一个简明易懂的网页，说明每一步应该怎么做。
因此，github就设计了Pages功能，允许用户自定义项目首页，用来替代默认的源码列表。所以，github Pages可以被认为是用户编写的、托管在github上的静态网页，而我们所搭建的blog正是基于github pages的静态网页。
github提供模板，允许站内生成网页，但也允许用户自己编写网页，然后上传。有意思的是，这种上传并不是单纯的上传，而是会经过Jekyll程序的再处理。

Jekyll（"杰克尔"）是一个静态站点生成器，它会根据网页源码生成静态文件。它提供了模板、变量、插件等功能，所以实际上可以用来编写整个网站。
所以构建blog的思路到这里就很明显了。你先在本地编写符合Jekyll规范的网站源码，然后上传到github，由github生成并托管整个网站。

下面就要是介绍一下blog搭建的一些具体步骤，主要是一些命令行的操作，还是比较容易上手的。
如果你对ruby完全没有了解，仅仅对html有初步的了解，这都没有关系，只要你懂一点点linux命令就行，
例如ls,cd,mkdir,cp,ssh命令等(不懂也没有关系),不懂请用到时Google。一切软件的下载见后面的软件汇总，具体步骤如下：


### 安装ruby环境
因为Jekyll是利用Ruby实现的，因此我们需要涉及到一些关于Ruby的东西，可能你对Ruby不是很了解，但这没关系，因为我们只是简单的使用一下而已。
这里我们使用RailsInstaller，它提供了一种轻松便捷的方式来创建Ruby on Rails应用。
目前的RailsInstaller提供了如下功能：
Rails、
Ruby、
SLQite、
Git、
DevKit。

安装RailInstaller，因为它集成了一系列的软件，因此使用起来也会比较方便，在安装过程中尽量使用默认的设置，这会为后面的工作节省很多精力。

### 配置Git
在RailInstaller安装完成界面(程序安装的最后一步)，提示是否进行Git环境的配置，默认情况是选择是，选择“确定”就行。
如果你之前配置好了git，这边会自动检测到你的相关信息，如git帐号，邮箱，key，以及会显示一些软件信息如：ruby，git版本之类的，
并且自动cd到目录 /c/Sites下面，今后你只要将博客放在该目录下就行。
在开始菜单里找到RailsInstaller –> Git Bash，执行它，就打开了下面的命令窗口，以后的配置操作都是在这个窗口下进行的，
首先测试是否git可以正常连接，如果不能，请回到第一步进行Git的配置(该命令在运行，开始->程序->RailsInstaller –> Git Bash 控制台下执行(该控制台我主要是为配置环境用))。
	ssh -T git@github.com
提示以下信息表示连接成功：

	$  ssh -T git@github.com
	Hi user_name! You've successfully authenticated, but GitHub does not provide shell
	access.
	
### 安装Jekyll和相关包
首先更改一个镜像文件的地址：

	gem sources --remove http://rubygems.org/
	gem sources -a http://ruby.taobao.org/
	
然后用gem sources -l看看现在源列表
	
	$ gem sources -l
	*** CURRENT SOURCES ***
	http://ruby.taobao.org/
	http://ruby.taobao.org/

安装jekyll

	gem install jekyll


### 建立github pages
在github.com上创建代码库，登录到自己的Github账户，选择New repository,比如新建一个名如：user_name.github.com的代码库，
然后在代码库页，选择右侧的下拉列表框：Settings，就会对该项目进行修改，找到Github Pages一栏，点击右侧Automatic Page Generator按钮，
生成网页，稍等片刻系统就会将网页生成好。待生成好后，克隆自己的代码库
	git clone git@github.com:user_name/user_name.github.com.git
执行以后，git会把存放在github上的代码库文件下载到本地的，生成名为user_name.github.com的目录。删掉.git目录，并且将网站文件放置在该文件夹下。

在这里你可以使用jekyll已有的模板，或者参考别人的模板进行编辑修改。

### 发布博文
打开Git Bash控制台，我们将在这儿继续博文的推送工作。
编辑博文，并以文件后缀.md命名，博文开头格式如下

	---
	layout: post
	title: 编程心得
	category: blog
	description: blablaaaaaaaaaaa
	---
	正文。。。。。
	
	
文件命名方式如下:
	2013-12-12-first-page.md
请确保你的文件被保存为不含 BOM 的 UTF-8(若不是将会出错，可以使用notepad++ 来进行格式转换) 
使用git命令推送到git服务器上，先加入本地库中
	git add .
	git commit -m"new blog“
	git push
如果你在其他机器上修改过，那么先要执行 git pull否则会提示： non-fast-forward错误

	C:\Sites\username.github.com>git push
	To git@github.com:username/username.github.com.git
	! [rejected]        master -> master (non-fast-forward)
	error: failed to push some refs to 'git@github.com:username/username.github.com.git'
	To prevent you from losing history, non-fast-forward updates were rejected
	Merge the remote changes (e.g. 'git pull') before pushing again.  See the
	'Note about fast-forwards' section of 'git push --help' for details.
	
	
### 访问你的BLOG
等待一段时间，github就会为你生成网页。用浏览器打开网址：user_name.github.com，到此blog的搭建工作就算基本完成。

在整个过程中，要熟悉对git命令的使用，这其实是个基本功，熟能生巧。


软件汇总：
- RailInstall下载链接：[RailInstall-1.9.3-p448][rail]

[rail]: http://inwake.com/ypchen/files/upload/railsinstaller-2.0.1.exe


