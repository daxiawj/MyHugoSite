---
title: 修改Octopress 列表的indent
date: 2013-12-24 15:58:47
tags: [Octopress, 自定义]
category: 博客
---

Octopress 默认的列表总是抵着页面第一列，看起来实在不美观。其实修改起来很简单，只要简单的将 
sass/custom/_layout.scss 文件中的 : //$indented-lists: true; 改为false 就行了。改完一看，世界清净了……