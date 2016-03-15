+++
date = "2016-02-01T10:30:55+08:00"
title = "Centos7 上 安装 ZendServer"
tags        = [ "Zend Server", "nginx", "PHP" ]
categories  = [ "env" ]
+++


### 获取官方包
`$ wget http://downloads.zend.com/zendserver/8.5.1/ZendServer-8.5.1-RepositoryInstaller-linux.tar.gz`

### 关闭防火墙

`$ vim /etc/selinux/config`

SELINUX=disabled

`$ setenforce 0`

### 安装ZendServer
`./install_zs.sh 5.6 nginx`


### 远程访问不到zend server 需要关闭iptable
`$ service iptables status`
`$ service iptables stop`

### 配置文件的路径如下

* nginx  vim /etc/nginx/nginx.conf 
* php /usr/local/zend/etc/php.ini
* fpm /usr/local/zend/etc/php-fpm.conf 
* 虚拟机 /usr/local/zend/etc/sites.d

### 都配置好以后可以访问主机地址了
http://localhost:10081/ZendServer/

### 另外破解方法

`vim /usr/local/zend/gui/module/Configuration/src/Configuration/License/License.php` 

所有判断改成return true;

### FAQ

Nginx 报错 no port in upstream "fastcgi_backend",因为没有配置fastcgi
在/etc/nginx/nginx.conf在

`access_log  /var/log/nginx/access.log  main;`

后面加入

```
    fastcgi_read_timeout 300;
    upstream fastcgi_backend {
       server   unix:/usr/local/zend/tmp/php-fpm.sock;
    }
```

其中fastcgi_read_timeout 300;是为了防止ngxin 504超时错误



