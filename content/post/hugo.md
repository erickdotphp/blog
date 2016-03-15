+++
date = "2016-03-13T18:22:14+08:00"
title = "这个博客是怎么搭建起来的"
summary = "关于怎样搭建一个博客"
tags        = [ "hugo"]
categories  = [ "tool" ]
+++

大概原理
-------------
1. 首先hugo，用来生成博客的静态文件
hugo是用go语言写的，效率比较高

2. 把生成好的静态页面通过github pages 上传到github上

就做好了

安装
-------------
可以直接下载可执行文件 linux windows都有
官网地址 https://gohugo.io/

创建新的站点
-------------
`$ hugo new site blog`

会生成一个文件夹，里面的config.toml是配置文件
这是一个TOML文件，全称是Tom’s Obvious, Minimal Language，这是它的作者GitHub联合创始人Tom Preston-Werner 觉得YAML不够优雅，捣鼓出来的一个新格式。如果你不喜欢这种格式，你可以将config.toml替换为YAML格式的config.yaml，或者json格式的config.json。hugo都支持。

创建新页面
------------
cd 到 blog下 

`$ hugo new about.md`

这样会把文件生成在contents目录下

也可以放在文件夹下

`$ hugo new post/first.md`

md就是markdown格式，很方便

默认是没有模板的，可以去下载模板

地址是 [这里](https://github.com/spf13/hugoThemes)

找好模板之后
创建themes文件夹

`$ mkdir themes`

$ git clone https://github.com/spf13/模板名.git

启动本地服务器
-----
`$ hugo server --theme=base16 --buildDrafts --watch`

watch 是监控文章更新  buildDrafts是生成content里面的页面

生成静态站点
-----
在blog目录下

`$ hugo --theme=base16 --buildDrafts`

生成好以后把public里面的文件上传到github上就可以了

参考文章
[http://www.gohugo.org/](http://www.gohugo.org/)

