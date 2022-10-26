---
title: Sublime Text 开启对NCL的支持－附Vim NCL
date: 2014-11-06 11:03:33
tags: [ Sublime text, NCL, 语法高亮, 编辑器, Vim]
category: 技术
---
NCL是一门小众的语言，Sublime Text 是最近比较火的一款扩展能力非常强的跨平台编辑器，因此即便是小众的NCL 也有人（LASG的Dong Li 啦）为他开发了NCL支持功能，包括语法高亮、自动补全等。 具体使用方法如下：

## 安装 Sublime Text
自不赘言 http://www.sublimetext.com

## 开启Package 管理包
通过 ctrl+` 或者 the `View > Show Console ` Menu 打开 控制台，然后输入：

如果是 Sublime 2:
```
import urllib2,os,hashlib; h = '2deb499853c4371624f5a07e27c334aa' + 'bf8c4e67d14fb0525ba4f89698a6d7e1'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')
```

如果是 3:
```
import urllib.request,os,hashlib; h = '2deb499853c4371624f5a07e27c334aa' + 'bf8c4e67d14fb0525ba4f89698a6d7e1'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

## 添加 NCL扩展包

* Open command palette (click menu Tools > Command Palette ... or press ctrl-shift-p in Linux/Windows or cmd-shift-p in Mac).
* Type Install Package (you can just type some characters of Install Package such as inst).
Wait the completion of the loading (patience).
* Type NCL and click the NCL item showing up.

Here we go!

## Vim NCL

`git clone https://github.com/xiexinyls/vim ~/.vim`

也可以到 https://github.com/xiexinyls/vim 下载，然后放到 ~/.vim  目录下面，
当然注意 ~/.vimrc 文件
