---
title: Hello, Octopress
date: 2013-12-16 15:58:47
tags: [Blog, Demo, Octopress, LaTeX]
category: 博客
---
## 缘起
作为一个非主流 Coding 技术工人，不满 Sina Blog 已经很久了，各种功能缺失，比如数学公式，比如各种代码高亮。然而 WordPress 功能全则全矣，国内访问需要各种翻墙，各种不便。加上内容放在别人服务器上，始终是不放心的，比如即使如微软和雅虎等大公司，也是把服务说停就停的，如微软的 Live 博客和雅虎的相关服务。因此，自己掌握自己发布显然才放心；但是自己要搞定主机、DNS、独立 IP 等显然花费是巨大的，还好一心一意为码农服务的 GitHub 退出 Pages 服务，可以符合上述的要求，配合 Octopress，嘿嘿，Blog 也可以相当欢乐啊，本地备份、远程同步；Git 版本管理；加上 Github 社区化；再来个 BitBucket 的同步，嘿嘿，需要的东西齐活了。

如下，是一些简单的试用，呵呵。当然，建立一个功能齐全的 Blog 还是相当容易，但是要美观、大方、上档次那就需要相当一部分时间的调试了……

However, Hello, Octopress!

## Test code syntax

``` javascript
/**
sample javascript from xui
*/
 
var undefined,
    xui,
    window     = this,
    string     = new String('string'),
    document   = window.document,
    simpleExpr = /^#?([\w-]+)$/,
    idExpr     = /^#/,
    tagExpr    = /<([\w:]+)/,
    slice      = function (e) { return [].slice.call(e, 0); };
    try { var a = slice(document.documentElement.childNodes)[0].nodeType; }
    catch(e){ slice = function (e) { var ret=[]; for (var i=0; e[i]; i++)
        ret.push(e[i]); return ret; }; }
 
window.x$ = window.xui = xui = function(q, context) {
    return new xui.fn.find(q, context);
};
```
* another code demo

``` ruby Discover if a number is prime http://www.noulakaz.net/weblog/2007/03/18/a-regular-expression-to-check-for-prime-numbers/ Source Article
class Fixnum
  def prime?
    ('1' * self) !~ /^1?$|^(11+?)\1+$/
  end
end
```

* gist demo
{% gist 4321346 %}

or 

{% gist 4321346 gistfile1.diff %}

If you have a gist with multiple files, you can include files one at a time by adding the name after the gist id.

{% gist 1059334 svg_bullets.rb %}

## Math Examples

With these code:
{% vimhl latex false %}
 $$
 \LaTeX{}
 $$
 
 $$
 f=\frac{n v}{2 L}, \underbrace{\color{red}n=1, 2, 3, \ldots}_{\text{allowed 's}}
 $$
 
 $$
 \frac{n!}{k!(n-k)!} = \binom{n}{k}
 $$
 
 大家都喜欢用 $E=mc^2$ 举例子，但是我不是很理解。  
 
 这个公式 $\cos 2\theta = \cos^2 \theta - \sin^2 \theta =  2 \cos^2 \theta - 1$ 少年可还记得？
 
 插入方程组（注意多行公式结尾\\\需要打成\\\，可能是因为markdown会自动转义第一个\\）：
 
 \begin{aligned}
 \dot{x} & = \sigma(y-x) \\\
 \dot{y} & = \rho x - y - xz \\\
 \dot{z} & = -\beta z + xy
 \end{aligned}
 
 插入矩阵（同上）：
 
 \begin{bmatrix}
 1 & 2\\\
 3 & 4
 \end{bmatrix}
 
 来个复杂点的（注意有的公式开头不会自动识别，用$$包围）：
 
 $$
 \frac{\partial u}{\partial t} = h^2 \left( \frac{\partial^2 u}{\partial x^2} 
 + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2}\right)
 $$
 
 最后来个牛逼的吧，薛定谔方程，大学物理就记得这个了：
 
 $$
 i\hbar\frac{\partial \psi}{\partial t} = \frac{-\hbar^2}{2m} \left(  \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} +
  \frac{\partial^2}{\partial z^2} \right) \psi + V \psi.
 $$
{% endvimhl %}

结果如下：

 $$
 \LaTeX{}
 $$
 
 $$
 f=\frac{n v}{2 L}, \underbrace{\color{red}n=1, 2, 3, \ldots}_{\text{allowed 's}}
 $$
 
 $$
 \frac{n!}{k!(n-k)!} = \binom{n}{k}
 $$
 
 大家都喜欢用 $E=mc^2$ 举例子，但是我不是很理解。  
 
 这个公式 $\cos 2\theta = \cos^2 \theta - \sin^2 \theta =  2 \cos^2 \theta - 1$ 少年可还记得？
 
 插入方程组（注意多行公式结尾\\\需要打成\\\，可能是因为markdown会自动转义第一个\\）：
 
 \begin{aligned}
 \dot{x} & = \sigma(y-x) \\\
 \dot{y} & = \rho x - y - xz \\\
 \dot{z} & = -\beta z + xy
 \end{aligned}
 
 插入矩阵（同上）：
 
 \begin{bmatrix}
 1 & 2\\\
 3 & 4
 \end{bmatrix}
 
 来个复杂点的（注意有的公式开头不会自动识别，用$$包围）：
 
 $$
 \frac{\partial u}{\partial t} = h^2 \left( \frac{\partial^2 u}{\partial x^2}+ \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2}\right)
 $$
 
 最后来个牛逼的吧，薛定谔方程，大学物理就记得这个了：
 
 $$
 i\hbar\frac{\partial \psi}{\partial t} = \frac{-\hbar^2}{2m} \left(\frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2}+\frac{\partial^2}{\partial z^2} \right) \psi + V \psi.
 $$
