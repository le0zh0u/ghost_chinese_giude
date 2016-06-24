# 开始Ghost

Ghost是给你一个更简单、更有趣的方式来编辑和上传你自己文章的开源平台。这篇指南会带你走过从安装Ghost到使用Markdown写第一篇文章的所有坑。

### 第一步：安装并启动Ghost

在开始Ghost之前，首先要安装它。这里有不少安装Ghost的方式，取决于你要装在哪个系统上。这篇文档着重于以手动的方式在标准的Linux VPS上运行Ghost。

另外，如果你是一名开发者，你可以在GigHub上的[Ghost README](https://github.com/TryGhost/Ghost#ghost-)文档中找到基础开发安装步骤。或者你只是想把Ghost安装在你自己的电脑玩玩，那么你看看我们关于在[Mac](http://support.ghost.org/installing-ghost-mac/)或者[Windows](http://support.ghost.org/installing-ghost-windows/)上安装的说明。

除了手动安装，还有很多选项，例如使用[Bitnami](https://wiki.bitnami.com/Applications/BitNami_Ghost)，[Rackspace deployments](http://developer.rackspace.com/blog/launch-ghost-with-rackspace-deployments.html) 或者 [DigitalOcean one-click install](https://www.digitalocean.com/community/tutorials/how-to-use-the-digitalocean-ghost-application)。在[部署Ghost](http://support.ghost.org/deploying-ghost/)这篇文章中有更多的部署方式可供参考。

##### 在你的Linux VPS上获取Ghost

本片剩下的部分是建立在你能通过命令行界面（terminal window）访问Linux VPS 并知你你的VPS的IP地址。

浏览关于[在Linux上安装Ghost](http://support.ghost.org/installing-ghost-linux/)的文章。

按照说明当中的关于[安装Node](http://support.ghost.org/installing-ghost-linux/#install-node)和[安装Ghost](http://support.ghost.org/installing-ghost-linux/#install-ghost)部分的文章进行操作。根据你Linux的使用习惯进行安装node，但是安装Ghost应一直按照相同的3个步骤和运行命令

	npm start --production
	
一旦已已经完成了Ghost的安装和运行，那就是时候好好玩耍了!

### 第二步：第一次运行

当你已经开始运行Ghost时，你将使用你的浏览器访问它，并开始创建你的admin帐号，以便你能发布内容到你的博客上。为了这个，你需要访问`http://localhost:2368/ghost/signup`，并填写表单。如果需要更多关于在Ghost第一次运行时遭遇的情况的相关信息，请看[第一次运行Ghost](http://support.ghost.org/ghost-first-run/)。

### 第三步：Ghost基础配置

如果你是自己托管Ghost，你需要配置一些信息。如果你使用Ghost(Pro)，你可以忽略这个步骤（或者你想看看[Ghost(Pro)创建说明](http://support.ghost.org/getting-started-ghost-pro/)而不是本篇说明）。

你可以在`config.js`文件中配置你的博客。这个文件被创建于你第一次开始Ghost，创建在Ghost的根目录下。如果你按照这Linux的安装教程，它将会被安装在`/var/www/ghost/config.js`。如果你还没有运行Ghost，你可以运行命令行`cp config.example.js config.js` 来创建一个`config.js`文件。

有两块关键部分需要你配置：你博客的URL和电子邮件设置。URL是必须的，否则你会找到许多连接，将你带到默认页面`http://my-ghost-blog.com`。如果不配置电子邮件，Ghost也能运行，但是我们推荐你加上它们。

你将需要使用一种文本编辑器来编辑配置文件。在Linux上有一种通用的用法是nano，因此输入`nano config.js`来编辑config.js 文件。修改在`production: { }`中的配置项，并且按下`Ctrl + x`。当你完成配置时，最终按下`Y`和`enter`来保存和退出。

如果要了解配置选项的所有细节，可以看[配置Ghost](http://support.ghost.org/config/)和[电子邮件配置](http://support.ghost.org/mail/)文档。

### 第四步：高级配置

一旦Ghost完成了安装、运行和配置，你需要一些方法来确保Ghost保持运行状态、在自定义域名中可访问和是安全的。

##### 将Ghost作为长期运行的进程

类似Ghost的Node应用程序将只会呆在你打开的当前命令行中。这里有许多配置Ghost的选项来让它保持运行，例如使用forver或者pm2。它们在[部署Ghost](http://support.ghost.org/deploying-ghost/)文章中被记录下来。我们推荐阅读[初始化脚本](http://support.ghost.org/deploying-ghost/#init-script)的方法。

##### 使用nginx代理域名

在设置了Ghost作为长期运行的进程后，下一步是使用网络服务器作为代理来配置一个自定义域名。我们推荐使用[nginx](http://nginx.org/en/)和参照我们的[nginx基础配置](http://support.ghost.org/basic-nginx-config/)指南中的步骤。

	注意：
	千万不要直接在80端口中启动Ghost。这被认为存在一种安全风险。我们经常推荐使用一种代理，例如nginx。

##### 配置SSL

最后，如果你已经在空间中配置了nginx，我们也强烈推荐[配置SSL](http://support.ghost.org/setup-ssl-self-hosted-ghost/)。这是对于Ghost管理员格外重要，通过它你能更安全的登录。为管理员如何使用多种租户地配置SSL的细节在[配置Ghost](http://support.ghost.org/config/#ssl)的指南中SSl部分中被找到。关于配置nginx的详细说明在[ssl配置](http://support.ghost.org/setup-ssl-self-hosted-ghost/)指南中。

### 下一步做什么

[开始使用Ghost](http://support.ghost.org/how-to-use-ghost/)!



本文翻译自[Ghost官方文档](http://support.ghost.org/getting-started/)，如有错误请指正，如造成侵犯，请联系我——<leozhou2015@163.com>。


