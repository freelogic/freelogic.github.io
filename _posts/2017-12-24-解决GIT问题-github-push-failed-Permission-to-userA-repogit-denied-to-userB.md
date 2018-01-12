---
layout: post
title: 20171224-解决GIT问题-github-push-failed[Permission to userA/repo.git denied to userB]
key: 20171224
tags: GIT 问答 版本管理
modify_date: 2017-12-24
---

# 问题：
* 当从本地push代码到远端github仓库，报“remote: Permission to userA/repo.git denied to userB.”

# 分析：
* 本地和github有ssh和https两种认证模式。如果是https模式，当IDE(pycharm等)做一次push会要求你输入github的账号密码，并会保存到win10本地，如果下次用另一个github账号push就会发生这个问题。
* 同理，除了https简单方式，ssh需要生成公钥秘钥对，公钥放github的repo仓库中，私钥放本地来让github认证你本地身份，如果其他人用了你的公钥，也会发生此问题（我未遇到过此情况，请另查！）

# 解决：
* [https方式下解决github的push账号问题](http://blog.csdn.net/klxh2009/article/details/76019742)
  * 注意：WIN10下面可以输入“管理windows凭据”字符串来找到github保存的账号密码信息并删除它！


