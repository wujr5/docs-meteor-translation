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

### 文件加载顺序

最好让你的应用与文件的加载顺序无关，比如可以使用`Meteor.starup`，或者把与加载顺序密切相关的代码放到packages里面，这样可以显式控制控制加载顺序和它们的内容和它们相对于其他packages的加载顺序。可是有时候你的应用的加载顺序依赖是难以确定的。

有几种加载顺序规则。规则逐一应用于应用中的所有文件，优先级如下：

1. HTML模板文件总是在其他文件之前加载
2. 然后加载命名以`main`开头的文件
3. 再加载在lib目录下的文件
4. 接着处于更深路径的文件加载
5. 最后文件以完整路径的字母顺序加载

```
nav.html
main.html
client/lib/methods.js
client/lib/styles.js
lib/feature/styles.js
lib/collections.js
client/feature-y.js
feature-x.js
client/main.js
```

举个例子，以上的文件是以正确地加载顺序编排的。`main.html`排在第二加载是因为HTML模板总是首先加载，即使以`main.`开头，因为规则1优先级大于规则2.可是，它会在`nav.html`加载之后加载因为规则2优先级高于规则5。

`client/lib/styles.js`和`lib/feature/styles.js`由于规则4而有相同的加载顺序，可是，因为`client`在字母顺序上先于`lib`，它会先加载。


### 组织你的项目

根据功能和组件来组织文件有三种主要的方式。在我们下面的示例项目中，有两个对象：苹果和橙子。

#### 方法 1：根目录文件夹

因为`client`，`server`，`lib`目录不管在什么路径下都能起作用，你可以使用最高级别的文件夹来把代码组织成模块。

```
apples/lib/               # apple相关功能的代码
apples/client/
apples/server/

oranges/lib/              # orange相关功能的代码
oranges/client/
oranges/server/
```

#### 方法 2：放到**client/**和**server/**中的文件夹

```
lib/apples/               # oranges和apples项目的公用代码
lib/oranges/

client/apples/            # apples和oranges的客户代码
client/oranges/          

server/apples/            # apples和oranges的服务端代码
server/oranges/
```

#### 方法 3：Packages

这是实现代码分离，模块化，和重用性的最基本的方法。如果你把代码每个功能的代码都放到一个分开的package中，除非使用exports，否则一个功能的代码不能访问到另一个功能的代码，这使得独立性非常明显。这也允许功能的最简单的独立测试。你也可以发布这些packages，并且通过`meteor add`在多个应用中使用它们。

```
packages/apples/package.js     # apple功能的文件，依赖，exports
packages/apples/<anything>.js  # 文件夹在受package.js控制

packages/oranges/package.js    # orange功能的文件，依赖，exports
packages/oranges/<anything>.js # 文件加载受packege.js控制

```

## 数据和安全

Meteor使得编写分布式客户端代码就像在谈论本地数据库一样简单。它是一个干净简单和安全的方法，能够免去单独实现RPC（Remote Procedure Call）端的需求，在客户端手动缓存数据来避免慢速往返于服务器与客户端之间，并且当数据发变化时，能给每个客户端，小心地编排分发独立的消息。

在Meteor中，客户端和服务端使用相同的数据库API。相同的应用代码 - 就像验证器和计算属性 - 可以经常在同时运行在两个端。但是当服务端的代码能直接访问数据库，而客户端的代码不能。这种特征就是Meteor数据安全模型的基础。

> 默认情况下，一个新的Meteor应用会包括packages`autopublish`和`insecure`，这能使得客户端能读写客户端数据库。这些是用用的构建原型的工具，但对于产品应用来说是不合适的。你准备好的话，删掉这两个包吧。

每一个Meteor客户端包含一个内存中的数据库缓存。为了管理客户端缓存，服务器`publish`JSON文档集合，并且客户端需要`subscribes`这些集合。如果集合中的文档发生改变，服务端相应地改变每一个客户端的缓存。

