---
layout: post
title:  "Git基本操作"
date:   2016-08-23 17:48:54
categories: Git
comments: true
---

1.向远程分支推送：避免修改远程master影响别人工作。等都OK以后可以merge，和主分支合并

如果想把本地的某个分支test提交到远程仓库，并作为远程仓库的master分支，或者作为另外一个名叫test的分支，那么可以这么做。

$ git push origin test:master         // 提交本地test分支作为远程的master分支
$ git push origin test:test              // 提交本地test分支作为远程的test分支

如果想删除远程的分支呢？类似于上面，如果:左边的分支为空，那么将删除:右边的远程的分支。

$ git push origin :test              // 刚提交到远程的test将被删除，但是本地还会保存的，不用担心
$ git init : 将此文件夹初始化为git仓库



push的格式是git push <远程主机名> <源分支地址>:<目的分支地址>，如果源分支与目的分支已经关联或者没有对应的目的分支可省略冒号及冒号后的部分（例如git push origin 分支名不存在的远程分支会自动新建），如果源分支就是当前分支可省略源分支地址部分(例如git push origin)，如果远程主机只有一个，那么连远程主机名都可以省略（直接git push）   ---转自李嘉文
& git remote add origin +库网址   : 添加远程库,名字为origin
& git remote add teamone +库网址  : 添加远程库，名字为teamone
& git branch -a  ： 查看远程分支
& git remote :查看远程库
& git remote -v ：查看远程库克隆地址，比上面实用
& git remote rm origin :删除原来的远程库
& git remote show origin :查看远程分支

当远程代码被他人更新以后，自己的origin/master分支没有随之移动，所以需要fetch
& git fetch origin ： 自动获取远程服务器的“新加入的分支”
& git fetch teamone ：, Git fetches no data but sets a remote-tracking branch called teamone/master to point to the commit that teamone has as its master branch.
& git fetch origin master: 从远程的origin仓库的master分支下载代码到本地的origin master
& git fetch origin master:temp:从远程的origin仓库的master分支下载到本地并新建一个分支temp（如果本地存在temp，并且是`fast forward', 则自动合并两个分支, 否则, 会阻止以上操作.）
& git fetch <远程主机名><源分支地址>:<目的分支地址>
$ git fetch diff temp : 比较master分支和temp分支的不同
& git merge temp ：合并temp分支到master分支


& git push <remote> <branch> ：如果远程没有这个branch，会自动创建一个
& git merge origin/develop  ：将当前工作分支与远程的origin/develop合并

& git push [远程名] :[分支名]   如 git push origin :develop   删除远程分支（一个非常无厘头的方法）


pull的是从远程拉到本地，源分支应是远程分支，目的分支是本地分支。

$ git pull <远程主机名> <源分支地址>:<目的分支地址>  把特定的远程分支和特定的本地分支合并
$ git pull <远程主机名> <源分支地址>  把特定的本地分支和当前分支合并
$ git pull <远程主机名> 把与当前分支关联的远程分支合并进当前分支 
$ git pull  远程主机唯一时这么写就可以把当前分支和唯一的关联的远程分支合并


[]: 