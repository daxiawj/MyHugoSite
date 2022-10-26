---
title: Octopress Solarized Light 替换 Dark
date: 2013-12-20 16:58:47
tags: [Octopress, Solarized]
category: 博客
---
Octopress 中默认的代码高亮是程序猿喜闻乐见的 Solarized，不过很遗憾的是默认是 Solarized Dark，像我等心里黑暗的非主流 Coding 技术人员生活已经很暗无天日了，因此还是希望生活中能多一点阳光的，Solarized Light 就很好。幸运的是，Octopress 其实也带了 Solarized Light 配色的，只要简单的修改一行配置就行了：

```
in   : sass/base/_solarized.scss
from : $solarized: dark !default;
to   : $solarized: light !default;
```

Bazinga!