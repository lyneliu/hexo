---
title: 【Hexo】01——Comment Theme
date: 2018-10-18 10:08:04
tags: [Hexo, Valine]
categories: [Hexo]
---

- Hexo 评论系统

<!-- more -->

--------------------------------

1、注册leancloud
<https://leancloud.cn/>

2、创建应用后，获取App ID和App Key
控制台 -> 创建应用 -> 设置 -> 应用Key

3、修改Yelee配置文件

    _config.yml添加valine配置信息：
    valine:
     appid:  #Leancloud应用的appId
     appkey:  #Leancloud应用的appKey
     verify: false #验证码
     notify: false #评论回复提醒
     avatar: mm #评论列表头像样式：''/mm/identicon/monsterid/wavatar/retro/hide
     placeholder: Just go go #评论框占位符


    layout/_partial/article.ejs添加处理逻辑：
    <% } else if (theme.valine.on) { %>
        <%- partial('comments/valine', {
          key: post.slug,
          title: post.title,
          url: config.url+url_for(post.path)
        }) %>


    创建comment文件layout/_partial/post/valine.ejs
    <section id='comments' style='margin: 2em; padding: 2em; background: rgba(255, 255, 255, 0.5)'>
      <div id='vcomment' class='comment'></div>
      <script src='//cdn1.lncld.net/static/js/3.0.4/av-min.js'></script>
      <script src='<%- theme.CDN.valine %>'></script>
      <script>
        new Valine({
          el: '#vcomment',
          notify: '<%= theme.valine.notify %>',
          verify: '<%= theme.valine.verify %>',
          app_id: '<%= theme.valine.appid %>',
          app_key: '<%= theme.valine.appkey %>',
          placeholder: '<%= theme.valine.placeholder %>',
          avatar: '<%= theme.valine.avatar %>'
        });
      </script>
    </section>

注：
尝试了Gitalk后还是放弃了，最终采取的方案是valine.

参考链接：
<https://valine.js.org/>
<https://blog.wangriyu.wang/2018/03-valine.html>