今天几乎所有的Meteor应用都是用MongoDB作为它们的数据库，因为它得到了最好的支持，将来也会支持其他数据库。`Mongo.Collection`类用来尚明Mongo的collections和操纵它们。多亏了minimongo，Meteor的客户端的Mongo副本，`Mongo.Collection`可以在客户端和服务端代码中使用。

```
// 声明collections
// 代码应该存在于客户端和服务端
Rooms = new Mongo.Collection("rooms");
Messages = new Mongo.Collection("messages");
Parties = new Mongo.Collection("parties");

// 服务端：用初始化的文档填充collections
Rooms.insert({name: "Conference Room A"});
var myRooms = Rooms.find({}).fetch();
Messages.insert({text: "Hello world", room: myRooms[0]._id});
Parties.insert({name: "Super Bowl Party"});
```

在server端`publish`函数定义每一个文档集合。每当一个新的客户端订阅一个文档集合的时候，`publish`函数就运行。文档集合的数据可以来自任何地方，但是通常情况下`publish`一个数据库查询。

```
// 服务端：发布所有room文档
Meteor.publish("all-rooms", function () {
  return Rooms.find(); // everything
});

// 服务端：对一个给定的room发布所有messages
Meteor.publish("messages", function (roomId) {
  check(roomId, String);
  return Messages.find({room: roomId});
});

// 服务端：把parties集合发布给登录的用户
Meteor.publish("parties", function () {
  return Parties.find({$or: [{"public": true},
                             {invited: this.userId},
                             {owner: this.userId}]});
});
```

`publish`函数可以给每个客户端提供不同的结果。在上一个例子中，一个登录的用户仅能看到公开的，或者他拥有的，或者他被邀请的Party文档。

一旦订阅开始，客户端使用它的缓存作为一个快速地本地数据库，大大简化了客户端代码。读取数据不再需要访问服务器的代价了。他们同事限制缓存的内容：在客户端，对在collection中的每一个文档的查询，仅仅返回服务端`publish`给客户端的文档。

```
// 客户端：开始一个parties订阅
Meteor.subscribe("parties");

// 客户端：返回一个客户端可以读取的Parties数组
return Parties.find().fetch(); // 这是同步的!
```

复杂的客户端可以通过关闭或者打开订阅来控制缓存中的存储多少数据和控制网络流量。当一个订阅关闭的时候，所有它的文档会从缓存中移除，除非相同文档同样被其他打开的订阅提供。

当客户端改变一个或者多个文档的时候，它会发送信息给服务端请求发生改变。服务端在你写的就像JavaScript函数一样的`allow/deny`规则，检查这些改变请求。服务端接受改变请求，当且仅当所有规则都通过了。

```
// 服务端：不允许客户端插入一条party数据
Parties.allow({
  insert: function (userId, party) {
    return false;
  }
});

// 客户端：插入失败
var party = { ... };
Parties.insert(party);
```

如果服务端接受了改变，它会对数据库和应用这些改变，并且自动把这些改变广播给其他客户端，以调整文档。如果没有接受，更新失败，服务端数据库仍然没被改变，其他客户端也看不到这些改变。

可是Meteor有一个可爱的trick。当一个客户端发布对服务端的写入的时候，它也会马上更新本地缓存，而不需要等待服务端响应。这意味着屏幕会马上重绘。如果服务端接受了更新 - 在表现正常的客户端绝大部分情况下会接受 - 那么客户端会跳过变化并且不需要等待返回来更新屏幕。如果服务端拒绝更新，Meteor会把服务端结果分发给客户端缓存。

把这些技术放到一起，便实现了延迟补偿。客户端保留一个它们需要的最新的数据副本，不需要等待服务端的响应。当客户端修改了数据，这些修改可以在本地执行，不需要当代服务端确认，同时仍然通过请求变化给服务端最终的决定权。

> 当前的Meteor版本支持MongoDB，一个流行的文档数据库，在这部分的例子中使用了[MongoDB API][]。未来的版本会给其他数据库提供支持。

[MongoDB API]: http://www.mongodb.org/display/DOCS/Manual

