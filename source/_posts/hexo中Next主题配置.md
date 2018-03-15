---
title: hexo中Next主题配置
date: 2018-03-15 11:25:05
tags:
  - Next, hexo
categories: 教程
---
# Next主题配置
> 设置Next主题主要是为了改变hexo默认主题显示的样式, 以一种更清新, 愉悦的方式来展示博客的内容

## 安装Next
关于Next主题的更多介绍, 请参考: [Next官网](http://theme-next.iissnan.com/)

使用git工具获取next源代码: [Next git仓库](https://github.com/iissnan/hexo-theme-next)

## 启用Next主题
在站点配置文件**_config.yml**中, 找到**theme**字段, 将内容改为**next**

## 风格(Scheme)设定
> Scheme是Next提供的一种特性, 借助于Scheme, Next为你提供多种不同的外观. 同时, 几乎所有的配置都可以在Scheme之间共用, 目前Next支持三种Scheme 
* Muse -- 默认Scheme, 这是Next最初的版本, 黑白主调, 大量留白
* Mist -- Muse的紧凑版, 整洁有序的单栏外观
* Pisces -- 双栏Scheme, 小家碧玉的清新
* Gemini -- 横向拉伸版的Pisces

Scheme的切换通过更改主题配置文件, 搜索**scheme**关键字, 将需要启动的那一行前面的**#**去掉, 将当前使用的那一行前面加上**#**

## 语言设定
编辑站点配置文件**_config.yml**, 将**language**字段设置成你需要的语言

|语言|设定格式|
|:----|:----|
|简体中文|`language: zh-Hans`|
|English|`language: en`|


## 设置菜单
> 菜单配置包括三个部分
* 菜单项(名称和链接)
* 菜单项的显示文本
* 菜单项对应图标

> Next 使用的是[Font Awesome](https://fontawesome.com/)提供的图标, Font Awesome提供了600+图标, 可以满足绝大多数的场景, 同时无需担心在Retina屏幕图标显示模糊的问题

编辑主题配置文件**_config.yml**, 修改如下内容
* 设定菜单内容, 对应的字段是**menu**, 菜单内容的设置格式是: `item name: link`. 其中**item name**是一个名称, 这个名称并不是直接显示在页面上, 而是用于匹配图标以及翻译

Next默认的菜单项有(标注**!**的项目表示需要手动创建这个页面)

|键值|设定值|显示文本(**简体中文**)|
|:-|:-|:-|
|home|`home: /`|主页|
|archives|`archives: /archives`|归档|
|categories|`categories: /categories`|分类!|
|tags|`tags: /tags`|标签!|
|about|`about: /about`|关于!|
|commonweal|`commonweal: /404`|公益404!|
|schedule|`schedule: /schedule`|日程表!|
|sitemap|`sitemap: /sitemap.xml`|站点地图!|

* 设置菜单项的显示文本
第一步中设置的菜单名称并不直接用于界面上的显示, Hexo在生成的时候将使用这个名称查找对应的翻译语言, 并提取显示文本. 这些翻译文本放置在Next主题目录下的language/{language}.yml
> 其中**language**为你所选用的语言

以简体中文为例, 若你需要再添加一个菜单项, 比如something, 那么就需要修改简体中文对应的翻译文件language/zh-Hans.yml, 在menu字段下添加项something: 有料(在主题配置文件**menu**字段下添加something即可使用该菜单项)

> 以上是主题的基本配置介绍
