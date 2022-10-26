---
title: "SFTP: Received message too long"
tags:
  - sftp
  - ssh
  - Server
  - 系统
date: 2014-05-08 11:06:30
category: 系统
---

After a slight modification to `~/.bashrc`, my sftp connection always fails with FileZilla, XFTP, and commandline `sftp`, but Transmit in OS X works fine. 

With verbose mode of command `sftp`, it tells ‘Received message too long’. Carefully checked `~/.bashrc`, found that an `echo` was added for debugging, after remove the `echo` sentence, sftp works perfectly again.

So, if you want your sftp works fine, please be careful with shell config files like .bashrc or .cshrc or so, especially there are `echo` or other messages outputed. 