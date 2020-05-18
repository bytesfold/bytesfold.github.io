---
layout: post
title: "记录windows10安装rabbitmq的坑"
author: "bytesfold"
header-style: text
tags:
  - rabbitmq
---

Rabbitmq的安装过程有点挫折，差点劝退，遂记录帮助后人排忧解难。。。

### 安装vs2013
第一步必须要安装vs2013，否则会出现erlang安装根目录下bin文件夹缺失(缺少bin等文件夹)。  
[从官网下载](https://aka.ms/highdpimfc2013x64cht)  
安装一直下一步即可。  

### 安装erlang
1. 从 [erlang官网](https://www.erlang.org/downloads) 下载安装包。安装路径任意，一直下一步。  
2. 配置环境变量  
    a. 新建变量名ERLANG_HOME，变量值为erlang安装路径(我的默认C:\Program Files\erl-23.0)  
    b. path变量新增%ERLANG_HOME%\bin  
    ![图片](/img/2020/05/18/env_path.gif?raw=true)  


### 安装Rabbitmq
1. 从 [rabbitmq官网](https://www.rabbitmq.com/) 下载安装包  
2. 安装过程的路径千万不能包含空格！默认为C:\program files\rabbitmq，需要更改
3. 打开dos窗口进入，C:\Files\RabbitMQ\rabbitmq_server-3.8.3\sbin目录，输入rabbitmq-plugins enable rabbitmq_management
4. 启动rabbitmq服务，rabbitmq-server.bat start
5. 浏览器输入 http://localhost:15672/#/，用户名guest，密码guest即可登陆。