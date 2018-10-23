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
	

参考链接：
https://docs.npmjs.com/cli/npm