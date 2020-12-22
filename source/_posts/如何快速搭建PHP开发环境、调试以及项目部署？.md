---
title: 如何快速搭建PHP开发环境、调试以及项目部署？
tags:
  - php
  - wampserver
originContent: ''
categories:
  - php
toc: false
date: 2020-12-20 22:33:51
---

本篇文章主要讲述如何通过 WampServer 3.1 +  Navicat Premium 15 + Visual Studio 2019 + Php tools for vs 2019，来搭建基本的开发以及调试功能等。

##### WampServer 安装及配置

官方地址：[https://www.wampserver.com](https://https://www.wampserver.com)，下载存在一定的问题，点击“下载”按钮无反应。当然也有解决的方案，但速度异常的缓慢，最终放弃。果断选择[国产神器360软件管理](http://urlqh.cn/mRU8I)，便捷才是真理。
![wampserver  下载.png](http://file.azing.cn/Fm54GjWPlGFKLResE0-zMftMuN3Z)

默认情况下，WampServer 附带最新版本的 Apache、MySQL 和 PHP。注意安装路径中不能带有空格，否则后期会引发一些列怪异的问题。安装后可以看到 bin目录 包含  php、apache 、mysql 这些都是 开发必备的东西。安装完成后，在浏览器中输入http://localhost 看到如下图所示 即表明 已经安装成功。

![无标题-1.png](http://file.azing.cn/FjIJpbBeZ9QfZZQKSrANUkbD75bc)

我们为了避免和IIS 80 端口的冲突 还要改变 apche 服务器的端口设定。在这里我们改为“8080”。

![无标题-2.png](http://file.azing.cn/FjPshG923hefS5GKP3e85LFs-_Is)
打开此文件后对其进行编辑， 搜索 “Listen 0.0.0.0:80” ，“ServerName localhost:80” 修改后如下图所示![无标题-3.png](http://file.azing.cn/FgTO5JuoOXZJI9ulZl0LEPUWb5yK)
修改完毕后保存，并重新启服所有服务。再次输入 http://localhost:8080 进行 验证。

默认情况时wampserver 所带的Mysql 数据库root账户 是没有密码的，我们可以对其进行设置密码。我们这里通过Navicat Premium  数据库可视化管理工具 来设置密码，便捷才是王道。
下载地址：[https://www.navicat.com.cn/download/navicat-premium](https://www.navicat.com.cn/download/navicat-premium)，该软件是收费的，如有需要破解的方法，可联系我。

Navicat Premium 是一套数据库开发工具，让你从单一应用程序中同时连接 MySQL、MariaDB、MongoDB、SQL Server、Oracle、PostgreSQL 和 SQLite 数据库。它与 Amazon RDS、Amazon Aurora、Amazon Redshift、Microsoft Azure、Oracle Cloud、MongoDB Atlas、阿里云、腾讯云和华为云等云数据库兼容。你可以快速轻松地创建、管理和维护数据库。

好了 我们先用无密码登录本地的mysql。密码为空即可。
![无标题-4.png](http://file.azing.cn/Fsp-3eAcjBotuN-kRLJDVBqPgdDh)
登录成功后 我们选择左侧的本地MYSQL 然后点击 横向菜单栏中的“用户”，双击  “root@localhost"即可进行设定密码。
![无标题-5.png](http://file.azing.cn/FkWbHgticBhkDAVRV1o9M1GMVCjU)

由于本人编程入门语言是C#，深受Visual Studio 开发工具的影响，所以市面上的PHP专用开发工具 Phpstorm 、 Zend Stuido 等 使用起来一直未得心应手。所以本篇文章推荐 的开发工具是VS2019+php tools 。（未完待续）

