---
layout: post
title: "git使用--SSH配置"
tagline: "ssh"
description: "git使用"
tags: ["git"]
---
{% include JB/setup %}


First : 安装git,不多说


Next : 设置SSH Key


**1.  检查是否已经有SSH Key。**

如果说没有这个目录，就直接看第三步

**2.  备份**

**3.  生成一个新的SSH**

之后直接回车，不用填写东西。之后会让你输入密码。然后就生成一个目录.ssh ，里面有两个文件：id_rsa , id_rsa.pub

**4.  把这个SSH放到github上。**

先在GitHub上注册一个用户，然后进入account-setting ，把id_rsa.pub的内容复制进去就可以了。

<img src="/assets/media/20131117_1.jpg" alt="Pic" class="img-center">

　　然后把id_rsa.pub里的内容复制进去就可以了。

<img src="/assets/media/20131117_2.jpg" alt="Pic" class="img-center">

**5.  测试**

 输入命令：
	
	$ssh -T git@github.com
	
提示以下信息表示连接成功：

	Hi user_name! You've successfully authenticated, but GitHub does not provide shell access.




