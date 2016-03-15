+++
date = "2016-02-01T18:22:14+08:00"
title = "Git的常用么命令"
tags        = [ "git" ]
categories  = [ "tool" ]
+++

#### 生成密钥
`ssh-keygen`

#### 添加公钥到git账户

#### 检测是否成功
`ssh -T git@github.com`

#### 获取代码
git clone git://github.com:xxxx/test.git 以gitreadonly方式克隆到本地，只可以读

git clone git@github.com:xxx/test.git  ##以SSH方式克隆到本地，可以读写

git clone https://github.com/xxx/test.git ##以https方式克隆到本地，可以读写

git fetch git@github.com:xxx/xxx.git  ##获取到本地但不合并

git pull git@github.com:xxx/xxx.git ##获取并合并内容到本地

#### 本地配置
git config --global user.name 'ed'  
git config --global user.email 'erickdotphp@gmail.com' #全局联系方式，可选  

#### 新建Git项目并提交到Github
`mkdir testdir & cd testdir `
`touch README.md`
* git init #初始化一个本地库  
* git add README.md #添加文件到本地仓库  
* git rm README.md #本地倒库内删除  
* git commit -m "first commit" #提交到本地库并备注，此时变更仍在本地。  
* git commit -a  ##自动更新变化的文件，a可以理解为auto  
* git remote add xxx git@github.com:xxx/xxx.git  #增加一个远程服务器的别名。  
* git remote rm xxx   ##删除远程版本库的别名  
* git push -u remotename master 

将本地文件提交到Github的remoname版本库中。此时才更新了本地变更到github服务上。  

#### 创建和合并分支
* git branch #显示当前分支是master  
* git branch new-feature  #创建分支  
* git checkout new-feature  #切换到新分支  
* vi page_cache.inc.php  
* git add page_cache.inc.php  
* git commit -a -m "added initial version of page cache"  
* git push origin new-feature  ##把分支提交到远程服务器，只是把分支结构和内容提交到远程，并没有发生和主干的合并行为。  

#### 如果new-feature分支成熟了，觉得有必要合并进master
* git checkout master  #切换到新主干  
* git merge new-feature  ##把分支合并到主干  
* git branch #显示当前分支是master  
* git push  #此时主干中也合并了new-feature的代码  

#### 忽略某个文件更新的命令
`git update-index --assume-unchanged`


