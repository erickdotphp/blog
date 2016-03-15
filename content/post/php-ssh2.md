+++
date = "2016-03-16T22:30:55+08:00"
title = "PHP SSH2 扩展"
tags        = [ "PHP", "SSH2" ]
categories  = [ "env" ]
+++


### 安装

#### 下载包
wget http://www.libssh2.org/download/libssh2-1.4.2.tar.gz

wget http://pecl.php.net/get/ssh2-0.12.tgz

#### 先安装 libssh2 再安装 SSH2

`$ tar -zxvf libssh2-1.4.2.tar.gz`

`$ cd libssh2-1.4.2`

`$ ./configure --prefix=/usr/local/libssh2`

`$ make && make install`

#### 安装ssh2

`$ tar -zxvf ssh2-0.12.tgz`

`$ cd ssh2-0.12`

`$ /usr/local/zend/bin/phpize`

`$ ./configure --prefix=/usr/local/ssh2 --with-ssh2=/usr/local/libssh2 --with-php-config=/usr/local/zend/bin/php-config`

`$ make && make install`

修改php.ini 加入 

`extension=ssh2.so`

重启Zend Server

### 调试

##### 用户名密码方式登录

```
$user="root";//远程用户名
$pass="123456";//远程密码
$connection=ssh2_connect('192.168.1.46',22);
ssh2_auth_password($connection,$user,$pass);
```

##### 用sshkey方式登录


```
$connection=ssh2_connect('192.168.1.46',22);
if(ssh2_auth_pubkey_file($connection, 'root', '/home/id_rsa.pub', '/home/id_rsa', 'secret'))
{
    echo "Public Key Authentication Successful\n";
} else {    
    die('Public Key Authentication Failed');
}
```

##### 执行命令获取返回值

```
$cmd="ps aux";//命令
$ret=ssh2_exec($connection,$cmd);
stream_set_blocking($ret, true);
echo (stream_get_contents($ret));
```
