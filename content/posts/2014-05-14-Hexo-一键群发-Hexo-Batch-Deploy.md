---
title: Hexo 一键群发_Hexo Batch Deploy
tags:
  - Blog
  - Git
  - Hexo
  - 博客架构
date: 2014-05-14 17:31:28
category: 博客
---

Hexo 架构的博客可以很方便地发布到 Github 等，而且因为是纯 md 文件，同时转化为全静态的文件，因此可以非常方便地在不同站点间同步。 这不，原本架构在 Github 上的博客，但是 Github 毕竟速度比较慢一些，所以同时还架在 Gitcafe 上了，这样国内访问就快多了，要是有自己的域名加上 DNSpod 的一些设置，可以让国内国外的访客分别访问最快的服务器。 原本是写了个 cron 脚本自动 rsync 到不同的目录的，现在才发现 Hexo 本身就有一键群发的功能，只需要在 `_config.yml` 文件里面配置好多个网站 git 地址就好了：
For Batch deploy with Hexo, just configure `_config.yml` :

```yml
# Deployment
## Docs: http://zespia.tw/hexo/docs/deployment.html
deploy:
  type: git
  repo:
    github: https://github.com/daxiawj/daxiawj.github.io.git
    gitcafe: https://gitcafe.com/daxiawj/daxiawj.git,gitcafe-pages
    bitbucket: https://daxiawj@bitbucket.org/daxiawj/daxiawj.bitbucket.org.git
```
 其中，`gitcafe: https://gitcafe.com/daxiawj/daxiawj.git,gitcafe-pages` 基本格式是 ` 标签: repo,[branch]`，`[branch]` 默认是 `master`。

 当然，还可以添加 rsync 等同步方式，以同步到自建的 apache 或者 nginx 静态站点上，此处不再赘述。