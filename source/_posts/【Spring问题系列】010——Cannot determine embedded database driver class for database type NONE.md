---
title: 【Spring问题系列】010——Cannot determine embedded database driver class for database type NONE
date: 2017-02-02 14:37:40
tags: [Spring]
categories: [Spring]
---
- Spring database
<!-- more -->

--------------------------------


项目中通常会依赖到其他的二方库，在使用二方库的时候可能会导入其他的依赖项。

Spring Boot项目便会遇到如下的问题：
Cannot determine embedded database driver class for database type NONE

spring-boot-autoconfig自动配置模块的问题，解决办法就是排除没有用到的引用：
@EnableAutoConfiguration(exclude = {DataSourceAutoConfiguration.class})

参考链接：
http://blog.didispace.com/spring-boot-disable-autoconfig/