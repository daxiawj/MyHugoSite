---
title: su 出现 This account is currently not available
tags:
  - Linux
  - Server
  - su
  - 技术
date: 2014-04-23 21:34:55
category: 技术
---

`su` 切换用户的时候出现 “This account is currently not available” 的提示，尤其是在 `/etc/init.d/` 的文件里面，运行一些服务需要切换到特定的用户，如启动 tomcat 的脚本，需要切换到 www 用户，但是 www 用户在 /etc/passwd 里面的 shell 是 /sbin/nologin，那么在启动的脚本里面:

```
su  www -c /opt/tomcat7/bin/startup.sh
```
这一句就会导致上述的报错。

解决的办法有几种，第一，运行 `vipw` 修改 passwd 文件，将其 shell 项改为 /bin/bash。第二种方法则是修改这条命令，改为：

```
su -s /bin/bash www -c /opt/tomcat7/bin/startup.sh
```
个人更喜欢第二种方案。第一种要修改系统的安全设置，不太建议。