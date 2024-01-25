---
showonlyimage: true
title:      "Hugo 技巧总结"
subtitle:   "如何实现latex"
excerpt: " "
description: "有很多地方都不太会。"
date:  2024-01-25
author: 陈诗曰
image: "/img/contact-bg.jpg"
published: true 
tags:
    - Hugo
categories: [ Tech ]
---


# Start

首先安装hugo

然后查看version:

hugo version

建立一个新网站：

hugo new site cyblog
![](/img/404-bg.jpg)

Congratulations! Your new Hugo site was created in /Users/changyanzhu/MySpace/MyBlog/cyblog.

Just a few more steps...

1. Change the current directory to /Users/changyanzhu/MySpace/MyBlog/cyblog.
2. Create or install a theme:
   - Create a new theme with the command "hugo new theme <THEMENAME>"
   - Install a theme from https://themes.gohugo.io/
3. Edit hugo.toml, setting the "theme" property to the theme name.
4. Create new content with the command "hugo new content <SECTIONNAME>/<FILENAME>.<FORMAT>".
5. Start the embedded web server with the command "hugo server --buildDrafts".


# Themes

找到一个不错的主题，直接使用。

https://github.com/zhaohuabing/hugo-theme-cleanwhite.git




# 使用latex
