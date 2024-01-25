# My Blog

Codes for my personal blog website.

**平台:** MacOS \
**hugo version:**  v0.121.2

1. 新建github仓库

仓库名叫做your_user_name.github.io

1. 在本地clone新建的仓库

在本地新建一个文件夹，然后运行：
```bash
$ git clone https://github.com/zhuchangyan/Blog.git
```
3. 配置网站

首先安装hugo
```bash
$ brew install hugo
```
然后查看version:
```bash
$ hugo version
```
安装好之后就可以通过hugo来配置网站了。

hugo的官网中提供了很多的主题可以选择，这里我们选择hugo-theme-cleanwhite，其他themes的操作基本都一样。
```bash
$ cd Blog
$ mkdir themes
$ git submodule add https://github.com/zhaohuabing/hugo-theme-cleanwhite.git themes/hugo-theme-cleanwhite  # 将themes模块化添加到本地仓库中
$ cd themes
$ cp -r hugo-theme-cleanwhite/exampleSite/** ../  # 把themes的样例复制到仓库中。
$ cd ..
$ hugo serve
```
注意这里我用了git submodule而不是直接git clone，是为了避免themes仓库和我自建仓库的冲突。

输入hugo serve之后在浏览器中输入 http://localhost:1313/(bind address 127.0.0.1)就可以在本地查看网站的样子啦。接下来，我们就要把本地的网站发布到github pages上去，成为真正可以访问的网站。

4. 建立远程连接

首先我们要建立远程github仓库和本地的连接，因为我们刚刚是直接clone的，所以很简单， 用git remote set-url就可以设置连接到的仓库的地址。

这里我用了Personal Access Token来提供远程访问的密钥，详细方式在PAT部分有提到。拿到token后就可以用token进行便捷的登录啦～

```bash
$ git remote set-url origin https://your-personal-token@github.com/zhuchangyan/Blog.git
```
这里"your-personal-token"用得到的token来替换掉。
完成之后可以用git remote -v确认一下远程地址。

5. push 本地仓库到github

完成本地和远程的连接之后，就可以正常的git push命令：
```bash
$ git pull ## 把远程的内容同步过来
$ git add -A 
$ git commit
$ git push
```
或者使用一个指令：
```bash
$ git add . && git commit -m 'new hugo blog' -a && git push
```
这个git push/pull的流程是非常标准的流程了，没有什么可说的。
接下来就进入最重要的环节，在github仓库部署网站。

6. Build and deployment

打开settings --> Pages, source选中Github actions, 在底下出来的两个方框中选择deploy hugo,然后在新页面中选择commit。

commit之后其实已经开始commit了，在code页面会出现一个绿色的点代表正在运行。也可以重新回到page页面， 在build and deployment底下可以查看workflow同样可以看到进度，几分钟之后就可以看到Github pages下面出现了网址了。
