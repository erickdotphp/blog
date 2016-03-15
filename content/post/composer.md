+++
date = "2016-02-01T12:30:55+08:00"
title = "Centos7 上 安装 Composer"
tags        = [ "Composer"]
categories  = [ "env" ]
+++


安装前请确保 环境中有PHP
可以用`php -v`查看

#### 下载

`$ curl -sS https://getcomposer.org/installer| php -- --install-dir=/home`

#### 移动到可执行目录

`$ mv composer.phar /usr/local/bin/composer`


#### 配置环境变量

`$ export PATH=$PATH:/usr/local/bin`