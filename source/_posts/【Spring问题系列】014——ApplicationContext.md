---
title: 【Spring问题系列】14——ApplicationContext
date: 2018-10-11 10:48:00
tags: [Spring,context]
categories: [Spring]
---
- Spring ApplicationContext

<!-- more -->

--------------------------------

Spring Boot项目中获取ApplicationContext的方法：
1、方法一：

public class SpringContext implements ServletContextListener {
    private static ApplicationContext springContext;
    public SpringContext() {
        super();
    }
    public void contextInitialized(ServletContextEvent event) {
        WebApplicationContext context= WebApplicationContextUtils.getWebApplicationContext(event.getServletContext());
        setContext(context);
    }
    public void contextDestroyed(ServletContextEvent event) {
    }
    public static ApplicationContext context() {
        return springContext;
    }    
    public static void setContext(ApplicationContext context){
        springContext=context;
    }
}

2、方法二（Spring Boot）：

@SpringBootApplication
public class Application extends SpringBootServletInitializer {   
    private static ApplicationContext context;
    @Override
    protected SpringApplicationBuilder configure(SpringApplicationBuilder application) {
        ApplicationStarterInitial.initial();
        return application.sources(Application.class);
    }
    public static void main(String[] args) {
        context = new SpringApplicationBuilder(Application.class).run(args);
    }
    public static ApplicationContext getContext(){
        return context;
    }
}
3、方法三：

@Autowired
private ApplicationContext applicationContext;

参考链接：
https://stackoverflow.com/questions/4914012/how-to-inject-applicationcontext-itself