+++
date = "2016-02-01T12:30:55+08:00"
title = "Centos7 上 安装和配置 Sublime Text3"
tags        = [ "sublime" ]
categories  = [ "tool" ]
+++

### 下载最新的包
http://www.sublimetext.com/3

下载tarball

`$ tar jxvf sublime_text_3_build_3083_x64.tar.bz2  -C /opt`

### 移动到系统目录
`$ mv sublime_text_3 /opt/`

### 创建连接
`$ ln -s /opt/sublime_text_3/sublime_text /usr/bin/sublime`


### 移动到系统目录下
`$ cp /opt/sublime_text_3/sublime_text.desktop /usr/share/applications`


### 修改配置文件

`$ cd /usr/share/applications`
`$ vim sublime_text.desktop`

```
[Desktop Entry]
Version=1.0
Type=Application
Name=Sublime Text
GenericName=Text Editor
Comment=Sophisticated text editor for code, markup and prose
Exec=/opt/sublime_text_3/sublime_text %F
Terminal=false
MimeType=text/plain;
Icon=/opt/sublime_text_3/Icon/48x48/sublime-text.png
Categories=TextEditor;Development;
StartupNotify=true
Actions=Window;Document;

[Desktop Action Window]
Name=New Window
Exec=/opt/sublime_text_3/sublime_text -n
OnlyShowIn=Unity;

[Desktop Action Document]
Name=New File
Exec=/opt/sublime_text_3/sublime_text --command new_file
OnlyShowIn=Unity;
```


这些都做完以后 sublime的快捷方式会出现在   应用程序=>编程 里面