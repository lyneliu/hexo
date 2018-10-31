---
title: 【IDEA】02——Java Remote Debug
date: 2018-10-31 18:26:06
tags: [IDEA, Java]
categories: [IDEA]
---
- IDEA Java Remote Debug
<!-- more -->

--------------------------------

1. JVM添加启动参数


        -Xdebug -Xrunjdwp:transport=dt_socket,suspend=n,server=y,address=8090
        
        dt_socket：使用的通信方式
        server：是主动连接调试器还是作为服务器等待调试器连接
        suspend：是否在启动JVM时就暂停，并等待调试器连接
        address：地址和端口，地址可以省略，两者用冒号分隔
        


2. IDEA添加启动项:Host、Port

    ![](/images/idea_remote_jvm.jpg)


3. 非阻塞方式debug生产环境：arthas、jvm-sandbox
https://github.com/alibaba/arthas
https://github.com/alibaba/jvm-sandbox



参考链接：
https://www.cnblogs.com/lailailai/p/4560399.html
https://yq.aliyun.com/articles/654698
https://blog.trifork.com/2014/07/14/how-to-remotely-debug-application-running-on-tomcat-from-within-intellij-idea/


