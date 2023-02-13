---
title: vscode
---

# 前言

vscode是一个代码编辑器，vscode支持ssh协议，能连接远程服务器

## 下载vscode

vscode为开源软件，进入官网即可下载

https://code.visualstudio.com/Download#

插件下载

## 远程连接服务器

1.安装相关扩展

该扩展以ssh协议连接服务器，vscode联网即可下载

![Snipaste_2023-02-12_16-52-14](C:\Users\Administrator\Desktop\blog\img\Snipaste_2023-02-12_16-52-14.png)

2.使用内网ip地址登录服务器，因为我使用的是云服务器，所以账户是root，密码是登录时所使用的密码

![Snipaste_2023-02-12_17-05-18](C:\Users\Administrator\Desktop\blog\img\Snipaste_2023-02-12_17-05-18.png)

3.该配置保存在本地，在config文件中修改，每次点击连接时，需要验证密码，所以我推荐设置免密登录

![Snipaste_2023-02-12_17-10-19](C:\Users\Administrator\Desktop\blog\img\Snipaste_2023-02-12_17-10-19.png)

4.使用git提交代码时需要在服务器中建立一个本地的标签，也就是邮箱和用户名。

git config --global user.name "AnHao"

git config --global user.email "AnHao"

在./root/.gitconfig中可以查看布置的邮箱和

## 设置免密登录

### 1.在windows下，使用git bash 

输入命令 ssh-keygen -t rsa

出现提示，一直回车即可

### 2.在远程服务器上，生成公钥

输入命令 ssh-keygen -t rsa

出现提示，一直回车即可

### 3.拷贝id_rsa.pub

将windows下的id_rsa.pub拷贝到远程服务器的./.ssh目录下

### 4.修改authorized_keys

可以使用命令

mv id_rsa.pub authorized_keys     或者

将id_rsa.pub的内容，复制到authorized_keys中。

### 5.重启vscode

重新登录后，就不用再输入密码了
