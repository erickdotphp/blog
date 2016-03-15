+++
date = "2016-03-14T18:22:14+08:00"
title = "Git 多远端问题"
tags        = [ "git" ]
categories  = [ "tool" ]
+++

如果需要在同一套代码中控制多个远程版本

#### 查看当前的远端

`$ git remote -v`

#### 增加远端

`$ git remote add 远端名 远端git地址`

这样推送和拉取的之后只要在后面加上远端名和分支名就可以

#### 拉取远端

`$ git pull inter master`

#### 推送远端

`$ git push inter master`

