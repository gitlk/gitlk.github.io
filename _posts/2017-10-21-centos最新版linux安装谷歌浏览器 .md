---
layout: post
description: centos最新版linux安装谷歌浏览器完整攻略，超详细
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

~~~~~~~

		[root@localhost lk]# wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
		--2017-10-21 10:42:02--  https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
		正在解析主机 dl.google.com (dl.google.com)... 203.208.51.69, 203.208.51.67, 203.208.51.66, ...
		正在连接 dl.google.com (dl.google.com)|203.208.51.69|:443... 已连接。
		已发出 HTTP 请求，正在等待回应... 200 OK
		长度：49091606 (47M) [application/x-rpm]
		正在保存至: “google-chrome-stable_current_x86_64.rpm”

		100%[======================================>] 49,091,606   722KB/s 用时 70s    

		2017-10-21 10:43:13 (681 KB/s) - 已保存 “google-chrome-stable_current_x86_64.rpm” [49091606/49091606])

		[root@localhost lk]# ls
		demotest   Downloads                                Pictures   Videos
		Desktop    google-chrome-stable_current_x86_64.rpm  Public     桌面
		Documents  Music                                    Templates
		[root@localhost lk]# chmod 755 google-chrome-stable_current_x86_64.rpm 
		[root@localhost lk]# ls
		demotest   Downloads                                Pictures   Videos
		Desktop    google-chrome-stable_current_x86_64.rpm  Public     桌面
		Documents  Music                                    Templates
		[root@localhost lk]# rpm -ivh google-chrome-stable_current_x86_64.rpm 
		警告：google-chrome-stable_current_x86_64.rpm: 头V4 DSA/SHA1 Signature, 密钥 ID 7fac5991: NOKEY
		错误：依赖检测失败：
			/usr/bin/lsb_release 被 google-chrome-stable-62.0.3202.62-1.x86_64 需要
			libXss.so.1()(64bit) 被 google-chrome-stable-62.0.3202.62-1.x86_64 需要
		[root@localhost lk]# su
		[root@localhost lk]# sudo yum localinstall google-chrome-stable_current_x86_64.rpm
		已加载插件：fastestmirror, langpacks
		正在检查 google-chrome-stable_current_x86_64.rpm: google-chrome-stable-62.0.3202.62-1.x86_64
		google-chrome-stable_current_x86_64.rpm 将被安装
		正在解决依赖关系
		--> 正在检查事务
		---> 软件包 google-chrome-stable.x86_64.0.62.0.3202.62-1 将被 安装
		--> 正在处理依赖关系 /usr/bin/lsb_release，它被软件包 google-chrome-stable-62.0.3202.62-1.x86_64 需要
		base                                                     | 3.6 kB     00:00     
		extras                                                   | 3.4 kB     00:00     
		updates                                                  | 3.4 kB     00:00     
		updates/7/x86_64/primary_db                                | 2.9 MB   00:21     
		Loading mirror speeds from cached hostfile
		 * base: mirrors.aliyun.com
		 * extras: mirrors.aliyun.com
		 * updates: ftp.yz.yamagata-u.ac.jp
		--> 正在处理依赖关系 libXss.so.1()(64bit)，它被软件包 google-chrome-stable-62.0.3202.62-1.x86_64 需要
		--> 正在检查事务
		---> 软件包 libXScrnSaver.x86_64.0.1.2.2-6.1.el7 将被 安装
		---> 软件包 redhat-lsb-core.x86_64.0.4.1-27.el7.centos.1 将被 安装
		--> 正在处理依赖关系 redhat-lsb-submod-security(x86-64) = 4.1-27.el7.centos.1，它被软件包 redhat-lsb-core-4.1-27.el7.centos.1.x86_64 需要
		--> 正在处理依赖关系 spax，它被软件包 redhat-lsb-core-4.1-27.el7.centos.1.x86_64 需要
		--> 正在处理依赖关系 /usr/bin/patch，它被软件包 redhat-lsb-core-4.1-27.el7.centos.1.x86_64 需要
		--> 正在处理依赖关系 /usr/bin/m4，它被软件包 redhat-lsb-core-4.1-27.el7.centos.1.x86_64 需要
		--> 正在检查事务
		---> 软件包 m4.x86_64.0.1.4.16-10.el7 将被 安装
		---> 软件包 patch.x86_64.0.2.7.1-8.el7 将被 安装
		---> 软件包 redhat-lsb-submod-security.x86_64.0.4.1-27.el7.centos.1 将被 安装
		---> 软件包 spax.x86_64.0.1.5.2-13.el7 将被 安装
		--> 解决依赖关系完成

		依赖关系解决

		================================================================================
		 Package                    架构   版本                源                  大小
		================================================================================
		正在安装:
		 google-chrome-stable       x86_64 62.0.3202.62-1      /google-chrome-stable_current_x86_64
																				  176 M
		为依赖而安装:
		 libXScrnSaver              x86_64 1.2.2-6.1.el7       base                24 k
		 m4                         x86_64 1.4.16-10.el7       base               256 k
		 patch                      x86_64 2.7.1-8.el7         base               110 k
		 redhat-lsb-core            x86_64 4.1-27.el7.centos.1 base                38 k
		 redhat-lsb-submod-security x86_64 4.1-27.el7.centos.1 base                15 k
		 spax                       x86_64 1.5.2-13.el7        base               260 k

		事务概要
		================================================================================
		安装  1 软件包 (+6 依赖软件包)

		总计：176 M
		总下载量：702 k
		安装大小：177 M
		Is this ok [y/d/N]: y
		Downloading packages:
		(1/6): libXScrnSaver-1.2.2-6.1.el7.x86_64.rpm              |  24 kB   00:01     
		(2/6): redhat-lsb-core-4.1-27.el7.centos.1.x86_64.rpm      |  38 kB   00:00     
		(3/6): m4-1.4.16-10.el7.x86_64.rpm                         | 256 kB   00:02     
		(4/6): redhat-lsb-submod-security-4.1-27.el7.centos.1.x86_ |  15 kB   00:00     
		(5/6): patch-2.7.1-8.el7.x86_64.rpm                        | 110 kB   00:02     
		(6/6): spax-1.5.2-13.el7.x86_64.rpm                        | 260 kB   00:00     
		--------------------------------------------------------------------------------
		总计                                               232 kB/s | 702 kB  00:03     
		Running transaction check
		Running transaction test
		Transaction test succeeded
		Running transaction
		  正在安装    : patch-2.7.1-8.el7.x86_64                                    1/7 
		  正在安装    : m4-1.4.16-10.el7.x86_64                                     2/7 
		  正在安装    : spax-1.5.2-13.el7.x86_64                                    3/7 
		  正在安装    : libXScrnSaver-1.2.2-6.1.el7.x86_64                          4/7 
		  正在安装    : redhat-lsb-submod-security-4.1-27.el7.centos.1.x86_64       5/7 
		  正在安装    : redhat-lsb-core-4.1-27.el7.centos.1.x86_64                  6/7 
		  正在安装    : google-chrome-stable-62.0.3202.62-1.x86_64                  7/7 
		Redirecting to /bin/systemctl start atd.service
		  验证中      : redhat-lsb-submod-security-4.1-27.el7.centos.1.x86_64       1/7 
		  验证中      : google-chrome-stable-62.0.3202.62-1.x86_64                  2/7 
		  验证中      : libXScrnSaver-1.2.2-6.1.el7.x86_64                          3/7 
		  验证中      : spax-1.5.2-13.el7.x86_64                                    4/7 
		  验证中      : redhat-lsb-core-4.1-27.el7.centos.1.x86_64                  5/7 
		  验证中      : m4-1.4.16-10.el7.x86_64                                     6/7 
		  验证中      : patch-2.7.1-8.el7.x86_64                                    7/7 

		已安装:
		  google-chrome-stable.x86_64 0:62.0.3202.62-1                                  

		作为依赖被安装:
		  libXScrnSaver.x86_64 0:1.2.2-6.1.el7                                          
		  m4.x86_64 0:1.4.16-10.el7                                                     
		  patch.x86_64 0:2.7.1-8.el7                                                    
		  redhat-lsb-core.x86_64 0:4.1-27.el7.centos.1                                  
		  redhat-lsb-submod-security.x86_64 0:4.1-27.el7.centos.1                       
		  spax.x86_64 0:1.5.2-13.el7                                                    

		完毕！
		[root@localhost lk]# ls
		demotest   Downloads                                Pictures   Videos
		Desktop    google-chrome-stable_current_x86_64.rpm  Public     桌面
		Documents  Music                                    Templates
		[root@localhost lk]# rpm -ivh google-chrome-stable_current_x86_64.rpm 
		准备中...                          ################################# [100%]
			软件包 google-chrome-stable-62.0.3202.62-1.x86_64 已经安装

~~~~~~~