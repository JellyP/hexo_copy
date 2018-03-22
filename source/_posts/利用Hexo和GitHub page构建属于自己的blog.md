---
title: 利用Hexo和GitHub page构建属于自己的blog
categories: [web]
tags: [Hexo,github]
---

今天给大家介绍的就是我这个blog的具体构建方式，让一个小白借助GitHub page和hexo，一步一步地实现属于自己的blog，并绑定自己的域名。

#### <h3>前期准备：</h3>

##### <h4>1. Github：</h4>

首先你需要创建一个属于自己的GitHub，[注册页面](https://github.com/)如下，而GitHub page可以认为是用户编写的、托管在github上的静态网页，首先它可以绑定你的域名；其次简单快捷，使用Github Pages可以为你提供一个免费的服务器，免去了自己搭建服务器和写数据库的麻烦，是一个很好的搭建blog的平台。

![1](利用Hexo和GitHub page构建属于自己的blog\1.png)

</br>

##### <h4>2. node.js</h4>

在[node.js](https://nodejs.org/en/) 的官网上，如下所示，选择左边的稳定版下载即可，安装过程一直next即可，较为简单，不做过多赘述。

![2](利用Hexo和GitHub page构建属于自己的blog\2.png)

<br>

<h4>3. Git</h4>

首先需要上[官网](https://git-scm.com/download)选择自己的系统进行下载，可以参考[安装教程](https://jingyan.baidu.com/article/90895e0fb3495f64ed6b0b50.html) ，然后安装完成之后，，在任意文件夹（包括桌面）点击鼠标右键，即可看到如下两个选项。我们要使用的是Git Bash Here选项。更多关于git的操作可以参考[Git入门教程](http://git.oschina.net/progit/) 。

![2](利用Hexo和GitHub page构建属于自己的blog\3.png)

<br>

<h3>Hexo的安装和配置</h3>

首先，Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页，所以说借助Hexo，我们可以方便的实现属于自己的博客。

<h4>1. Hexo安装</h4>

首先选择一个文件夹，表示你要安装Hexo的路径，然后鼠标右键，点击Git Bash Here，然后输入如下的npm命令：

```sh
npm install hexo-cli -g
npm install hexo --save
#如果命令无法运行，可以尝试更换taobao的npm源
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

安装完成后应该会出现npm的文件夹。

</br>

<h4>2. Hexo初始化配置</h4>

安装完成后，根据自己喜好建立目录（如`F:\Blog\Hexo`），直接进入`F:\Blog\Hexo`文件夹下右键鼠标，点击`Git Bash Here`，进入Git命令框，执行以下操作。

```shell
hexo init
npm install
```

![2](利用Hexo和GitHub page构建属于自己的blog\4.png)

然后再输入如下指令来安装插件，为了方便，将所有插件安装即可：

```shell
npm install hexo-generator-index --save
npm install hexo-generator-archive --save
npm install hexo-generator-category --save
npm install hexo-generator-tag --save
npm install hexo-server --save
npm install hexo-deployer-git --save
npm install hexo-deployer-heroku --save
npm install hexo-deployer-rsync --save
npm install hexo-deployer-openshift --save
npm install hexo-renderer-marked@0.2 --save
npm install hexo-renderer-stylus@0.2 --save
npm install hexo-generator-feed@1 --save
npm install hexo-generator-sitemap@1 --save
```

最后如果想在本地查看效果的话，再在git命令框中输入

```shell
hexo generate
hexo server
```

然后打开网页，在网页链接中输入`localhost:4000`，就可以看到本地的效果如下。

![2](利用Hexo和GitHub page构建属于自己的blog\5.jpg)

<br>

<h3>博客的美化</h3>

虽然博客已经可以在本地运行了，但是其实样式都还是默认的，那么要怎么进行美化呢，在这里推荐一种最简单的方式：

- 进入[Hexo官网主题专栏](https://hexo.io/themes/)。

![2](利用Hexo和GitHub page构建属于自己的blog\6.png)

- 然后选择自己喜欢的主题，在这里以nayo为例，点进去之后可以看到页面为如下显示，

![2](利用Hexo和GitHub page构建属于自己的blog\7.png)

然后预览如果觉得合适的话，那么进入到刚才Hexo放置的目录，找到themes文件夹，例如`F:\Blog\Hexo\themes`，然后右键，选择Git Bash Here，然后输入：

```sh
git clone https://github.com/Lemonreds/hexo-theme-Nayo(这里指的是你点进去主题的那个网页的网址)
```

然后会发现themes文件中多了一个为`hexo-theme-Nayo`的文件夹，然后打开`F:\Blog\Hexo`下的_config.yml（用记事本或者sublime等工具打开），找到theme，修改参数为：`theme:hexo-theme-Nayo`。 

然后就是定制属于自己的blog，首先对于那些有分类、标签、关于等目录的主题，Hexo 默认不生成 `categories/tags/about` 等页面,需要自己创建页面。首先进入到Hexo的目录下，右键选择`Git Bash Here`，然后输入：

```sh
hexo new page categories ##表示分类页
hexo new page tags ##表示标签页
hexo new page about ##表示关于页
```

然后进入到`F:\Blog\Hexo\source`文件夹，发现多了三个文件夹，分别是categories、tags和about，里面都有一个index的md文件，然后增加一个layout属性：

```markdown
---
title: categories/tags/about
date: 2018-03-01 12:57:53
layout: category/tag/about
---
```

这里是对三个文件都做一次操作即可。



然后打开`F:\Blog\Hexo\themes\hexo-theme-nayo`，在`_config.yml`中修改相应的属性，即可定制属于自己的博客，然后可以在git输入框中输入

```shel
hexo generate
hexo server
```

然后打开`localhost:4000`进行查看效果。如果满意，那么我们就可以把他部署到我们自己的GitHub上面了。



<h3>将本地的网页上传到GitHub上</h3>

<h4>1. GitHub账号的注册</h4>

首先需要注册一个GitHub账号，注册的过程较为简单在这里略过。

<h4>2. 创建项目代码库</h4>

- 注册完成后，就需要创建一个自己的GitHub page项目了，点击New repository。

![2](利用Hexo和GitHub page构建属于自己的blog\8.png)

然后根据下图来配置仓库信息，最后点击下方的`Create repository`，完成创建。 

![2](利用Hexo和GitHub page构建属于自己的blog\9.png)

<h4>3. 配置SSH密钥</h4>

这里的目的是为了让你的本地git仓库能够和你的GitHub建立联系。对于以前使用过git来上传代码的用户，这一步可以忽略，但是对于新用户来说，要怎么配置git的ssh呢？

- 首先，我们需要看看是否看看本机是否存在SSH keys,打开Git Bash,并运行:

```powershell
cd ~/.ssh
```

如果存在则可以不用创建新的SSH密钥，如果不存在，则进入下一步。

- 存在的话可以忽略此步，我们可以通过如下指令创建按照你提供的邮箱的一对密钥：

```powershell
ssh-keygen -t rsa -C "your_email@example.com"

Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/you/.ssh/id_rsa): [Press enter]
```

然后回车之后，则将密钥按默认文件位置进行存储。

然后根据提示，输入密码和确认密码，相关提示为：

```
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
```

完成之后，运行如下命令将密钥复制到系统粘贴板中。

```powershell
clip < ~/.ssh/id_rsa.pub
```

至此，你已经拥有了一个自己的密钥了。

- 拿到密钥以后，你就可以登录GitHub，然后在settings->SSH and GPG keys->New SSH key。

![2](利用Hexo和GitHub page构建属于自己的blog\10.png)

然后输入标题和SSH key，输入相关信息。

![2](利用Hexo和GitHub page构建属于自己的blog\11.png)

- 为了测试是否成功，我们可以输入如下指令：

```powershell
ssh -T git@github.com
```

然后收到提示：

```shell
The authenticity of host ‘github.com (207.97.227.239)’ can’t be established. 
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48. 
Are you sure you want to continue connecting (yes/no)? 
```

然后直接输入yes即可，即可收到：

```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```



- 其实现在你已经可以通过SSH链接来连接到Github了，接着还可以完善一些个人信息，Git会根据用户的名字和邮箱来记录提交。GitHub也是用这些信息来做权限的处理，输入下面的代码进行个人信息的设置，把名称和邮箱替换成你自己的，名字必须是你的真名，而不是GitHub的昵称。

```sh
git config --global user.name "cnfeat"  ##用户名
git config --global user.email  "cnfeat@gmail.com"  ##填写自己的邮箱
```

到这里，你的电脑已经成功连接到了GitHub。



<h4>4. 将本地的Hexo文件更新到Github的库中</h4>

- 首先是点击Clone or download，然后复制SSH的链接。

![2](利用Hexo和GitHub page构建属于自己的blog\12.png)

- 然后打开Hexo文件夹下面的`_config.yml`文件，查找关键词`deploy`，修改成：

```sh
deploy:
  type: git  ##类型填写git
  repo: git@github.com:JellyP/JellyP.github.io.git ##添加一个repo，输入网址，
  branch: master ##添加一个branch，输入master
```

值得注意的是，每个关键字后面要接着一个空格再接信息。

然后在Hexo的目录下，右键选择 Git Bash Here，然后输入

```sh
hexo clean
hexo g -d
```

然后你的本地博客就被部署到你的GitHub上啦，在浏览器中输入你建立的仓库的名字，即yourname.github.io，即可访问你自己的博客了。



<h3>使用markdown写自己的博客</h3>

Markdown 是一种轻量级的「标记语言」，它的优点很多，目前也被越来越多的写作爱好者，撰稿者广泛使用。看到这里请不要被「标记」、「语言」所迷惑，Markdown 的语法十分简单。常用的标记符号也不超过十个，这种相对于更为复杂的HTML 标记语言来说，Markdown 可谓是十分轻量的，学习成本也不需要太多，且一旦熟悉这种语法规则，会有一劳永逸的效果。在这里不介绍具体的markdown语法了，详情可以参考[markdown语法中文版](https://www.appinn.com/markdown/)。具体的写博客的过程可以参考如下步骤：

<h4>1. 前期准备</h4>

为了让自己在写博客的时候插入图片，首先打开Hexo的目录下的`_config.yml`文件，将里面的`post_asset_folder:`的属性设置为`true`。

然后在hexo目录下利用Git Bash Here执行

```sh
npm install hexo-asset-image --save
```

下载安装一个可以上传本地图片的插件。



<h4>2. 创建博客</h4>

在这里主要介绍创建博客的两种方式：

- 第一种方式，运行

```sh
hexo n "aaaa" ###比如你要写的文章的名字为aaaa
```

就会发现在`F:\Blog\Hexo\source\_posts`里不仅有aaaa.md文件，还有一个aaaa的文件夹。插入的图片放入aaaa文件夹里面。

- 第二种方式，直接在`F:\Blog\Hexo\source\_posts`文件夹例创建aaaa.md和aaaa文件夹即可。



<h4>3. 书写博客</h4>

为了给博客书写标题、标签等，并非直接命名即可，我们可以对于博客的markdown文件，在开头的地方，输入：

```markdown
---
title: aaaa
categories: [test]
tags: [aaa,bbb]
---
```

来对博客进行命名、分类、和插入标签。



<h4>4. 上传博客</h4>

在书写结束后，我们就可以直接上传到自己的GitHub了，也是利用指令:

```sh
hexo clean
hexo g -d
```



<h3>关联个性化域名</h3> 

也许你不想使用yourname.github.io这样的网址当做自己博客的域名，那么绑定个性化域名也是比较简单的操作，可以分为如下几个步骤：

<h4>1. 购买域名</h4>

首先可以购买一个域名，例如[阿里云](https://wanwang.aliyun.com/domain/?spm=5176.383338.1907008.1.LWIFhw)的网站，我们可以使用支付宝或者淘宝账号进行登录，也可以重新注册，然后查询域名，并进行购买

![2](利用Hexo和GitHub page构建属于自己的blog\13.png)



注意，为了要让域名生效，需要实名认证和输入个人信息模板。



<h4>2. 配置CNAME</h4>

在F:\Blog\Hexo\source文件夹下创建一个记事本文件CNAME.txt，然后输入你购买的域名，最后再修改CNAME.txt为CNAME（去除后缀）。

然后通过`hexo g -d`的方式进行提交，上传到GitHub。



<h4>3. 修改云解析DNS</h4>

在登录之后点击右上角头像，在左边栏选择 域名与网站->域名，然后选择自己购买的用来替换GitHub page的域名。

![2](利用Hexo和GitHub page构建属于自己的blog\14.png)

进入之后选择DNS修改，然后修改DNS为如下：
![2](利用Hexo和GitHub page构建属于自己的blog\15.png)

```sh
f1g1ns1.dnspod.net 
f1g1ns2.dnspod.net 
```



<h4>4. 域名解析</h4>

- 打开[DNSPOD](https://www.dnspod.cn/)注册一个账户。然后域名解析->添加域名->点击域名

![2](利用Hexo和GitHub page构建属于自己的blog\16.png)



- 然后为了得到自己GitHub page的ip，我们可以`win+R`输入`cmd`，输入

```sh
ping yourname.github.io
```

然后会得到一个IP，有可能是IPV6的信息，如果想要得到IPV4的ip信息可以使用：

```sh
ping -4 yourname.github.io
```

![2](利用Hexo和GitHub page构建属于自己的blog\17.png)

将IP地址复制，进入到点击域名后的界面。

- 最后在域名界面选择添加记录：对于IPV4的IP，类型选择A，添加两种主机记录，分别为@和`www`的类型；对于IPV6的IP，类型选择AAAA，添加两种主机记录，分别为@和`www`。

![2](利用Hexo和GitHub page构建属于自己的blog\18.png)

现在等待生效即可，最迟72小时，在网页上输入你购买的域名即可获得你自己的博客主页了。



<h3>写在最后</h3>

当你完成了这一系列之后，肯定心情还是比较开心和激动的，其实这只是属于你博客的刚刚开始，你还需要不断的往里面书写自己的文章，才能有助于博客的蓬勃发展，形式并非是重要的，只有靠内容才能够获得别人的认可，相信你在写博客的过程中会受益无穷的，有问题的话可以在留言板留言，或者联系我的邮箱：pengguodong0414@foxmail.com。







<h3>参考资料：</h3>

[小白独立搭建博客--Github Pages和Hexo简明教程](https://www.jianshu.com/p/15ae47eddc56)

[创建SSH密钥，并连接GitHub](http://blog.csdn.net/happystarycy/article/details/52490183)

[hexo生成博文插入图片](http://blog.csdn.net/sugar_rainbow/article/details/57415705)

