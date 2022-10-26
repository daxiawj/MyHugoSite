---
title: PYTHONPATH环境变量的设置以及不同Python Distribution的package互用
date: 2015-01-15 15:34:48
tags: [Pyhton, 环境变量, EPD, VTK, Canopy]
category: 系统
---
地学常用的几个Python包/系统CDAT、VTK、Matplotlib、Basemap、netCDF4等编译起来非常麻烦，因此经常有一些厂商/组织将他们打包起来做成一个distribution，方便大家的使用。但是由于这些组织机构性质不同侧重点不同，里面选择的包也不尽相同。为了方便，往往最好、最偷懒的方法就是把他们都安装上，然后混合调用。这就涉及到 PYTHONPATH环境变量的设置了。

这个环境变量设置的就是python程序的搜索路径，在import module的时候，python就是根据这个环境变量的设置来查找的。 在python中可以通过如下语句来查询：

```python
import  sys

```