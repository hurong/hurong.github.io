---
title: git命令用于自己查找
date: 2017-05-05 09:47:11
tags:
---

git命令
=========

**直接用git clone ssh协议地址 克隆远程库的master分支，但是这样无法clone所有分支，可以用一下方法解决。**

>
1. 找一个干净目录，假设是git_work
2. cd git_work
3. git clone http://myrepo.xxx.com/project/.git ,这样在git_work目录下得到一个project子目录
4. cd project
5. git branch -a，列出所有分支名称如下：
remotes/origin/dev
remotes/origin/release
6. git checkout -b dev origin/dev，作用是checkout远程的dev分支，在本地起名为dev分支，并切换到本地的dev分支
7. git checkout -b release origin/release，作用参见上一步解释
8. git checkout dev，切换回dev分支，并开始开发。
> 

**git clone 仓库中的一个分支**

> 
> git clone -b <branch> <remote_repo> 


**git 推送本地分支到远程新分支上**

>git push origin local_branch:remote_branch
这个操作，local_branch必须为你本地存在的分支，remote_branch为远程分支，如果remote_branch不存在则会自动创建分支。
类似，git push origin :remote_branch，local_branch留空的话则是删除远程remote_branch分支。


**git本地分支与远程分支关联的方法***

>github上已经有master分支 和dev分支
在本地
git checkout -b dev 新建并切换到本地dev分支
git pull origin dev 本地分支与远程分支相关联
在本地新建分支并推送到远程
git checkout -b test
git push origin test   这样远程仓库中也就创建了一个test分支
>


当我们在本地新建一个叫devtest的分支的时候，我们希望他与git远程上的某个分支进行关联。
>git branch --set-upstream-to origin/devtest devtest 



**git一般的步骤**
>1. 克隆代码
git clone https://github.com/XXX.git  
2. 查看所有分支
git branch --all  # 默认只有master分支，所以会看到如下两个分支# master[本地主分支] origin/master[远程主分支]# 新克隆下来的代码默认master和origin/master是关联的，也就是他们的代码保持同步
3. 创建本地新的dev分支
git branch dev  # 创建本地分支
git branch  # 查看分支# 这是会看到master和dev，而且master上会有一个星号# 这个时候dev是一个本地分支，远程仓库不知道它的存在# 本地分支可以不同步到远程仓库，我们可以在dev开发，然后merge到master，使用master同步代码，当然也可以同步
4. 发布dev分支
发布dev分支指的是同步dev分支的代码到远程服务器
git push origin dev:dev  # 这样远程仓库也有一个dev分支了
5. 在dev分支开发代码
git checkout dev  # 切换到dev分支进行开发# 开发代码之后，我们有两个选择# 第一个：如果功能开发完成了，可以合并主分支
git checkout master  # 切换到主分支
git merge dev  # 把dev分支的更改和master合并
git push  # 提交主分支代码远程
git checkout dev  # 切换到dev远程分支
git push  # 提交dev分支到远程# 第二个：如果功能没有完成，可以直接推送
git push  # 提交到dev远程分支# 注意：在分支切换之前最好先commit全部的改变，除非你真的知道自己在做什么
6. 删除分支
git push origin :dev  # 删除远程dev分支，危险命令哦# 下面两条是删除本地分支
git checkout master  # 切换到master分支
git branch -d dev  # 删除本地dev分支


