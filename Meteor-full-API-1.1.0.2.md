##### Meteor 是一个建立现代网站的超简单的环境。搭建这样的网站，以前即使利用最好的工具也要几个星期，但是现在利用meteor，几个小时就可以了。

web的工作方式跟20世纪70年代最初的设计是一样的。应用程序的服务器渲染页面，然后通过网络把它发送到不智能的终端设备。不管用户做了什么，服务器总是渲染整个页面。这样的模式在10多年内没有什么问题。它催生了LAMP，Rails，Django，PHP等框架或者语言。

但是最好的团队，有着最大的预算和最长的规划，现在利用运行在客户端的JavaScript来建立应用。这些应用有着一流的借口。它们不会重新加载页面。它们是响应式的：来自一个人的客户端的改变可以呈现在每个人的屏幕上。

传统的方式用艰难的方法来建立这样的应用。Meteor使得它容易了一个数量级，并且还有很多的趣味。你可以在一个周末之内，或者在一个极其吸引人的黑客马拉松中，建立一个完整的应用。你不在需要停工服务器资源，或者在云平台上部署API接口，或者维护一个数据库，或者争论一个ORM层，或者在JavaScript和Ruby之间切换来切换去，或者把数据无效广播到客户端。


Quick start!
Meteor supports OS X, Windows, and Linux.
On Windows? Download the official Meteor installer here.
On OS X or Linux? Install the latest official Meteor release from your terminal:
curl https://install.meteor.com/ | sh
The Windows installer supports Windows 7, Windows 8.1, Windows Server 2008, and Windows Server 2012. The command line installer supports Mac OS X 10.7 (Lion) and above, and Linux on x86 and x86_64 architectures.
Once you've installed Meteor, create a project:
meteor create myapp
Run it locally:
cd myapp
meteor

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
```








