---
title: Restrict sftp-server concurrent connections
tags:
  - Server
  - sftp
  - Linux
  - 技术
date: 2014-02-19 14:50:57
category: 系统
---

`man sshd_config`:

```
MaxStartups 2
```
~用选项 MaxStartups, Default value is 10.~

补充：这个貌似不是这样的，sigh，sftp 能不能进行限制就真不知道了，哪位高手告诉我一下吧！