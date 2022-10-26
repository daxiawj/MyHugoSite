---
title: 轻松并发执行作业--GNU Parallel
tags:
  - GNU
  - parallel
  - 并发
  - shell
  - 技术
date: 2014-03-19 14:50:57
category: 技术
---

 有的时候要执行一些很快但是却很多重复的操作，例如修改所有普通文件的权限，修改一下权限本是很快的操作，但是文件很多的话操作起来就慢了。再比如要下载很多 http 下很小的文件，下载一个文件如果只需要三秒，但是每一个文件从建立连接、进行对话然后开始下载直到下载完成，中间会浪费很多时间，可能浪费的比实际下载所需的时间还多。

 因此，如果能有一个方法并发进行，那么效率会高得多。以前在 Shell 里面也有一些 tricks 来进行这方面的操作，但是总是因为繁琐而容易出错。

 现在 FSF 开发的 GNU parallel 一出，问题迎刃而解。例如修改所有子目录下面普通文件的权限：

```
find ./ -type f | parallel -m chmod mode
```

 批量修改文件夹权限 

```
find ./ -type d | parallel -m chmod mode
```

 再如有一个顺序任务的脚本 batch.sh

```
wget url1
wget url2
wget url3
wget url4
wget url5
wget url6
```

 那么你就可以并行运行如下：

```
parallel -j+0 < batch.txt 
## This runs as many instance of the commands in batch.txt
## in parallel as you have cores (-j+0) and schedules the
## jobs in an efficient manner
```

 当然，你也可以直接 使用一个 parallel 脚本（shebang）

```
#!/usr/bin/parallel 
blahblah
```

 要安装它很简单，比如:

*   Ubuntu: `sudo apt-get install parallel`
*   Fedora: `yum install parallel`
*   Mac OSX: `brew install parallel`
*   Others: ` 源码编译（下载, tar xjvf parallel....tar.bz2;  ./configure; make install）`

 至于详细功能，那就需要： `man parallel` 了 