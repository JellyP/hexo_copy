---
title: Android studio的安装和配置
date: 2018-03-15 21:42:38
tags: [环境配置,git,Android]
categories: [Android]
---

在这篇文章里，主要内容是向你们介绍怎么安装和配置Android studio，使得最后能够新建项目和Android与GitHub相连接。

<h4>Android studio 的安装</h4>

Android studio的安装，你们可以参考一下这个网址[Android studio的安装和配置]()，建议将PDF下载之后进行查看。然后如果是首次安装的话，涉及到sdk的安装，hosts的修改，虚拟机的安装等，按着教程一步一步来应该是可以解决的。



<h4>配置Android studio中的git</h4>

首先需要在[官网](https://git-scm.com/download )下载git，然后安装之后记住安装路径（例如G:\github\Git\cmd\git.exe），然后打开Android studio，选择右上角file->settings，打开如下界面，具体操作步骤见下图：

![1](Android studio的安装和配置\1.png)



<h4>在Android studio中配置GitHub账号</h4>

同样和配置git一样，选择GitHub，输入已经注册好的GitHub账号，然后选择test，如果弹出connection successful，那么就证明配置成功了。

![1](Android studio的安装和配置\2.png)



<h4>在Android studio中导入GitHub的项目</h4>

在Android studio界面，选择如下的选项：

![1](Android studio的安装和配置\3.png)

然后如果已经登录了GitHub之后，那么就会弹出进行你GitHub上仓库的项目的选取，在选择好项目和路径之后，就可以克隆到本地了。

![1](Android studio的安装和配置\4.png)



<h4>将本地项目分享到GitHub上</h4>

为了更好的管理自己的代码，实现多人协作，我们可以将代码上传到GitHub上，和克隆代码类似，我们选择share project on github即可。

![1](Android studio的安装和配置\5.png)

确定好仓库名字和描述之后

![1](Android studio的安装和配置\6.png)

再选择好自己所要上传的文件，上传即可。

![1](Android studio的安装和配置\7.png)

然后打开自己的GitHub就能看到自己所新建的仓库和仓库内上传的新项目了。



Android studio的配置到这里就已经结束了，如果你还有什么问题欢迎联系我的邮箱pengguodong0414@foxmail.com或者留下你的评论。

