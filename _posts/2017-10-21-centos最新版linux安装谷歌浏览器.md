---
layout: post
description: 'centos最新版linux安装谷歌浏览器完整攻略，超详细'
categories: linux
tags: ['linux','centos','谷歌浏览器']
date:'2017-10-21'
---


第一步下载安装包：

~~~

wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm 

~~~

第二步：

超级管理员登陆: su

查看安装包权限: ls

修改安装包权限：（如果是绿色则不需要修改）

~~~

chmod 755 google-chrome-stable_current_x86_64.rpm 

~~~

第三步：解决依赖关系

~~~

sudo yum localinstall google-chrome-stable_current_x86_64.rpm

~~~

第四步：执行安装

~~~

 rpm -ivh google-chrome-stable_current_x86_64.rpm 

~~~



# 完整过程代码及结果：

