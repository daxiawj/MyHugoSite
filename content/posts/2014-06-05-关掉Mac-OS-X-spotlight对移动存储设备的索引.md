---
title: 关掉Mac OS X spotlight对移动存储设备的索引
tags:
  - Mac
  - 系统
date: 2014-06-05 14:06:18
category: 系统
---

Mac OS X 默认开启对所有移动存储设备的索引，因此，常常多出来一些 类似：

```
.fseventsd 
.Spotlight-V100 
.TemporaryItems 
.Trashes
```
 这样的文件。而且可能个头会很大。

 禁止 Spotlight 对设备进行索引也比较简单，只要在终端下进入移动设备的主目录，运行：

```
touch .metadata_never_index
```