---
showonlyimage: true
title:      "Github + Hugo 技巧总结"
subtitle:   ""
excerpt: " "
description: "包括Personal access tokens的获取， latex语法的实现等等。"
date:  2024-01-25
author: 陈诗曰
image: "/img/contact-bg.jpg"
published: true 
tags:
    - Hugo
categories: [ Tech ]
math: true
---


# 1. Github远程同步 (Personal access tokens)

在我们git clone一个仓库之后，在本地文件夹做的改动可以通过git push同步到远程。
然而在git push命令执行后，需要输入用户名和密码。在2021年后不能再使用github的登录密码，而需要token，也就是我们要提到的Personal access tokens(PAT)。

获取PAT的方式很简单： 

在个人profile的页面，点击Settings --> Developer Settings --> Personal access tokens， 新建一个Fine-grained tokens。

这个过程很简单， 但是注意要给足够的权限，否则在push的时候会遇到access denied的情况。

我现在选中的是
>Read and Write access to actions, administration, code, codespaces, codespaces lifecycle admin, codespaces secrets, commit statuses, and security events

得到token之后就可以把它复制下来，然后在本地命令行中
```bash
$ git remote set-url origin https://you-personal-token@github.com/zhuchangyan/zhuchangyan.github.io.git
```
就相当于把token保存到了本地，这样之后可以直接运行git pull&push而不用输入密码了。

另外，可以用下面的命令查看当前push&push的仓库在哪里。
```bash
$ git remote -v
```

# 2. 配置latex

终于搞定了latex支持。   

参照https://mertbakir.gitlab.io/hugo/math-typesetting-in-hugo/中的方法。

1. 建一个/layouts/partials/katex.html文件

可以进入[Katex 官网](https://katex.org/docs/browser.html)， 里面有提供katex.html的最新示例。

```html
<!DOCTYPE html>
<!-- KaTeX requires the use of the HTML5 doctype. Without it, KaTeX may not render properly -->
<html>
  <head>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css" integrity="sha384-n8MVd4RsNIU0tAv4ct0nTaAbDJwPJzDEaqSD1odI+WdtXRGWt2kTvGFasHpSy3SV" crossorigin="anonymous">

    <!-- The loading of KaTeX is deferred to speed up page rendering -->
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js" integrity="sha384-XjKyOOlGwcjNTAIQHIpgOno0Hl1YQqzUOEleOLALmuqehneUG+vnGctmUb0ZY0l8" crossorigin="anonymous"></script>

    <!-- To automatically render math in text elements, include the auto-render extension: -->
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js" integrity="sha384-+VBxd3r6XgURycqtZ117nYw44OOcIax56Z4dCRWbxyPt0Koah1uHoK0o4+/RRE05" crossorigin="anonymous"
        onload="renderMathInElement(document.body);"></script>
  </head>
  ...
</html>
```

2. 为了能够在所有页面上都使用katex，我们得在partial/head.html里定义一个math参数：
```html
{{ if .Params.math }}{{ partial "katex.html" . }}{{ end }}
```
3. 最后在post中加上：

```
math: true
```
就可以正常使用latex了。

4. 如果想要inline equation，就在katex.html中再加上：
```html
<script>
    document.addEventListener("DOMContentLoaded", function() {
        renderMathInElement(document.body, {
            delimiters: [
                {left: "$$", right: "$$", display: true},
                {left: "$", right: "$", display: false}
            ]
        });
    });
</script>
```
现在来示例一下：


* inline equation "$$"

$y = x^2 $

* 居中equation

$$ y = x^3 $$

* 用\\begin{equation}的方式

\begin{equation}
y = x^5
\end{equation}


# 3. small tips

* 遇到标签不能够在网站上同步的情况时，重新hugo server一下就好了。




