---
layout: post
title: "ShadowSocks—有墙不怕,科学上网"
tagline: "ShadowSocks"
description: "科学上网"
tags: ["架构"]
---
{% include JB/setup %}


<img src="/assets/media/20150517_0.png" alt="Pic" class="img-center">

　　除去广为人知、人见人爱的[VPN](http://www.i-vpn.net)，其实还有十八般兵器存在于科学上网界，其中ShadowSocks可以说是其中一把功能齐全的瑞士军刀。服务器端提供了各种版本，如Python、Nodejs、Go、C libev等等，安装配置过程极其简单。而用户端则可以在windows、mac、iOS和android上轻松运行，很好很强大。


　　PS：此程序[开源](https://github.com/clowwindy/shadowsocks)，感谢作者[@clowwindy](https://twitter.com/clowwindy)为主的所有程序员。
官网地址[www.shadowsocks.org](http://shadowsocks.org/en/index.html)
注意那个.com并不是官网，而是上面的.org


#### Shadowsocks是什么？

码农对于shadowsocks应该不陌生，而一般普通网民可能知之甚少。shadowsocks实质上也是一种socks5代理服务，类似于ssh代理。与vpn的全局代理不同，shadowsocks仅针对浏览器代理，不能代理应用软件，比如youtube、twitter客户端软件。如果把vpn比喻为一把屠龙刀，那么shadowsocks就是一把瑞士军刀，轻巧方便，功能却非常强大。

#### 喜欢上shadowsocks的理由

很多时候，我们仅仅只是需要上一下google，收个gmail邮件，或者打开某个网站瞄一眼看看有无更新。这种情况下，vpn可以做到吗，可以，但是很麻烦，连个vpn，qq也得掉一次线，有时候还连半天连不上。而通过ss的话呢，后台运行一个小程序，然后浏览器点击切换一下SS的网络，就可以了。不用的时候，再切回来。这也就是其轻巧的地方。

#### 如何使用shadowsocks？

首先，你需要有一个shadowsocks账号，这里有[免费shadowsocks账号](http://www.ishadowsocks.com)（会换密码）。

#### windows平台

1.下载一个shadowsocks的客户端程序

[ Win7及以下百度网盘下载地址](http://pan.baidu.com/s/1o6KF4vw)

[ Win8及以上百度网盘下载地址](http://pan.baidu.com/s/1gdvlsif)

不需要安装，解压就可以用。

2.运行解压后文件夹中的“shadowsocks.exe”

3.右下角找到程序图标，右键图标，“服务器”--“编辑服务器”，如下图，设置好shadowsocks的账号信息，点确定；

<img src="/assets/media/20150517_1.png" alt="Pic" class="img-center">

4.再次右键程序图标，勾选“启用系统代理”。

<img src="/assets/media/20150517_2.png" alt="Pic" class="img-center">

5.接下来，可以在chrome中直接打开youtube试试，测试OK，没问题。

<img src="/assets/media/20150517_3.png" alt="Pic" class="img-center">

Tips：

*   原GUI版本需要配合浏览器插件才能使用，新版无需浏览器插件配合，直接启用系统代理，配置好后就可以上网了。
*   系统代理模式一项，可以选择“PAC模式”和“全局模式”。PAC模式即需要代理的网站才代理，不需要代理的则通过本地网络访问，可以理解为，访问国内网站还是和你原来的网络一样，只有访问部分国外网站，才通过shadowsocks服务器。全局模式则是访问所有网站都通过shadowsocks服务器。
*   如何关闭shadowsocks呢？shadowsocks程序直接关闭就行了。

#### Mac OS X平台

还是先下载mac下的客户端程序（[百度网盘下载](http://pan.baidu.com/s/1gdIRTnl)），后面的过程和win是一样的，设置好以后，打开浏览器上网就O了，新版支持海外和全局的选项，一般默认选海外，基本感觉不到Wall的存在。

#### iOS平台

直接在appstore搜索下载shadowsocks（[safari直接进入下载](https://itunes.apple.com/cn/app/shadowsocks/id665729974?mt=8)），app打开后就是一个浏览器，内置了公共服务器，可以直接输入网址打开youtube了。当然，有时候公共服务器会出现不稳定的情况，这时可以设置自己的服务器使用，设置方法和windows一样。相比Android版，iOS版只支持浏览器，有点弱爆了的感觉。iOS上还是VPN更方便

前往[iOS上那些好用的VPN应用](http://www.jianshu.com/p/90e18e1e40a7)

<img src="/assets/media/20150517_4.png" alt="Pic" class="img-center">

#### Android平台

安卓下的软件名称为“**影梭**”（[GooglePlay下载](https://play.google.com/store/apps/details?id=com.github.shadowsocks)  [百度网盘](http://pan.baidu.com/s/1kTEacbt)），下载后无需root，设置好服务器和帐号信息后即可直接使用。

与iOS版本不同，android版是以VPN的方式运行的，也就是说不仅支持浏览器，而且支持其他App，简直好用到没朋友。

<img src="/assets/media/20150517_5.png" alt="Pic" class="img-center">


[（整理自网络）][post]

[post]: http://www.jianshu.com/p/08ba65d1f91a

