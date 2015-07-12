##### Meteor 是一个建立现代网站的超简单的环境。搭建这样的网站，以前即使利用最好的工具也要几个星期，但是现在利用meteor，几个小时就可以了。

web的工作方式跟20世纪70年代最初的设计是一样的。应用程序的服务器渲染页面，然后通过网络把它发送到不智能的终端设备。不管用户做了什么，服务器总是渲染整个页面。这样的模式在10多年内没有什么问题。它催生了LAMP，Rails，Django，PHP等框架或者语言。

但是最好的团队，有着最大的预算和最长的规划，现在利用运行在客户端的JavaScript来建立应用。这些应用有着一流的借口。它们不会重新加载页面。它们是响应式的：来自一个人的客户端的改变可以呈现在每个人的屏幕上。

传统的方式用艰难的方法来建立这样的应用。Meteor使得它容易了一个数量级，并且还有很多的趣味。你可以在一个周末之内，或者在一个极其吸引人的黑客马拉松中，建立一个完整的应用。你不在需要停工服务器资源，或者在云平台上部署API接口，或者维护一个数据库，或者争论一个ORM层，或者在JavaScript和Ruby之间切换来切换去，或者把数据无效广播到客户端。

# 快速开始
Meteor支持[OS X，Windows，和Linux](https://github.com/meteor/meteor/wiki/Supported-Platforms)

安装在Windows上？[在这里下载官方Meteor安装器](https://install.meteor.com/windows)。

安装在OS X或者Linux上？在你的终端安装最新的官方Meteor发布版本：
```
curl https://install.meteor.com/ | sh
```

Windows安装器支持Windows 7，Windows 8.1，Windows Server 2008，还有Windows Server 2012。命令行安装起支持Mac OS X 10.7 （Lion）和以上的版本，还有Linux在X86和X86_64架构上的Linux。

一旦你安装了Meteor，可以用以下命令创建应用工程：
```
meteor create myapp
```

本地运行：
```
cd myapp
meteor
#Meteor服务运行在：http://localhost:3000/
```

向全世界发布：
```
meteor deploy myapp.meteor.com
```

# 关于Meteor的几个原则

- 传送的是数据。Meteor不会通过网络传送HTML。服务器传送的是数据并且让客户端渲染它。
- 一种语言。Meteor让你使用JavaScript来写客户端和服务器的代码。
- 无处不在的数据库。无论是客户端还是服务器，你都可以使用相同的方法来访问数据库。
- 延迟补偿。在客户端，Meteor预取数据并且模仿模型使得它表现得像时服务器的方法调用得到即时的返回一样。
- 全栈响应。在Meteor，实时时默认的。所有的层次，从数据库到模版，都会在需要的时候更新自身。
- 完整的生态系统。Meteor时开源的并且可以集成存在的开源工具和框架。
- 简单就是生产力。使得事物看起来简单的最好方法是让它真正地简单。
- Meteor的主要的函数有着干净，典型漂亮的API接口。

# 开发者资源

如果Meteor有什么吸引了你的兴趣的话，我们希望你能参与到这个project中来。

####教程

利用[Meteor官方教程](https://www.meteor.com/install)快速开始吧！

####STACK OVERFLOW

提问（并且回答）技术问题的最好的地方是[STACK OVERFLOW](http://stackoverflow.com/questions/tagged/meteor)。提问Meteor相关问题的时候要确保加上‘Meteor’的标签。

####论坛

访问[Meteor discussion forums](https://forums.meteor.com/)来宣布你发布了项目，寻求帮助，谈论社区，或者讨论核心的变化。

####GITHUB

Meteor的核心代码在[GitHub](https://github.com/meteor/meteor)上。如果你有能力写代码或者文件的问题我们很愿意得到你的帮助。为了上手，请先阅读[Contributing to Meteor](https://github.com/meteor/meteor/wiki/Contributing-to-Meteor)

THE METEOR MANUAL
In-depth articles about the core components of Meteor can be found on the Meteor Manual. The first article is about Tracker, our transparent reactivity framework. More articles (covering topics like Blaze, Unibuild, and DDP) are coming soon!





