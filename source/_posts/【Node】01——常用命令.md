---
title: 【Node】01——常用命令
date: 2018-10-23 13:24:26
tags: [Node,npm]
categories: [Node]
---
- Node & npm 常用命令
<!-- more -->

--------------------------------

1、查看npm基本配置：

	npm config list //查看基本配置
	npm config list -l //查看所有配置


2、全局安装相关配置：

	npm config set prefix "C:/Program Files/nodejs/npm_global"
	npm config set cache "C:/Program Files/nodejs/npm_cache" 

	配置文件目录~/.npmrc内容
	cache=C:/Program Files/nodejs/npm_cache
	prefix=C:\Program Files\nodejs\npm_global
	loglevel=error
	strict-ssl=false
	registry=https://registry.npm.taobao.org/
	
3、使用yarn管理npm依赖

	// 淘宝yarn国内源
	npm i tyarn -g

	注：
	1、如果通过yarn global add安装的组件使用时， command not found，将yarn global bin的path添加至系统环境变量
	（windows 如下路径至PATH：~\AppData\Local\Yarn\config\global\node_modules\.bin）
	2、windows修改环境变量PATH，不重启生效办法：打开一个dos窗口，set PATH=test,然后关闭dos窗口，再重新开启另一个dos窗口，echo %PATH%，这个时候，PATH设置的环境变量已经生效。原理是该操作会使操作系统刷新配置的缓存信息。

参考链接：
https://docs.npmjs.com/cli/npm