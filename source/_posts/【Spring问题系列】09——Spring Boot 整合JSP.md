---
title: 【Spring问题系列】09——Spring Boot 整合JSP
date: 2017-02-01 14:37:40
tags: [Spring]
categories: [Spring]
---
- Spring JSP
<!-- more -->

--------------------------------


默认的Spring Boot项目不支持JSP，需要添加依赖：
<dependency>
    <groupId>org.apache.tomcat.embed</groupId>
    <artifactId>tomcat-embed-jasper</artifactId>
	<scope>provided</scope>
</dependency>

参考链接：
http://fanlychie.github.io/post/spring-boot-with-jsp.html