### 授权和用户账户

Meteor包含`Meteor Accounts`，一个最先进的认证系统。它使用bcrypt加密算法来提供安全的密码登陆功能，与外部服务集成，包括Facebook，GitHub，Google，Meetup，Twitter和微博。Meteor Accounts定义了一个`Meteor.users`的集合，开发者可以使用它来存储应用程序特定的用户数据。

Meteor也为普通任务，比如登录、注册、修改密码和重新设置邮箱，包含了预置的形式。只需要一行代码，你就可以给你的应用添加`Accounts UI`。`account-ui`package甚至提供一个配置向导，带领你通过几个不走来设置你在应用中使用的外部登录服务。

### 输入验证

Meteor允许你的mothod和`publish`函数带有任何JSON类型的参数。（实际上，Meteor的连接协议hi吃EJSON，一个JSON的拓展，也能支持其他普通类型比如dates和binary buffers）JavaScript的动态类型意味着，你不需要在你的应用中为每一个变量声明精确地类型，但是，确保客户端传给你的method和publish函数的参数，是你希望的类型，往往是有用的。

Meteor提供了一个轻量级的库来检查你所期望的参数和其他值的类型。只需要在你的函数中写这样的语句：`check(username, String)`或者`check(office, {building: String, room: Number})`。如果它的参数是一个意想不到的类型的话，`check`的调用会抛出一个错误。

Meteor也提供一个容易的途径来确保所有你的method和publish函数验证它们所有的参数。只需要执行`meteor add audit-argument-checks`，任何method或者publish函数跳过检查所有它的参数的话，都会失败，并产生一个异常。

## 响应式

Meteor拥抱[响应式编程][]的概念。这意味着你可以用简单命令式风格来写你的代码，每当你的代码依赖的数据数据发生变化的时候，结果都会自动地被重新计算。

[响应式编程]: http://en.wikipedia.org/wiki/Reactive_programming

```
Tracker.autorun(function () {
  Meteor.subscribe("messages", Session.get("currentRoomId"));
});
```

这个例子（从一个聊天室应用客户端引用来的）设置了一个基于session变量`currentRoomId`的数据订阅。如果`Session.get("currentRoomId")`的值因为某些原因发生了改变，这个函数会自动重新执行，设置一个新的订阅来代替旧的。

这个自动的重新执行是通过`Session`和`Tracker.autorun`的合作来实现的。`Tracker.autorun`表现为一个任意的“响应式计算”，在它的内部，数据依赖是被追踪的，并且当有需要的时候，它会重新运行它的函数参数。数据提供者比如`Session`，在另一方面，记录这些它们被引用的computation和什么数据被请求，同时当数据发生改变的时候，它们会准备发送一个失效信号给这个computation。

这个简单地模式（响应式computation + 响应式数据源）有着广泛地应用。以上，程序员幸免于写`ubsubscribe/resubscribe`调用和确保它们在正确地时间被调用。通常来说，Meteor可以消除整个类别的数据传输代码，这些代码可能会因为简单地逻辑而阻塞你的应用。

这些Meteor函数作为响应式的computation来执行你的代码：

* Templates
* Tracker.autorun
* Blaze.render 和 Blaze.renderWithData

可以触发改变的响应式数据源：

* Session variables
* Database queries on Collections
* Meteor.status
* The ready() method on a subscription handle
* Meteor.user
* Meteor.userId
* Meteor.loggingIn

此外，下面的函数 - 如果在一个响应式的computation中调用的话，返回一个含有stop方法的对象 - 会被停止当computation被重新执行或者被停止的时候。

* Tracker.autorun (nested)
* Meteor.subscribe
* observe() and observeChanges() on cursors

Meteor是由一个相当简短的叫做`Tracker`的package来实现的。你可以使用它来实现新的响应式数据源。

## 实时刷新的HTML模板

HTML模板是web应用的核心。有了Blaze，Meteor的实时刷新网页的技术，你可以响应式地渲染你的HTML，意思是它可以自动更新来跟踪生成模板的数据的改变。

