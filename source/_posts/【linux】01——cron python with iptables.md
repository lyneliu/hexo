---
layout: 【linux】01——cron python with iptables
title: iptables
date: 2019-03-15 10:53:03
tags: [cron, iptables]
categories: [linux]
---
- linux cron python with iptables
<!-- more -->

--------------------------------

1、脚本内容如下test.py：
#!/usr/bin/python
# coding:utf-8
from subprocess import Popen,PIPE 

Popen("iptables -I INPUT -s %s -j DROP" % “,shell=True,bufsize=1024,stdout=PIPE).stdout

2、* * * * * python test.py  #每隔一分钟执行一次

3、问题原因
执行的时候，iptables命令没有生效，这个问题的原因是cron执行脚本的时候没有获取到iptables命令的执行路径.
    The default path is set to PATH=/usr/bin:/bin. If the command you are calling is present in the cron specified path you can either use the absolute path to the command or change the cron $PATH variable. You can’t implicitly append :$PATH as you would do with a normal script.
    The default shell is set to /bin/sh. You can set a different shell by changing the SHELL variable.
    Cron invokes the command from the user’s home directory. The HOME variable can be overridden by settings in the crontab.
    The email notification is sent to the owner of the crontab. To overwrite the default behavior you can use the MAILTO environment variable with a list (comma separated) of all the email addresses you want to receive the email notifications. If MAILTO is defined but empty (MAILTO=""), no mail is sent.

参考链接：

http://www.lpfrx.com/archives/5915/
https://stackoverflow.com/questions/22984318/bash-script-commands-not-working-in-cron
https://linuxize.com/post/scheduling-cron-jobs-with-crontab/
