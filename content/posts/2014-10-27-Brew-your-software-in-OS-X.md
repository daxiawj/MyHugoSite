---
title: Brew your software in OS X
date: 2014-10-27 09:38:12
tags: [OSX, Mac, Software, brew]
category: 系统
---

## 安装 brew

`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"` 

## 查找软件

`brew search netcdf`

## 查看软件信息

`brew info netcdf`

## 安装软件

`brew install ncview gfortran cdo grads wget axel parallel`

值得注意的是，brew会自动解决依赖问题，如ncview依赖netcdf，那么他会自动先安装netcdf，然后再安装ncview

如果编译一个软件需要参数，那么可以直接加上这些参数，如：

`brew install --enable-fortran`

## 安装小众软件

brew 目前将比较小众的一些软件分门别类，cdo 属于science类，同样地 ncview、netcdf等也属于这一类，而grads则分到binary 类，这类小众软件的formula默认是不下载的，需要预先“提取”一下: 

`brew tap homebrew/science homebrew/binary`

## 自己创建brew安装包

如果需要的软件暂时还没有进入官方维护包内，那么可以创建一个新的 brew formula (以cdo为例, 更新：cdo目前已经正式进入官方的list中，因此不需要再手动创建，而只需要运行 brew install cdo 就好了)

`brew create https://code.zmaw.de/attachments/download/2372/cdo-1.5.4.tar.gz`

创建好了以后，修改 Formula文件，解决一些依赖问题

`brew edit cdo`

写入以下内容（依赖 netcdf, hdf5, proj）

```ruby
require 'formula'

class Cdo < Formula
  url 'https://code.zmaw.de/attachments/download/1690/cdo-1.5.2.tar.gz'
  homepage ''
  md5 'a01826b7c2906579f17c6dbc7d619479'

  depends_on 'netcdf'  # 这几句是手动添加的，增加依赖关系
  depends_on 'hdf5'
  depends_on 'proj'

  def install
  
    hdf5   = Formula.factory 'hdf5'  # 这几句是手动添加的，增加依赖关系
    netcdf = Formula.factory 'netcdf'
    proj   = Formula.factory 'proj'
    system "./configure", "--with-hdf5=#{hdf5.prefix}","--with-proj=#{proj.prefix}","--disable-debug", "--disable-dependency-tracking","--with-netcdf=#{netcdf.prefix}", "--prefix=#{prefix}"
    # system "cmake . #{std_cmake_parameters}"
    system "make install"
  end

  def test
    # This test will fail and we won't accept that! It's enough to just
    # replace "false" with the main program this formula installs, but
    # it'd be nice if you were more thorough. Test the test with
    # `brew test cdo`. Remove this comment before submitting
    # your pull request!
    system "false"
  end
end
```
然后就可以编译安装啦

`brew install cdo`