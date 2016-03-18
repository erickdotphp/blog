+++
date = "2016-02-01T18:22:14+08:00"
title = "Git的常用么命令"
tags        = [ "git" ]
categories  = [ "tool" ]
+++

#### 生成密钥
`ssh-keygen`

#### 检测是否成功

`$ ssh -T git@github.com`

#### 本地配置用户名和邮箱

`$ git config --global user.name 'ed'`
`$ git config --global user.email 'erickdotphp@gmail.com'` 

#### 初始化

`$ git init`

#### 添加README

`$ git add README.md`

#### 自动提交所有变化文件

`$ git commit -a -m "comment" `

不自动提交的话需要`$ git add 文件名或者-A`


#### 忽略某个文件更新的命令

`$ git update-index --assume-unchanged`


####忽略权限修改

`$ git config core.filemode false`

