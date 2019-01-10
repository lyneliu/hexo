---
title: 【Chrome】常见问题
date: 2019-01-10 11:42:25
tags: [Chrome]
categories: [Chrome]
---
- Chrome相关
<!-- more -->

--------------------------------

1、您的管理员已停用更新，导致无法更新最新版本的Chrome

    解决办法:
    Win + R, regedit打开注册表；  
    HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Google\Update，更新UpdateDefault值为1，保存后然后退出；
    重启Chrome。