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

4、npm vs yarn
|	npm 命令	|	Yarn 命令 | 备注 |
|:--------|:--------|:--------|
|	npm install |	yarn install |	安装所有依赖包（依据package.json中的依赖配置参数） |
|	(N/A)	|	yarn install --flat | 单版本模式 |
|	(N/A)	|	yarn install --har| 生成har文件，记录安装时网络请求性能 |
|	(N/A)	|	yarn install --no-lockfile| 不读写lockfile方式 |
|	(N/A)	|	yarn install --pure-lockfile| 不生成yarn.lock文件 |
|	npm install [package]	|	(N/A)| 安装依赖 |
|	npm install --save [package]	|	yarn add [package]|	添加生产模式依赖到项目	|
|	npm install --save-dev [package]	|	yarn add [package] [--dev/-D]| 添加开发模式的依赖 |
|	(N/A)	|	yarn add [package] [--peer/-P] | 对等模式添加依赖，发布/分享项目时的依赖 |
|	npm install --save-optional [package]	|	yarn add [package] [--optional/-O]| 添加可选依赖包 |
|	npm install --save-exact [package]	|	yarn add [package] [--exact/-E]| 精准添加某版本的包 |
|	(N/A)	|	yarn add [package] [--tilde/-T]| 添加同一次版本的包，如指定版本为1.2.3，可接受1.2.x的其他版本，但不接受1.3.x的版本 |
|	npm install --global [package]	|	yarn global add [package] | 添加全局包 |
|	npm rebuild	|	yarn install --force| 重建 |
|	npm uninstall [package]	|	(N/A)| 删除本地依赖包 |
|	npm uninstall --save [package]	|	yarn remove [package]| 删除正式依赖包|
|	npm uninstall --save-dev [package]	|	yarn remove [package]| 删除开发依赖包 |
|	npm uninstall --save-optional [package]	|	yarn remove [package] | 删除可选依赖包 |
|	npm cache clean	|	yarn cache clean| 清除缓存 |
|	rm -rf node_modules && npm install	|	yarn upgrade | 更新包管理器自身 |

参考链接：
https://docs.npmjs.com/cli/npm
http://docs.shellway.cn/learning-yarn/#/