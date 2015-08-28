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

#### Meteor使用手册
深入介绍Meteor核心组件的文章可以在[Meteor使用手册](http://manual.meteor.com/)上找到。第一篇文章是关于[Tracker](http://manual.meteor.com/#tracker)的，我们的显而易见的响应式框架。更多的文章（囊括比如Blaze，Unibuild，DDP主题的）很快就会写出来。

# 重要概念

我们已经亲手写过单页面的Javascript应用了。用一种语言和一种数据格式写整个应用真的很有趣。Meteor就是用来让我们写这样的应用的。

## Meteor是什么？

Meteor就是以下两点：

*  一个*packages的库*：你的应用需要的，预先写好的，独立的模块。  
   
   绝大部分应用会使用大概十几个Meteor的核心packages。举两个例子：[webapp][]，管理即将到来的HTTP链接，还有，templating，有数据改变的话会自动更新template。也有一些可选的packages，比如email，能让你的应用发送邮件，或者Meteor Accounts系列（accounts-password, accounts-facebook, accounts-ui等）能提供功能完整地用户账户管理系统，这些你都可以加到你的应用中去。除了这些“核心”packages，在[Atmosphere][]，你能找到你需要的packages，在那有成千上万的产生于Meteor社区的packages。

[webapp]: http://docs.meteor.com/#webapp 'webapp'
[Atmosphere]: https://atmospherejs.com/ 'Atmosphere'

*  一个叫做`meteor`的命令行工具  
   
   `meteor`是一种搭建工具，类似于`make`，`rake`，或者Visual Studio的非视觉部分。`meteor`能集中你的应用里面的所有源代码和资源，执行一些需要的构建步骤（比如编译[CoffeeScript][]，压缩CSS，建立[npm][]模块，或者生成source map），取得你的应用需要用到的packages，最后输出一个独立的，准备运行的应用程序包。在开发模式中它可以交互地完成这些工作，因此每当你改变一个文件的时候，你可以马上看到浏览器的变化。这是超级容易使用的，但是它同时也是可拓展的：你可以添加新语言支持，并且通过添加搭建插件packages来编译。
   
   Meteor package系统的关键之处是：*所有package都应该在浏览器端和服务器端独立的工作*（当然指的是能发挥作用的地方，毕竟浏览器没有邮件发送功能，服务器也不能捕获鼠标事件）。我们已经搭建整个生态系统来支持这个关键之处。
   
[CoffeeScript]: http://coffeescript.org/ 'CoffeeScript'
[npm]: https://npmjs.org/ 'npm'

## 构建你的应用程序

一个Meteor应用程序就是运行在web浏览器或者PhoneGap移动应用中的客户端JavaScript、运行在Meteor server中的Node.js的服务器端的JavaScript、还有所有支持的HTML模板、CSS规则、静态自愿。Meteor自动化地打包和转换不同的组件，让你灵活地在你的文件中选择如何构建这些组件。

### 特殊目录

在你的Meteor文件夹下的所有JavaScript文件都会打包并且发送到客户端和服务端。可是，在你的项目中的以下这下文件和目录的名字将会影响它们的加载顺序、影响它们会被加载到哪里、和一些其他的特性。以下是会被Meteor特殊对待的文件和目录的列表。

* **client**  

  名为client的任何目录都不会加载到服务端。类似于把你的代码放到`if (Meteor.isClient) { ... }`中去。处于生产模式时，加载到客户端的所有文件都会被自动合并和压缩。当处于开发模式时，JavaScript和CSS文件不会被压缩，这使得调试更容易。（为保证生产和开发时的一致性，CSS文件仍然会被合并到一个单独的文件中去，因为改变CSS文件的URL会影响它如何处理这些URL）
  
  Meteor应用中的HTML文件处理方式与服务端框架对其的处理方式有很大的差异。Meteor扫描你的目录中的所有的HTML文件，找到三个最高级别的元素：`<head>, <body>, <template>` 。`<head>`和`<body>`部分分别被合并到一个单独的`head`和`body`中，当初始页面加载时被发送到客户端。
  
* **server**  
  
  名为server的任何目录都不会加载到客户端。类似于把你的代码放到`if (Meteor.isServer) { ... }`中去，客户端从不会接收到代码。任何敏感的，你不想放到客户端的代码，比如包含密码和授权机制的代码，应该放到server目录中。
  
  Meteor会收集，除了在client、public和private子目录中的，所有的JavaScript文件，并且把他们加载到一个Node.js服务器实例中。Meteor的服务端对每一个请求都是用单线程处理的，而不是用Node的异步回调的处理方式。在Meteor应用中，线性执行更适合典型的服务端代码。

* **public**  
  
  主目录下的public文件夹中的所有文件是客户端的静态资源。当引用这些资源的时候，URL中不要包含 `public/`，把URL当成是处于主目录下面一样来写。比如，在`<img src='/bg.png'>`中引用`public/bg.png`。这是存放`favicon.ico, robots.tex`和类似文件的最佳位置。
  

  
* **private**  
  
  主目录下的private文件夹中的所有文件，只能被server端的代码使用，也可以通过[Assests] API来加载。这里可以存放私有数据或者项目中不想被外界访问的文件。
  
[Assests]: http://docs.meteor.com/#assets 'assests'

* **client/compatibility**  
  
  这个文件夹用来存放兼容的，依赖var声明的全局变量的JavaScript类库。在这个目录下的文件执行的时候无需包裹在一个新的变量空间。这些文件在客户端的JavasScript文件之前执行。
  
* **tests**  
  
  客户端和服务端任何命名为tests的目录。可以使用这个目录来存放本地测试代码。
  
### 特殊目录以外的文件  

在特殊目录以外的JavaScript文件会同时加载到客户端和服务端。这些地方可以定义model和其他函数。Meteor提供变量 `Meteor.isClient`和`Meteor.isServer`，所以你的代码可以依赖于在客户端还是服务端运行来改变行为。

特殊目录外的CSS和HTML文件只会被加载到客户端，在客户端不会被使用。

### 文件结构例子

你的Meteor应用的文件结构其实是很灵活的。这是一个运用上面提到的特殊目录的示例。

```
lib/                      # 存放比如collections和utilities这样的公共代码
lib/methods.js            # Meteor.methods.js定义
lib/constants.js          # 代码使用的常量

client/compatibility      # 全局的JavaScript类库
client/lib/               # 客户端首先加载的代码
client/lib/helpers.js     # 客户代码有用的helpers
client/body.html          # <body>标签内的内容
client/head.html          # <head>标签内的内容：<meta>标签等
client/style.css          # 一些CSS代码
client/<feature>.html     # 某个功能的HTML模板
client/<feature>.js       # 某个功能的JavaScript代码

server/lib/permissions.js # 服务端使用的敏感的权限代码
server/publications.js    # Meteor.publish定义

public/favicon.ico        # 应用图标

settings.json             # 传给命令meteor --settings的配置数据
mobile-config.js          # 为Android/iOS定义icons和元数据
```

你也可以在示例应用之外建立你的目录结构。执行`meteor create --example todos`，探索一下它的文件目录，看看真实应用所有的文件都到哪去了。


