---
title: 普通用户使用sudo免密
date: 2018-05-21 20:42:40
tags:
categories: linux相关
---
> 用户在执行sudo指令时不用输入密码

1. 执行如下指令：
```shell
sudo vim /etc/sudoers
```

2. 在最后添加如下语句（**假设用户名为czy**）:
```shell
%czy    ALL=(ALL)  NOPASSWD:ALL
```

3. 执行**:wq!**退出，即可到达目的

ps: 今天又重新装了一个ubuntu虚拟机，apt 安装工具的时候比较慢，所以不要懒惰，去/etc/apt/sources.list文件中把源切到国内，推荐使用阿里源
