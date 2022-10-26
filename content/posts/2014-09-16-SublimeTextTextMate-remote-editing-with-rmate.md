---
title: SublimeText/TextMate remote editing with rmate
date: 2014-09-16 11:20:25
tags: [Sublime Text, TextMate, rmate, Editor]
category: 技术
---
## Preparation of Sublime Text 准备工作

`ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl 就可以了`

Run `subl --help`

subl as default EDITOR

`export EDITOR='subl -w'`

Specifying -w will cause the subl command to not exit until the file is closed.

## Install

Install `rmate` on remote server where you would like to 

You can install `rmate` via `gem`:

```
gem install rmate
```

or just:


```
curl -Lo /usr/local/bin/rmate https://raw.github.com/textmate/rmate/master/bin/rmate
chmod a+x /usr/local/bin/rmate
```

or, you cqn install ported version of 

- [Bash version](https://github.com/aurora/rmate) by Harald Lapp
- [Python version](https://github.com/sclukey/rmate-python) by Steven Clukey

## 用法 Usage:

- First open Sublime Text or TextMate on your machine. 
- Then, open a tunnel to your server on your local machine 

```
ssh -R 52698:localhost:52698 user@yourserver.org
这样
```

- Finally, run `rmate yourfile` on the openned ssh shell and edit your file on your local machine