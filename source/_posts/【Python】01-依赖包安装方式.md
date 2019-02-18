---
title: 【Python】01-依赖模块安装方式
date: 2019-02-18 19:56:48
tags: [pip]
categories: [Python]
---
- Python依赖模块安装方式
<!-- more -->

--------------------------------

1、使用pip安装.


2、通过安装包手动安装，下载源码文件并解压，在安装文件setup.py路径下执行
如下命令：
    
    python setup.py install --prefix=$HOME/.local

3、通过easy_install安装.

参考链接：
    https://hpc.uni.lu/blog/2016/faq-how-do-i-install-python-packages/
    https://docs.python.org/2.3/inst/search-path.html