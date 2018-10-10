---
title: 【Spring问题系列】011——Return only string message from Spring MVC 3 Controller
date: 2017-01-24 14:37:40
tags: [Spring]
categories: [Spring]
---
- Spring MVC
<!-- more -->

--------------------------------


问题场景：spring boot添加自定义静态资源访问，视图是freemarker。

@Configuration
public class CommonConfig implements WebMvcConfigurer {

    /*资源处理器*/
    @Override
    public void addResourceHandlers(ResourceHandlerRegistry registry) {
        registry.addResourceHandler("/js/**").addResourceLocations("/WEB-INF/" + "/js/");
        registry.addResourceHandler("/css/**").addResourceLocations("/WEB-INF/" + "/css/");
    }

}


使用如下代码，刚开始返回ModelAndView，添加自定义静态资源访问后，只返回字符串，经过查看源码发现是配置注解的问题，见参考链接：

@RequestMapping(value = "/index")
@ResponseBody
public String index(){
	return "index";
}


RequestMappingHandlerAdapter :: handleInternal --> RequestMappingHandlerAdapter :: invokeHandlerMethod

--> ServletInvocableHandlerMethod :: invokeAndHandle --> 所有的returnValueHandlers处理HandlerMethodReturnValueHandlerComposite :: handleReturnValue

通过returnType.getParameterType()获取返回值类型，然后匹配处理的handler。


参考链接：
https://stackoverflow.com/questions/7672858/return-only-string-message-from-spring-mvc-3-controller