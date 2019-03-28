---
title: 【Java面试】04——Tomcat（待整理）
date: 2019-03-20T09:12:53.237Z
tags: [Java, Tomcat]
categories: [Java]
---

- Tomcat

<!-- more -->

--------------------------------

- Servlet？

    Servlet是Web服务器核心工作的抽象，在Java中是一个Interface. 在Servlet规范中的描述为Servlet是基于Java技术的Web组件，托管于容器中。
    A servlet is a small Java program that runs within a Web server. Servlets receive and respond to requests from Web clients, usually across HTTP, the HyperText Transfer Protocol.

- Servlet生命周期？

    三个主要方法：
    1. init()初始化截断：
    2. service()处理请求截断：
    3. destroy()终止阶段：

- Servlet是线程安全的吗？
    不是，一个servlet实现类通常是单实例多线程处理请求，多个线程处理请求的情况下，全局变量及静态变量会被修改，所以是非线程安全的。

- Servlet是单例吗？
    不一定是，在一个ServeltName情况下是的。在多个ServletName匹配到一个Servlet类时，该Servlet不是单例。

- Tomcat启动流程？
<http://www.fanyilun.me/2016/10/10/Tomcat%E7%9A%84%E5%90%AF%E5%8A%A8%E5%88%86%E6%9E%90/>

参考链接：
<https://www.bysocket.com/archives/518/%E5%9B%BE%E8%A7%A3-%E6%B7%B1%E5%85%A5%E6%B5%85%E5%87%BA-javaweb%EF%BC%9Aservlet%E5%BF%85%E4%BC%9A%E5%BF%85%E7%9F%A5>