Meteor使得使用你喜欢的HTML模板语言，同时有着Meteor的实时网页刷新的技术，变得容易。你只需要正常地写模板，Meteor会让它实时刷新。

Meteor附带一种模板语言，叫做[Spacebars][]，源于[Handlebars][]。它带着Handlebars的一些特性和语法，但是，当编译开始的时候，它被定制来生成响应式的Meteor模板。

[Spacebars]: https://github.com/meteor/meteor/blob/devel/packages/spacebars/README.md
[Handlebars]: http://handlebarsjs.com/ 

> 今天，Meteor自带的仅有的模板系统是Spacebars，但我们的社区已经为其他的语言创建了packages，比如[Jade][]

[Jade]: https://atmospherejs.com/mquandalle/jade

为了定义模板，在你的项目中创建一个拓展名为`.html`的文件。在文件中，创建一个`<template>`的tag和给它设置一个`name`属性。把模板内容放到这个tag里面。Meteor会预编译这个模板，把它传送到客户端，和使它作为全局的模板对象而可以被访问。

当你的应用加载的时候，它会自动的渲染特定叫做`<body>`的模板，这个模板写在`<body>`元素中而不是`<template>`中。使用`{{> inclusion}}`操作符，你可以把一个模板插入到另一个模板当中。

把数据插入到templates中的最简单的方式是在JavaScript中定义`helper`函数。用`Template.templateName.helpers({ ... })`定义`helpers`。把它们放到一起。

```
// 在文件myapp.html中
<body>
  <h1>Today's weather!</h1>
  {{> forecast}}
</body>

<template name="forecast">
  <div>It'll be {{prediction}} tonight</div>
</template>
```

```
// 在client/myapp.js中: 响应式的helper函数
Template.forecast.helpers({
  prediction: function () {
    return Session.get("weather");
  }
});
```

```
// 在JavaScript的console中
> Session.set("weather", "cloudy");
> document.body.innerHTML
 => "<h1>Today's weather!</h1> <div>It'll be cloudy tonight</div>"

> Session.set("weather", "cool and dry");
> document.body.innerHTML
 => "<h1>Today's weather!</h1> <div>It'll be cool and dry tonight</div>"
```

可以使用`{{#each}}`来迭代数组和数据库cursor

```
// 在文件myapp.html中
<template name="players">
  {{#each topScorers}}
    <div>{{name}}</div>
  {{/each}}
</template>
```

```
// 在文件myapp.js中
Template.players.helpers({
  topScorers: function () {
    return Users.find({score: {$gt: 100}}, {sort: {score: -1}});
  }
});
```

在这种情况下，数据来自数据库查询。当数据库cursor传给`{{#each}}`的时候，它会连接所有的机械项来有效地添加或者移除DOM节点来作为输入查询的结果。

Helpers可以带有参数，他们在`this`中接受当前模板上下文数据。注意有些block helpers会改变当前上下文（尤其是`{{#each}}`和`{{#with}}`）:

```
// in a JavaScript file
Template.players.helpers({
  leagueIs: function (league) {
    return this.league === league;
  }
});
```

```
// in a HTML file
<template name="players">
  {{#each topScorers}}
    {{#if leagueIs "junior"}}
      <div>Junior: {{name}}</div>
    {{/if}}
    {{#if leagueIs "senior"}}
      <div>Senior: {{name}}</div>
    {{/if}}
  {{/each}}
</template>
```

Helpers也可以被用来传递数据常量。

```
// Works fine with {{#each sections}}
Template.report.helpers({
  sections: ["Situation", "Complication", "Resolution"]
});
```

最后，你可以在一个模板中使用events函数来绑定时间处理函数。传递给events的对象被记录在Event Maps中
。event处理函数的`this`变量，是触发该事件的元素的数据上下文。

```
// myapp.html文件
<template name="scores">
  {{#each player}}
    {{> playerScore}}
  {{/each}}
</template>

<template name="playerScore">
  <div>{{name}}: {{score}}
    <span class="give-points">Give points</span>
  </div>
</template>
```

