---
title: win-ubuntu之samba服务配置
date: 2018-05-15 14:02:58
tags:
categories:
---
> 这里简单介绍下samba服务的配置

1. 在ubuntu系统中安装samba工具
```shell
sudo apt install samba
```
2. samba服务器的配置文件在**/etc/samba/smb.conf**, 备份之
```shell
sudo cp /etc/samba/smb.conf  /etc/samba/smb.conf.bak
```

3. 将要共享的文件夹的用户改为指定用户，权限改为**777**
```shell
chown czy:czy  Work
chmod 777 Work
```

4. 将该用户添加进samba数据库
```shell
sudo smbpasswd -a czy
```

5. 编辑**smb.conf**配置文件，添加如下内容
```shell
# Samba share for Windows clients
[Work]
path = /home/czy/Work
available = yes
valid users = czy
read only = no
browseable = yes
public = yes
writable = yes
```
6. 重启samba服务
```shell
sudo /etc/init.d/samba restart
```
7. 在**Windows**系统中使用**win + r**调用运行，输入虚拟机ip地址即可访问共享文件夹
