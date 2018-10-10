---
title: 【Spring问题系列】012——localhost cookie not being set
date: 2017-02-05 14:37:40
tags: [Spring,cookie]
categories: [Spring]
---
- Spring Cookie
<!-- more -->

--------------------------------


问题场景：通过SSO单点认证系统，登陆用户信息后，始终无法获取到cookie信息，以致本地调试过程中，项目后台始终无法获取登陆cookie执行后续操作。


解决办法：
在/etc/hosts文件中添加路径映射
127.0.0.1  xxx.com

http://sso.xxx.com?BackUrl=http://xxx.com/index

参考链接：
https://stackoverflow.com/questions/7346919/chrome-localhost-cookie-not-being-set
https://stackoverflow.com/questions/1134290/cookies-on-localhost-with-explicit-domain
