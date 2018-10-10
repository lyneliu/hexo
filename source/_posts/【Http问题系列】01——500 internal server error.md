---
title: 【Http问题系列】01——500 internal server error
date: 2017-01-23 13:42:56
tags: [Http,500]
categories: [Http]
---
- Http访问500
<!-- more -->

--------------------------------

500 Internal Server Error
该问题的可能性如下:
a、编程语言语法错误，web脚本错误
b、并发高时，因为系统资源限制，而不能打开过多的文件

500通常是服务器返回的状态，但是浏览器访问的情况下，通常要先重启浏览器或清空缓存。

存在缓存的情况下，网页版本信息可能会导致服务器返回该信息。

参考链接：
https://www.interserver.net/tips/kb/troubleshoot-500-internal-server-error/