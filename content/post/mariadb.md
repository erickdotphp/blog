+++
date = "2016-02-01T11:30:55+08:00"
title = "Centos7 上 安装 mariadb"
tags        = [ "Mariadb", "Mysql" ]
categories  = [ "env" ]
+++

### 全部删除MySQL/MariaDB
MySQL 已经不再包含在 CentOS 7 的源中，而改用了 MariaDB;
* 使用rpm -qa | grep mariadb搜索 MariaDB 现有的包：
如果存在，使用rpm -e --nodeps mariadb-*全部删除：
* 使用rpm -qa | grep mariadb搜索 MariaDB 现有的包：
如果存在，使用yum remove mysql mysql-server mysql-libs compat-mysql51全部删除；

### 添加MariaDB的yum源
* 创建 /etc/yum.repos.d/MariaDB.repo：
* 添加yum源,该文件中添加如图所示内容：

```
# MariaDB 10.1 CentOS repository list - created 2015-11-19 02:26 UTC
# http://mariadb.org/mariadb/repositories/
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.0/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

### 安装 MariaDB
`$ yum install MariaDB-server MariaDB-client`

### 启动、配置MariaDB
`$ service mysql start`
`$ mysql_secure_installation`

