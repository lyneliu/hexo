---
title: 【Git问题系列】02——SSH
date: 2017-01-27 10:31:09
tags: [Git,ssh]
categories: [Git]
---
- git ssh 配置问题
<!-- more -->

--------------------------------

## 操作
1、生成公钥、私钥：
ssh-keygen -t rsa -C "邮箱地址"
注：
指定保存路径及文件名，可生成多个。

2、多账号（coding、gitee、github等）
Host coding.net
    HostName *.coding.net
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/路径/私钥文件名
Host github.com
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/路径/私钥文件名
Host github.com
    Hostname ssh.github.com
        PreferredAuthentications publickey
    IdentityFile ~/.ssh/person_rsa
    Port 443

3、将公钥添加是ssh的keyChain（该办法好像仅在Mac OS系统中生效）
eval $(ssh-agent)
ssh-add -K ~/.ssh/路径/私钥文件名

说明：
ssh-add 这个命令不是用来永久性的记住你所使用的私钥的。实际上，它的作用只是把你指定的私钥添加到 ssh-agent 所管理的一个
session 当中。而 ssh-agent 是一个用于存储私钥的临时性的 session 服务，也就是说当你重启之后，ssh-agent服务也就重置了。

ssh -T git@github.com -vvv
注：
-vvv 显示debug详情

4、添加公钥至coding、gitee、github等

## 问题
ssh -T git@github.com -vvv
始终报错：

~/.ssh/config文件：
ssh: connect to host github.com port 22: Connection timed out

修改之前的配置文件

Host coding.net
    HostName *.coding.net
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/code_rsa
Host github.com
    Hostname github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/person_rsa

修改之后的配置文件

Host coding.net
    HostName *.coding.net
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/code_rsa
Host github.com
    Hostname ssh.github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/person_rsa
    Port 443

参考链接：
https://www.cnblogs.com/jpfss/p/8094005.html
https://help.github.com/articles/error-permission-denied-publickey/