---
layout: post
title: "git使用—SSH配置"
tagline: "ssh"
description: "git使用"
tags: ["git"]
---
{% include JB/setup %}


First : 安装：ubuntu 下，终端输入命令：


Next : 设置SSH Key


1.  检查是否已经有SSH Key。

　　如果说没有这个目录，就直接看第三步

2.  备份
3.  生成一个新的SSH。


　　之后直接回车，不用填写东西。之后会让你输入密码。然后就生成一个目录.ssh ，里面有两个文件：id_rsa , id_rsa.pub

4.  把这个SSH放到github上。用公钥。先在GitHub上注册一个用户，然后进入account-setting ，把id_rsa.pub的内容复制进去就可以了。

![](http://pic002.cnblogs.com/images/2012/219120/2012042217203449.jpg)

　　然后把id_rsa.pub里的内容复制进去就可以了。

![](http://pic002.cnblogs.com/images/2012/219120/2012042217214059.jpg)

5.  测试OK。输入命令：

	$  ssh -T git@github.com
	
	提示以下信息表示连接成功：
	
	Hi user_name! You've successfully authenticated, but GitHub does not provide shell
	access.




