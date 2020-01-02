## 使用Git对代码进行clone

> **注意：（win10系统下）**



**目录**

[TOC]

### :fire:Git安装

在Windows上安装Git，

可以直接从Git的官网上下载安装程序，

[Git下载地址](https://git-scm.com/downloads)

网速慢的可以直接通过这个，

[百度网盘](https://pan.baidu.com/s/18WeVJOObwL3FUbADe773lg)（提取码：`znrb`）

然后按默认选项安装即可。

[详细的安装教程](https://blog.csdn.net/qq_32786873/article/details/80570783)（推荐）

在开始菜单中找到`Git-->Git Bash`点击打开弹出一个命令行窗口

说明Git安装成功。



### :fire:克隆Github代码

选择一个需要放置clone文件的文件夹

在该文件夹内，右击选择`Git Bash Here`

输入`git init`初始化一个本地仓库

会告诉你一个空的git仓库已经建好，在你点击Git Bash Here这里

`Administrator@SmartCamel MINGW64 /e/architect-awesome`
`$ git init`
`Initialized empty Git repository in E:/architect-awesome/.git/`



**1.通过HTTPS通道惊行Clone（克隆）**

在GIthub上找到你想要的Clone到本地的Repository

然后在刚才建立好的新仓库中输入：

`git clone https://github.com/twbs/bootstrap.git`（以bootstrap为例）

Clone好之后就会有提示。



**2.通过SSH通道惊行Clone（克隆）**

使用SSH通道时需要先进行配置

 `git config --global user.name '用户名'`

`git config --global user.email '邮箱'`



通过这个命令行，找到ssh所在的位置

`ssh-keygen -t rsa -C "你的邮箱"`

就会告诉你你的ssh通道秘钥在那个文件里

找到`id_rsa.pub`后，右击，选择编辑，进入之后，将文本内容全部复制下来

打开你的`Github`在`settings`里边找到`SSH and GPG keys`选择`New SSH key`

将刚才复制的文本粘贴到`Key`里边，`Title`起名按个人喜好

设置好SSH之后，继续回到刚才的操作界面上

输入` ssh -T git@github.com`

`Hi ‘你的用户名’! You've successfully authenticated, but GitHub does not provide shell access.`

显示上边这段话，就说名你配置成功了



然后再在刚才建立好的新仓库中输入：

`git clone git@github.com:twbs/bootstrap.git`（以bootstrap为例）

出现和使用`https`时的内容则就表示`Clone`成功



**我这里总结一下二者的优缺点：**

- `https`协议
  - 优点：省去了本地配置的麻烦，只要有URL和相应的权限便能进行相应的操作
  - 缺点：每次操作都需要频繁验证，除非使用密码缓存机制
- `ssh`协议
  - 优点：推送或获取数据时不需要每次输入密码进行验证
  - 缺点：在使用之前需要进行配置，并生成ssh key