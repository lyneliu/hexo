---
title: 【Java问题系列】01——Calendar序列化
date: 2017-01-24 14:37:40
tags: [Java, Calendar]
categories: [Java]
---
- Java Calendar序列化问题
<!-- more -->

--------------------------------

项目中序列化数据的时候常常看到/Date(1509292800000+0800)/，这种日期格式通常是C#的序列化时间格式。当C#和Java之间通过Json数据进行通信的时候，会存在时间序列化和反序列化的问题。解决方案可以参考java-common模块中的GsonUtil，通过自定义序列化时间格式的方式解决。

参考链接：
http://yacki.iteye.com/blog/1880619