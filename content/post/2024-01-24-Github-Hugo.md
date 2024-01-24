---
showonlyimage: true
title:     "Github+Hugo 配置个人博客网站"
subtitle:   "踩坑经验"
excerpt: " "
description: "踩坑经验"
date:    2024-01-24
author:  陈诗曰
image: "/img/contact-bg.jpg"
published: true 
tags:
    - Hugo

categories: [ Tech ]
URL: "/2024/01/24/Github-Hugo/"
---

最近尝试了用Hugo + Github pages来部署个人博客网站，使用的是hugo-theme-cleanwhite主题。本来以为过程挺简单的，结果还是踩了不少坑才成功。所以，基于这两天踩过的坑，我把目前我得到的最正确方便的步骤按顺序捋一遍。

**平台:** MacOS \
**hugo version:**  v0.121.2

### 1. 首先在github上新建一个github仓库Blog

直接在github中new repository即可，名字就叫Blog吧～

>后面发现名字还不能随便取，如果叫Blog的话，那么发布在github上的网页初试页面就会变成"https://zhuchangyan.github.io/Blog/"，然而在点击主页后就会变成 "https://zhuchangyan.github.io/"，使得页面不存在。

### 2. 在本地clone新建的仓库

```
git clone https://github.com/zhuchangyan/Blog.git
```
### 3. 按照hugo themes的要求，在本地仓库Blog文件夹中。

```
$ cd Blog
$ mkdir themes
$ git submodule add https://github.com/zhaohuabing/hugo-theme-cleanwhite.git themes/hugo-theme-cleanwhite
$ cd themes
$ cp -r hugo-theme-cleanwhite/exampleSite/** ../
$ cd ..
$ hugo serve
```
注意这里我用了git submodule而不是直接git clone，是为了避免themes仓库和我自建仓库的冲突。

输入hugo serve之后在浏览器中输入
http://localhost:1313/ (bind address 127.0.0.1)就可以在本地查看网站的样子啦。

接下来，我们就要把本地的网站发布到github pages上去，成为真正可以访问的网站。


### 4. 首先我们要建立远程github仓库和本地的连接，因为我们刚刚是直接clone的，所以很简单， 用git remote set-url就可以设置连接到的仓库的地址。

这里我用了Personal Access Token来提供远程访问的密钥，详细方式在PAT部分有提到。拿到token后就可以用token进行便捷的登录啦～


```
$ git remote set-url origin https://your-personal-token@github.com/zhuchangyan/Blog.git
```

完成之后可以用git remote -v确认一下远程地址。

### 5. push 本地仓库到github

完成本地和远程的连接之后，就可以正常的git push命令：

```
$ git pull ## 把远程的内容同步过来
$ git add -A 
$ git commit
$ git push

```
这个git push/pull的流程是非常标准的流程了，没有什么可说的。

接下来就进入最重要的环节，在github仓库部署网站。

### 6. Build and deployment

打开settings --> Pages, source选中Github actions, 在底下出来的两个方框中选择deploy hugo,然后在新页面中选择commit。

commit之后其实已经开始commit了，在code页面会出现一个绿色的点代表正在运行。也可以重新回到page页面， 在build and deployment底下可以查看workflow同样可以看到进度，几分钟之后就可以看到Github pages下面出现了网址了。

大功告成！

接下来就是正常的网站运营和维护了～