+++
date = "2016-03-15T10:30:55+08:00"
title = "Digital Ocean API整理"
description = "Nitro is a simple profiler for your Golang applications"
tags        = [ "Digital Ocean"]
categories  = [ "api" ]
+++


### 请求类型

__GET__ 只读请求，不需要验证，不会影响查询对象

__DELETE__ 删除操作

__PUT__ 更新操作

__POST__ 新增操作

__HEAD__ 只返回GET查询的head部分用于查询metadata


### 需要理解的几个词

#### Account

账户，包括基本信息，状态，水滴上限等等

#### Droplet

水滴（暂时这么翻译吧），可以理解为容器，Ocean的基本单位

#### Image
镜像，给Droplet使用的，可以作为备份，快照，或者是基础镜像

#### Actions
类似于日志的东西

#### Regions
区域，Digital Ocean 数据中心所在地，镜像可以在不同的区域之间切换

#### Slug
区域的唯一标示，human-readable

#### Size
硬件配置信息，一组配置信息包括内存，磁盘，区域CPU数量等信息。

#### Floating IP
公网可访问的静态IP，跟容器绑定



