---
title: 查看linux动态共享库中包含API的命令
date: 2018-10-15 14:59:02
tags:
categories:
---

> 本文主要用于记录查看linux动态共享库中API的命令

1. nm -D lib_name.so

	- 使用**T**做前缀标识的为导出API
	![nm导出API](http://p5l5fsh44.bkt.clouddn.com/nm%E5%AF%BC%E5%87%BAAPI.png)

2. objdump -tT lib_name.so

	- **Base**字段表示的为导出API
	![objdump](http://p5l5fsh44.bkt.clouddn.com/objdump%E5%AF%BC%E5%87%BAAPI.png)

> 查看静态库中API的命令

1. ```nm -g --defined-only libxxx.a```

> 以上
