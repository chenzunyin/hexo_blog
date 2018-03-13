---
title: 使用hexo在github上构建个人静态博客
date: 2018-03-13 10:19:35
tags:
---

## Hexo介绍

Hexo官网地址 : [Hexo官网](https://hexo.io)
> Hexo是一个快速,简洁,高效,基于**nodejs**的博客开发框架,具有如下特点 :
* 超快速度 : Node.js所带来的超快生成速度,让上百个页面在几秒内渲染完成
* 支持Markdown : Hexo支持Github Flavored Markdown 的所有功能,甚至可以整合Octopress的大多数插件
* 一键部署 : 只需要一条指令即可部署到Github Pages,Heroku或者其他网站
* 丰富的插件 : Hexo拥有强大的插件系统,安装插件可以让hexo支持Jade, CoffeeScript

## Hexo安装

1. 首先安装git工具, 安装参考链接 : [git安装](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)
2. 安装node.js, 安装参考链接 : [node.js安装](https://nodejs.org/zh-cn/download/)
3. 安装Hexo : 
```shell
npm install -g hexo
```
4. 查看Hexo版本 :
```shell
hexo v (hexo version)
```
5. 建立一个工程文件夹, 并在文件夹中初始化hexo(**这一步仅需要在工程建立的时候使用**) : 
```shell
hexo init
```
6. 启动Hexo服务器, 打开提示端口 : 
```shell
hexo s (hexo server)
```
7. 如果能够正常浏览页面, 则证明hexo初始化完成

## 创建Github Pages

Github Pages搭建链接如下 : [github pages](https://pages.github.com/)

* 在github上创建一个以username.github.io为名字的仓库(**将username替换成你在github的用户名**)

## 发布项目到Github

* hexo全局配置
编辑文件夹目录下的hexo配置文件*_config.yml*, 找到deploy部分, 设置项目的地址(**username替换成自己的github用户名**)
```shell
deploy:
  type: git
  repo: https://github.com/username/username.github.io
  branch: master
```
* 发布前处理

Hexo是静态博客框架, 静态博客, 只包含html, javascript脚本, css文件的网站, 没有动态的脚本. 虽然我们使用node进行开发, 但是博客发布之后就和node无关了, 发布之前, 我们通过一条命令, 对所有的文章做静态化处理, 就是生成对应的html, javascript, css, 使得发布的文章都是由静态文件组成的.

* 静态化命令
```shell
hexo g (hexo generate)
```
* 编辑后本地查看效果
```shell
hexo s
```
* 部署命令
```shell
hexo d (hexo deploy)
```
* 部署过程中遇到git相关问题, 执行下面的命令
```shell
npm install hexo-deployer-git --save
```
* 对于每次更改文章之后的重新部署, 执行以下命令
```shell
 hexo clean
 hexo g
 hexo d
```
至此, 整个博客的搭建过程完成, 通过访问https://username.github.io查看效果.
