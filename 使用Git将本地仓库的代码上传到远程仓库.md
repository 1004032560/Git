**使用`Git`将本地仓库的代码上传到远程仓库**

****

**目录**

[TOC]

### 1.:fire:创建一个`github`的空仓库

![](E:\git_Repository\image\create_repository.png)



### 2.:fire:复制`clone`的链接地址

> 通过`SSH`或者`HTTPS`两种方法
>
> 详细操作可以看看
>
> [使用Git对仓库代码进行Clone](https://github.com/1004032560/Git/blob/master/使用Git对代码进行clone.md)



### 3.:fire:初始化本地仓库

> 找到要上传的本地文件的位置
>
> 右击打开`Git Bash Here`
>
> 输入如下命令行

![](https://raw.githubusercontent.com/1004032560/Git/master/image/gitBash_window.png)



**1.`git init`**

> 初始化本地仓库
>
> 他就会在你的文件中生成一个`.git`的文件夹
>
> 如果看不到的话可能是文件被隐藏了
>
> 点击 "查看——>勾选隐藏项目" 就可以看到了

![](https://raw.githubusercontent.com/1004032560/Git/master/image/git_init.png)



**2.`git add .`**

> 注意：不要忘记  `" . "`
>
> 此处的 `" . "` 相当于 `" -a "`
>
> 添加所有已经修改的的文件



**3.`git commit -m "value"`**

> 将修改的后的文件提交到远程仓库；同时说明修改的大概内容
>
> 例如：`git commit -m "增加文档说明"`

![](https://raw.githubusercontent.com/1004032560/Git/master/image/ready_commit.png)



### 4.:fire:连接到远程仓库，并将代码同步到远程仓库

**1.`git remote add origin git@github.com:1004032560/Test.git`**

> 连接到远程仓库并为该仓库创建别名 , 别名为`origin` 
>
> 这个别名是自定义的，通常用`origin` 
>
> 远程仓库地址，就是你自己新建的那个仓库的地址
>
> 刚才复制好的地址



**2.`git push -u origin master`**

> 创建一个 `upStream` （上传流）
>
> 并将本地代码通过这个 `upStream` 推送到
>
>  别名为 `origin` 的仓库中的 `master` 分支上
>
> >`-u` ，就是创建 `upStream` 上传流
> >
> >如果没有这个上传流就无法将代码推送到 `github`
> >
> >同时，这个 `upStream` 只需要在初次推送代码的时候创建
> >
> >以后就不用创建了
>
> 在初次 push 代码的时候
>
> 可能会因为网络等原因导致命令行终端上的内容一直没有变化
>
> 耐心等待一会就好

![](https://raw.githubusercontent.com/1004032560/Git/master/image/20190913165559.png)

![](https://raw.githubusercontent.com/1004032560/Git/master/image/20190913165634.png)

> 出现上边这些提示以后就说明
>
> 初次将本地代码提交到`github`已经成功了
>
> 如果有问题：请参考



### 5.:fire:第一次提交成功以后修改再提交代码

**1.`git add .`**

> 添加所有修改过的代码，准备提交

**2.`git commit -m "value"`**

> 将修改后的代码提交到本地仓库

**3.`git pull`**

> 如果是多人协作开发的话
>
> 一定要先 `pull` 
>
> 将 `github` 的代码拉取到本地
>
> 这样在 `merge` 解决冲突的时候稍微简便些
>
> 默认拉取到 `master`分支
>
> （如果只是自己做这个项目，可以忽略pull）

**4.`git push`**

> 将代码推送到 `github` ,
>
> 默认推送到 别名为 `origin` 的仓库中的 `master` 分支上

![](https://raw.githubusercontent.com/1004032560/Git/master/image/successce.png)

**5.`注意事项`**

> 如果有多个"远程仓库" 或者 "多个分支"
>
> 并且需要将代码推送到指定仓库的指定分支上
>
> 那么在 pull 或者 push 的时候
>
> 就需要 按照下面的格式书写：
>
> > git pull 仓库别名 仓库分支名
> > git push 仓库别名 仓库分支名

