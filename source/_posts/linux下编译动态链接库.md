---
title: linux下编译动态链接库
date: 2018-10-15 21:03:19
tags:
categories:
---

> 本文档用于记录linux下编译动态链接库

1. 假设编译库的源文件为**example.c**, 使用如下命令进行编译

	```shell
	gcc example.c -fPIC -shared -o libexample.so
	```

	- 注意动态库的命名格式为**lib + 库名称 + .so**的格式

2. 编译参数解析

	- **shared**该选项指定生成动态链接库, 不用该标志外部程序无法链接, 相当于一个可执行文件

	- **fPIC**表示编译成位置独立的代码, 不用此选项的话编译后的代码是位置相关的, 所以动态载入时是通过代码拷贝的方式来满足不同进程的需要, 不能达到真正代码段共享的目的

3. 将编译的库添加到动态链接库路径中

	- 编辑.bashrc文件下的LD_LIBRARY_PATH环境变量, 将库的存放路径添加到该路径中

	```shell
	export LD_LIBRARY_PATH=/path_to_share_lib:$LD_LIBRARY_PATH
	```
