---
title: 【MySQL】01——Online DDL
date: 2019-02-12 18:01:09
tags: [MySQL]
categories: [MySQL]
---
- MySQL Online DDL
<!-- more -->

--------------------------------

Online DDL(Data Definition Language):
当生产环境的数据量千万级别，甚至上亿级别的话，添加字段、修改字段等操作无疑会存在巨大的风险和工作量。

工作中惊喜地发现，已有开源工具（gh-ost）支持该项内容。主要操作步骤如下：

    1. 根据原来的表结构执行 alter 语句，新建一个更新表结构之后的表，通常称为幽灵表。对用户不可见。
    2. 把原来表的已有数据 copy 到幽灵表。
    3. 在 copy 的过程中，会有新的数据过来，这些数据要同步到幽灵表，也就是 “Online” 的精髓。
    4. copy 和同步完成后，锁住源表，交换表名，幽灵表替换源表。
    5. 删除源表（可选），完成 online DDL。


参考链接：

    https://github.com/github/gh-ost
    http://mysql.taobao.org/monthly/2018/05/02/
    https://beanbee.me/2018/05/05/ghost-cut-over-steps/