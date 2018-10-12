---
title: 【NPM问题系列】01——Update npm and node
date: 2018-10-12 16:36:24
tags: [NPM,Node]
categories: [NPM]
---
- npm & node
<!-- more -->

--------------------------------

1、Linux

    安装n工具
    npm i -g n

    升级node
    n lst
    n latest

    升级npm
    npm i -g npm

2、Windows
    
    安装nvm软件
    nvm #查看命令参数
    nvm list available #查看可选的node版本
    nvm install [version] #安装指定版本的node
    nvm use [version] #使用指定版本的node

    可选方法：
    安装npm-upgrade组件





参考链接：
https://segmentfault.com/a/1190000012873131
https://segmentfault.com/q/1010000015427871/a-1020000015428017
https://github.com/coreybutler/nvm-windows