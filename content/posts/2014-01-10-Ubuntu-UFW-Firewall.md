---
title: Ubuntu UFW Forewall
date: 2013-01-10 15:58:47
tags: [Firewall, NetWorking, UFW, Ubuntu]
category: 系统
---
用一下几条命令安装并开启 ufw：

```
sudo apt-get install ufw
sudo ufw enable
sudo ufw default reject
```

这样就安装开启了 UFW 防火墙，并默认拒绝一切外来连接请求（reject），显示为未连接，为安全起见，最好将 reject 改为deny。

为开启 SSH 和 WWW 服务，运行：
```
sudo ufw allow ssh/tcp
sudo ufw allow www/tcp
```

同时使用以下命令查询状态：

```
sudo ufw status
```