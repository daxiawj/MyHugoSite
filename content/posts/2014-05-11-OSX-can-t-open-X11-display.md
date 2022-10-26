---
title: "OSX: can't open X11 display"
tags:
  - OSX
  - X11
  - Server
  - 技术
date: 2014-05-11 10:28:56
category: 博客
---

 由于苹果公司果断放弃了自己维护 X11.app，只能用 XQuatz 来替代。但是在使用 XQuartz 的过程中经常遇到一些问题，比如环境变量的设置问题。今天遇到一个问题就是，自己点击安装的 XQuartz.app 是能正常运行的，但是在终端里面使用 xeys、GrADS 等软件的时候报错：“can’’t open display”。

 大部分情况下，如果正确安装了 XQuartz 但是遇到这个问题的话，很可能是配置文件没能正确地起作用。

If XQuartz were installed and you can launch it, while can’t launch it in terminal, then you may solve it by:

```shell
launchctl unload -w /Library/LaunchAgents/org.macosforge.xquartz.startx.plist
launchctl load -w /Library/LaunchAgents/org.macosforge.xquartz.startx.plist
reboot
```

Then it should work!. 

 问题解决。 