```
// myapp.js
Template.playerScore.events({
  'click .give-points': function () {
    Users.update(this._id, {$inc: {score: 2}});
  }
});
```

要了解更多地关于Spacebars的细节，阅读[Spacebars README][]吧。

[Spacebars README]: https://github.com/meteor/meteor/blob/devel/packages/spacebars/README.md

## 使用Packages

到目前为止你所读到得功能都是在标准的Meteor packages实现的。多亏Meteor不同寻常的强大的同构package和构建系统，使得这变得可能。同构意味着相同的packages在web浏览器、手机应用、和服务端起作用，Packages也可以包含拓展构建过程的插件，比如`coffeescript`（[CoffeeScript][]编译）或者`templating`（编译HTML模板）。

[CoffeeScript]: http://coffeescript.org/

任何人都可以发布一个Meteorpackage，并且成千上万的社区写的package已经被发布了。浏览这些pakcages的最简单的方式是[Atmosphere][]，由Percolate Studio运营。你也可以使`meteor search`和`meteor show`命令。

[Atmosphere]: http://www.atmospherejs.com/

使用`meteor add`，你可以添加packages到你的项目中去，使用`meteor remove`来移除。此外，`meteor list`会告诉你你的项目正在使用什么packages，如果有更新的话，`meteor update`会把项目中的packages更新到最新的版本。

默认地所有应用会包括`meteor-platform`的package。这会自动地把组成核心Meteor栈的包拉进来。如果你想构建你自己自定义的栈，只需要从你的应用中移除`meteor-platform`，同时添加任何你想保留的标准packages。

Meteor使用一个简单装卸包装系统，意味着它只会加载每一个package的一个版本。在添加或者升级一个特定版本的package之前，Meteor使用一个约束解算器来检查这样做是否会导致其他package损坏。默认地，Meteor会选择保守地选择。当添加传递依赖关系（包是其他的包，但不是应用本身）时，Meteor会尝试选择更早的版本。

除了在官方Meteor发行版本的包在被你的应用使用之外，`meteor list`和`meteor add`也会在你的应用的顶层目录中搜索`packages`。为了方便，你也可以使用`packages`目录，把你的应用分解成若干个子package，或者用来测试你想发布的packages。详情请看[Writing Packages][]。

[Writing Packages]: http://docs.meteor.com/#writingpackages

## 命名空间

Meteor的命名空间支持使得它很容易用JavaScript写大规模的应用。你在你的应用中使用的每一个package都存在于它自己的分开的命名空间中，意味着它只能看到它自己的全局变量，和它特定使用的packages提供的任何变量。以下是工作原理。

当你声明一个最外层变量的时候，你有一个选择。你可以使得这个变量在文件作用域内或者Package作用域内。

```
// 文件作用域。这个变量在这个文件范围内是可视的。
// 这个应用的其他文件或package看不到它。
var alicePerson = {name: "alice"};

// Package作用域。
// 对于这个package或者应用的所有文件来说，这个变量是可视的
// 不同之处是省略了‘var‘声明
bobPerson = {name: "bob"};
```

注意这是声明一个局部或者全局变量的正常的JavaScript语法。Meteor扫描你的源代码来寻找变量赋值语句，同时产生包装来确保你的全局变量不会超出它们的适当的命名空间。

除了文件作用域和Package作用域，还有Exports。一个export就是一个当你使用它的时候package使得它可访问的一个变量。比如，`email` package输出`Email`变量。如果你的应用使用`email` package（当且仅当它使用`email` package！），那么，你的应用可以看到`Email`和你可以调用`Emali.send`。绝大部分的package都是仅有一个export，但是一些package可能有两到三个export（比如，比个提供几种一起工作的类的package）。

你可以只能看到你直接使用的package的export。如果你使用package A，同时package A使用package B，那么你仅仅能看到package A的export，package B的export没有加入到你的命名空间中，只是因为你使用的是package A。这能保证每一个命名空间都很好且简洁。每一个应用或者package仅仅只能看到他们自己的全局变量再加上它们特别要求的package的API。

