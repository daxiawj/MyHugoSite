---
title: 一切为了太阳系的荣耀--Xshell的Solarized配色
tags:
  - 美化
  - Solarized
  - Xshell
  - 系统
date: 2014-03-23 14:50:57
category: 系统
---

Xshell 是 Windows 里面为数不多的免费且好用的 SSH 客户端，不过默认的配色实在是太难看了，真的是太难看了，如果不改掉实在是不能用。而且和 Sublime Text、TextMate、Emacs、VIM 等编辑神器以及 iTerm2 等深受好评的软件不一样，网上现成的 XShell 配色也着实少的可怜。冇办法，只好自己动手了。

上面提到的编辑器，真的有很多经典的配色，如 Monokai、Dawn、Eiffel、Tommorow、Twilight 等，但是我最爱的，还是那经典的 Solarized。关于 Solarized，已经有很多 [ 介绍 ](http://www.dblotus.com/?p=1524)，其官网在[ 这里 ](http://ethanschoonover.com/solarized)，Github 的主页在[ 这里](https://github.com/altercation/solarized)，上面有为很多软件如 Emacs、Gedit、iTerm2、Putty、VIM、TextWrangler 等写好的配色文件，可自行采撷。

最爱的 Solarized Dark 配色，写成 Xshell 能用的形式如下
```
[Solarized Dark]
text(bold)=839496
magenta(bold)=6c71c4
text=839496
white(bold)=fdf6e3
green=859900
red(bold)=cb4b16
green(bold)=586e75
black(bold)=073642
red=dc322f
blue=268bd2
black=002b36
blue(bold)=839496
yellow(bold)=657b83
cyan(bold)=93a1a1
yellow=b58900
magenta=dd3682
background=042028
white=eee8d5
cyan=2aa198
[Names]
count=1
name0=Solarized Dark

```

只需把以上内容拷贝到 SolarizedDark.xcs，并在 Xshell 中导入这个配色文件，就可以享受程序猿专用的温暖的太阳系之光了。

效果如图![](/images/SD.png)

以下为更加温暖的亮色系配色文件，同理保存为 SolarizedLight.xcs 并导入 Xshell 即可。

```
[Solarized Light]
text(bold)=657b83
magenta(bold)=6c71c4
text=657b83
white(bold)=002b36
green=859900
red(bold)=cb4b16
green(bold)=93a1a1
black(bold)=eee8d5
red=dc322f
blue=268bd2
black=fdf6e3
blue(bold)=657b83
yellow(bold)=839496
cyan(bold)=586e75
yellow=b58900
magenta=dd3682
background=fdf6e3
white=073642
cyan=2aa198
[Names]
count=1
name0=Solarized Light

```
效果如图![](/images/SL.png)

ps: 后来仔细看了一下，已经有人 fork 了一个 Solarized 的代码库，并提交了 for Xshell 的 pull。参见
[这里]（https://github.com/mayjabber/solarized/tree/master/xshell-colors-solarized) [https://github.com/mayjabber/solarized/tree/master/xshell-colors-solarized](https://github.com/mayjabber/solarized/tree/master/xshell-colors-solarized)