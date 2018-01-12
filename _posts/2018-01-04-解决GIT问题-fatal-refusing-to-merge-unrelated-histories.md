---
layout: post
title: 20180104-解决GIT问题-fatal-refusing-to-merge-unrelated-histories
key: 20180104
tags: GIT 问答 版本管理
modify_date: 2018-01-04
---

# 问题：
* 当从本地branch推送到多个远端GIT分支，并且通过手机直接online修改远端GIT仓库，同时也用本地PC修改远端GIT的本地分支，的复杂情况下。偶发问题提示：
````
fatal: refusing to merge unrelated histories
````

# 分析：
* 手机移动端直接修改GIT仓库文件，本地PC也修改，要同步pull/push的时候导致问题；
* 很可能是版本冲突，导致头版本HEAD不一致，无法接续；
* 具体问题待查（如下链接也并未给出非常确定的起因）

# 解决：
* 步骤：
  * 如果你在pycharm等IDE遇到问题，因为无法直接输入GIT命令，所以需要在GIT bash命令行方式下解决；
  * 如果你本来就在git bash命令行方式遇到的问题，那么就直接用如下方法解决；
  * 用命令"git pull origin master --allow-unrelated-histories"
      * origin是远端GIT仓库的名称(举例:gitee-webpost https://gitee.com/freelogic/webpost.git //用git remote -v查到此信息)；
      * master是远端GTI仓库的分支名字，一般为master(默认)，除非你改过。
      * 参数“--allow-unrelated-histories”显然就是对应于报错的，用来解决报错，必须要添加；
      * 举例：git pull gitee-webpost master --allow-unrelated-histories
  * 其他情况：
      * 如果还有问题，可能是具体的某个文件或目录的问题，请参照GIT提示给予解决，才能继续使用这条命令！
* 信息贴：
````
http://blog.csdn.net/lindexi_gd/article/details/52554159
http://blog.csdn.net/sela0708/article/details/71480076
https://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories

````