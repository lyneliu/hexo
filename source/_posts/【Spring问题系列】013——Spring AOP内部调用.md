---
title: 【Spring问题系列】013——Spring AOP内部调用
date: 2017-01-24 14:37:40
tags: [Spring,AOP]
categories: [Spring]
---
- Spring AOP
<!-- more -->

--------------------------------


问题场景：
Spring项目中可以使用AOP对方法添加埋点、日志等信息，但是遇到一个问题是Spring AOP无法内部调用。

原因是本地方法直接调用时是this.method()，未使用代理类。

解决办法：
1、通过self inject的方式（spring4.3以后版本支持）
@Service
public class SomeService {
    private Logger logger = LoggerFactory.getLogger(getClass());

    @Autowired
    private SomeService self;

    public void hello(String someParam) {
        logger.info("---SomeService: hello invoked, param: {}---", someParam);
        self.test();
    }

    @CatMonitor
    public void test() {
        logger.info("---SomeService: test invoked---");
    }
} 

2、直接使用AspectJ方式，因为spring的AOP方式只允许使用于public的方法。


参考链接：
https://www.jianshu.com/p/6534945eb3b5
https://stackoverflow.com/questions/15093894/aspectj-pointcut-for-annotated-private-methods