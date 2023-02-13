---
title: git
---







参考pro git简体中文版

http://iissnan.com/progit/ 

# 1.git的基本使用方式

## 1.1git 安装

linux

yum -y install git

输入 git --version查看Git是否安装完成以及查看其版本号

windows 

https://git-scm.com/

进入git官网，选择windows版本进行下载

下载完后，点击exe文件执行，根据提示进行安装，

安装完成之后在桌面点击右键出现git bash 即成功



### 1.2 本地建立git标识

git config --global user.name "YOUR NAME"

git config --global user.email "YOUR EMAIL"

该两行命令表示一个标识，

### 1.3初始化git仓库

git init

在哪个目录下执行的，那这个目录就变成git可以管理的目录

### 1.4 添加文件到暂存区

git add [文件名] 

#将文件添加到暂存区

### 1.5  用命令 git commit告诉Git，把文件提交到仓库

git commit -m "注释"   ##给本次提交提供注释

### 1.6 **连接远程仓库**

在github(或其他接受git命令的仓库)

点开github页面，在设置里找到ssh连接，将本地的公钥内容复制到ssh框中，重新输入密码，提示成功即可。

```
git remote add origin https://github.com/xuyujie2020/Hello-World.git
```

使用该命令连接到远程仓库

```
把远程仓库和本地仓库连接起来
再自己仓库的主目录下输入命令

git remote add origin git@github.com:<用户名>/<仓库名>.git

以上命令origin是远程库名，也可以改成别的，但是这个是默认的，一看就知道是远程库，学习阶段没有改的必要。

<用户名>就是注册用户的时候输入的用户名。<仓库名>就是建立仓库的时候输入的仓库名。

如果地址写错了，关联错了，或者干脆想解除关联，可以用git remote rm origin来解除关联。

不过在此之前建议看看远程库信息，确认一遍，输入命令

git remote -v
```



### 1.7上传代码

git push -u origin master

第一次提交代码需要加上-u

### 1.8克隆代码

使用git clone + [url]   ##url : 路径

github支持git和http两种克隆模式

### 1.9 查看当前分支

git status

可以查看clone下来的代码所属的分支

使用git checkout 可以切换分支

git branch 也可以查看分支

### 1.10 创建分支

git branch + [名字] 创建一个新的分支，不切换分支

git checkout -b 创建一个分支并切换过去

### 1.11 查看代码的修改

每次代码修改会在该目录下形成一个.git文件，修改的内容保存在这

git status 可以查看被修改过的文件

git diff 查看修改的内容

### 1.12 删除分支

git branch -d + [名字]

### 1.13 删除仓库

在github网页中，进入仓库，在设置中的最下面选择delete，输入要删除的仓库的路径即可



问题解决

visual studio 上传代码出现错误

使用git add .时出现

error: open("贪吃蛇/.vs/贪吃蛇/v17/Browse.VC.opendb"): Permission denied
error: unable to index file '贪吃蛇/.vs/贪吃蛇/v17/Browse.VC.opendb'
fatal: adding files failed

解决方法

touch .gitignore    

在文件中添加 .vs/保存即可

##忽略.vs/文件

#### 整体流程

```
 git init 
 echo "hello " >> README.md
 git add README.md 
 git commit -m "first commit"
 //使用ssh方式
 git remote add origin git@github.com:nmt/nmblog.github.io.git
 git push -u origin master //第一次提交需要使用-u

```