当你调试你的应用的时候，你的浏览器的JavaScript控制台表现得就像它是依附在你的应用的命名空间一样。你能看到你的应用的全局变量，和你的应用直接使用的package的exports。你不能看到在package内部的变量，同时你不能考到你的传递依赖的export（不是你的应用直接使用的package，但是它们被你应用使用的其它包使用）。

如果你想在你的浏览器内部的调试器去看package的内部，你有两个选择：

* 在package代码中设置断点。当代码执行到断点的时候，控制台会在package的命名空间中。你会看到package的基于package的作用域下的变量，import，和你所停在的文件的文件作用域下的变量。

* 如果package `foo`包含在你的应用当中的话 ，不管是不是你的应用直接使用它，她的exports可以通过`Package.foo`访问到。比如，如果`email` package被加载进来，然后你可以访问`Package.email.Email.send`，甚至在你不会直接使用`email` package的命名空间中也是可以这样。

当声明函数的时候，记住，在JavaScript中，`function x() {}`只是`var x = function x () {}`的缩写。考虑一下例子：

```
// 这跟 'var x = function x () ...'是一样的。
// 所以x()是文件作用域的，只能在这一个文件之内被调用。
function x () { ... }

// 没有 'var'，所以x()是package作用域的，
// 可以在这个应用或者package内的任何文件中被调用
x = function () { ... }
```

> 在技术层面上说，在应用中（不是在一个pakcage中）的全局变量实质上是真正的全局变量。它们在应用代码的私有作用域中被捕获到，因为这样就意味着它们调试时在控制台中是不可见的！这样一位这应用的全局变量实际上最终只能在package层面上可见。这不应该是你正常写package代码的问题（因为应用的全局变量仍然可以被package中的声明所覆盖）。你一定不能依赖于这个奇怪的特性，在未来Meteor会给它添加检查，如果你这样用了，会抛出一个错误。


## 部署

Meteor是一个完整的应用服务。我们包含了所有你把应用部署到网上所需要的东西：你只需要提供JavaScript，HTML和CSS。

### 在Meteor的基础设施上运行

部署你的应用的最简单的方法就是使用`meteor deploy`。我们提供这个功能是因为，就我们来说，这一直是我们想要的：给这样的过程提供简单地方式：有了一个想法，在一个周末把它做出来，然后把它放到一个全世界都可以使用的地方，不会有什么东西阻挡创造力。

`meteor deploy myapp.meteor.com`

你的应用现在已经可以在myapp.meteor.com上了。如果这是第一次部署到这个主机名上，Meteor会创建一个新的空数据库给你的应用。如果你想要部署一个更新，Meteor会保存原来的存在的数据库，并且只更新代码。

你也可以部署到你自己的域名上去。只需要把你想要使用的主机名设置为一个指向`origin.meteor.com`的CNAME，然后部署这个名字。

`meteor deploy www.myapp.com`


我们把这个作为免费服务提供出去，所以你可以尝试一下Meteor。快速构建内部的beta，demo等等是很有用处的。更多信息请访问[meteor deploy][]

[meteor deploy]: http://docs.meteor.com/#meteordeploy

### 在你自己的基础设施运行

你也可以在你自己的基础设施或者任何的可以运行Node.js应用的服务器提供商上运行你的应用。

开始的时候，直接运行：

`meteor build my_directory`

这个命令会以压缩文件的形式产生一个完全包含Node.js的应用。为了运行这个应用，你需要提供Node.js0.10和一个MongoDB服务器。（Meteor目前的发行版本已经用Node 0.10.36测试过了）你就可以通过调用Node，为要监听的应用和MongoDB终端来指定HTTP端口，然后运行应用了。


```
cd my_directory
(cd programs/server && npm install)
env PORT=3000 MONGO_URL=mongodb://localhost:27017/myapp node main.js
```

