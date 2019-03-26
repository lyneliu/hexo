---
title: 【Java面试】01——Java基础（待整理）
date: 2019-03-20T09:06:57.081Z
tags: [Java]
categories: [Java]
---

- Java基础

<!-- more -->

--------------------------------

- 面向对象

    面向对象（Object Oriented Programming），简称OOP，把**对象**作为程序的基本单元，一个对象包含了属性（数据）和方法（操作数据的函数）。

    Note： OOP（面向对象）、OP（面向过程）、AOP（面向切面）

- 封装、继承、多态

- 抽象和接口

- Object方法及使用？

- 拆箱、装箱？

- 字符串不变性

- equals()方法、hashCode()方法的区别？

- Java异常类的层次结构？异常处理注意事项？

- Java集合？

- 线程安全的集合？

- Set和List的区别？

- ArrayList和LinkedList区别？

- static初始化流程？

- HashMap、HashTable区别？

- HashMap、ConcurrentMap实现？

- Java IO

- BIO、NIO（Reactor模式）、AIO（Proactor模式）区别及实现？
  
    思考：ServerSocket.accept()是线程安全的么？
    <https://segmentfault.com/a/1190000012976683>

- final、finally、finalize区别？

- 为什么要序列化？

        序列化就是一种用来处理对象流的机制，所谓对象流也就是将对象的内容进行流化(I/O)，
        我们可以对流化后的对象进行读写操作，也可将流化后的对象传输于网络之间(注：要想
        将对象传输于网络必须进行流化)！在对对象流进行读写操作时会引发一些问题（比如编
        码格式问题），而序列化机制可以避免并解决这些问题。

- 序列化的原理？ Jackson、Fastjson、Gson区别？

      1. 序列化原理
      2. Jsckson、Fastjson、Gson区别
          - jackson：反射+反射缓存、良好的stream支持、高效的内存管理
          - fastjson：
              jvm虚拟机：通过ASM库运行时生成parser字节码，支持的field不能超过200个。参考：FastJson使用ASM反序列化。
              android虚拟机：反射的方式。
          - gson：反射+反射缓存、支持部分stream、内存性能较差（gc问题）

      3. dubbo、sofarpc序列化实现？

- Java异常处理注意事项及常见异常？

- Java是值传递还是引用传递？

- 四元运算符？

    var row.status == 0 ? '未支付' : (row.status == 1 ? '已支付' : '作废')"

- fail-fast和fail-safe？

参考链接：
<https://www.jianshu.com/p/50b085b4920e>
<https://mp.weixin.qq.com/s/5s6PdPaHBIhDcuTYzVDwlQ>
<https://cloud.tencent.com/developer/article/1154744>
<http://www.voidcn.com/article/p-umtlwhuz-re.html>
<https://blog.csdn.net/anxpp/article/details/51512200>