一些package可能需要其他的环境变量。比如，`email` package需要一个`MAIL_URL`的环境变量。

## 写packages

写Meteor package是很容易的。为了初始化一个meteor package，运行`meteor create --package username:packagename`，`susername`是你的Meteor开发者用户名。这将创建一个新的package，并且会把一个控制文件package.js和一些javascript文件预先填充到目录下。默认地，Meteor会把包含package.js文件的目录的名字作为package的名字。为了使用它，不要忘记运行`meteor add [packagename]`，即使这个package是应用内部的package。

Meteor确保对package和应用的重复构建。这意味着，如果你在一个机器上面构建了你的package，那么在一个仓库里面检查代码和在其他地方检查代码，你应该得到一样的结果。在你的package目录下，你会找到一个自动创建的`.versions`文件。这个文件指定了你用来构建你的package的所有package的版本，这个文件也是源代码的一部分。把它记录在版本控制中来确保在不同机器上面的重复性的构建。

> 有时候，package不仅仅代表他们自己，也代表在应用程序层次上的上下文的函数（特别地，是应用程序的packages目录下的packages）。在那种情况下，会优先考虑应用程序的上下文。不是使用`.versions`文件作为指导，我们用被应用使用的相同的依赖构建package。（我们想，在实践中，如果你的本地的package使用不同版本的东西构建成的，是非常让人疑惑的）。

Meteor为它的package使用拓展的server版本控制：这意味着版本号有三个部分组成，由句号分割：主版本号，次要版本号和补丁版本号（比如：1.2.3），并带有可选的预发布版本。你可以在[semver.org][]上了解更多。此外，因为一些meteor的package包含外部的库，Meteor支持使用_来表示wrap number的约定。

[semver.org]: http://www.semver.org/

You can read more about package.js files in the API section.

A word on testing: since testing is an important part of the development process, there are two common ways to test a package:

* Integration tests (putting a package directly into an application, and writing tests against the application) is the most common way to test a package. After creating your package, add it to your app's /packages directory and run meteor
add. This will add your package to your app as a local package. You can then test and run your app as usual. Meteor will detect and respond to changes to your local package, just as it does to your app files.

* Unit tests are run with the command meteor test-packages
package-name. As described in the package.js section, you can use the package.js file to specify where your unit tests are located. If you have a repository that contains only the package source, you can test your package by specifying the path to the package directory (which must contain a slash), such as meteor test-packages ./.

To publish a package, run meteor publish from the package directory. There are some extra restrictions on published packages: they must contain a version (Meteor packages are versioned using strict semver versioning) and their names must be prefixed with the username of the author and a colon, like so: iron:router. This namespacing allows for more descriptive and on-topic package names.

你可以在API部分阅读到有关[package.js][]文件的相关信息。

[package.js]: http://docs.meteor.com/#packagejs

关于测试：测试在开发过程中是一个重要的部分，有两种一般的测试测试package的方法：

* 集成测试（吧package直接放到应用当中，针对应用来写测试）是测试一个package的最通用的方法。在创建了你的package之后，把它添加到你的应用的`/packages`目录下面，并且运行`meteor add`。这回吧你的package作为一个本地package添加到你的应用当中。然后你就可以像通常一样测试并运行的的应用。Meteor会检测和响应你的本地package的变化，就像是你应用程序的文件一样。

* 单元测试是用命令`meteor test-packages package-name`来运行的。就像在[package.js][]部分所描述的，你可以使用[package.js][]文件来指定测试你的那个单元。如果你有一个仅仅包含package源代码的仓库，你可以通过指定package目录（必须包含斜线）的路径来测试你的package，比如`meteor test-packages ./`。

在package目录下运行`meteor publish`可以发布一个package。发布package有一些额外的限制：它们必须包含一个版本（Meteor的package是使用严格的[semver][semver.org]来进行版本控制的）、它们的名字必须以用户名和一个冒号为前缀，就像：`iron:router`一样。这个命名空间允许更具描述性的和相互连接的package名。



