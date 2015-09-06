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

By default all apps include the meteor-platform package. This automatically pulls in the packages that make up the core Meteor stack. If you want to build your own custom stack, just remove meteor-platform from your app and add back in whichever of the standard packages you want to keep.

Meteor uses a single-loading packaging system, meaning that it loads just one version of every package. Before adding or upgrading to a particular version of a package, Meteor uses a constraint solver to check if doing so will cause other packages to break. By default, Meteor will choose conservatively. When adding transitive dependencies (packages that other packages, but not the application itself) depend on, Meteor will try to choose the earlier version.

In addition to the packages in the official Meteor release being used by your app, meteor list and meteor add also search the packages directory at the top of your app. You can also use the packages directory to break your app into subpackages for your convenience, or to test packages that you might want to publish. See Writing Packages.

默认地所有应用会包括`meteor-platform`的package。这会自动地

## Namespacing

Meteor's namespacing support makes it easy to write large applications in JavaScript. Each package that you use in your app exists in its own separate namespace, meaning that it sees only its own global variables and any variables provided by the packages that it specifically uses. Here's how it works.

When you declare a top-level variable, you have a choice. You can make the variable File Scope or Package Scope.

// File Scope. This variable will be visible only inside this
// one file. Other files in this app or package won't see it.
var alicePerson = {name: "alice"};

// Package Scope. This variable is visible to every file inside
// of this package or app. The difference is that 'var' is
// omitted.
bobPerson = {name: "bob"};
Notice that this is just the normal JavaScript syntax for declaring a variable that is local or global. Meteor scans your source code for global variable assignments and generates a wrapper that makes sure that your globals don't escape their appropriate namespace.

In addition to File Scope and Package Scope, there are also Exports. An export is a variable that a package makes available to you when you use it. For example, the email package exports the Email variable. If your app uses the email package (and only if it uses the email package!) then your app can see Email and you can call Email.send. Most packages have only one export, but some packages might have two or three (for example, a package that provides several classes that work together).

You see only the exports of the packages that you use directly. If you use package A, and package A uses package B, then you only see package A's exports. Package B's exports don't "leak" into your namespace just because you used package A. This keeps each namespace nice and tidy. Each app or package only sees their own globals plus the APIs of the packages that they specifically asked for.

When debugging your app, your browser's JavaScript console behaves as if it were attached to your app's namespace. You see your app's globals and the exports of the packages that your app uses directly. You don't see the variables from inside those packages, and you don't see the exports of your transitive dependencies (packages that aren't used directly by your app, but that are used by packages that are used by your app).

If you want to look inside packages from inside your in-browser debugger, you've got two options:

Set a breakpoint inside package code. While stopped on that breakpoint, the console will be in the package's namespace. You'll see the package's package-scope variables, imports, and also any file-scope variables for the file you're stopped in.

If a package foo is included in your app, regardless of whether your app uses it directly, its exports are available in Package.foo. For example, if the email package is loaded, then you can access Package.email.Email.send even from namespaces that don't use the email package directly.

When declaring functions, keep in mind that function x () {} is just shorthand for var x = function x () {} in JavaScript. Consider these examples:

// This is the same as 'var x = function x () ...'. So x() is
// file-scope and can be called only from within this one file.
function x () { ... }

// No 'var', so x() is package-scope and can be called from
// any file inside this app or package.
x = function () { ... }
Technically speaking, globals in an app (as opposed to in a package) are actually true globals. They can't be captured in a scope that is private to the app code, because that would mean that they wouldn't be visible in the console during debugging! This means that app globals actually end up being visible in packages. That should never be a problem for properly written package code (since the app globals will still be properly shadowed by declarations in the packages). You certainly shouldn't depend on this quirk, and in the future Meteor may check for it and throw an error if you do.

## Deploying

Meteor is a full application server. We include everything you need to deploy your application on the internet: you just provide the JavaScript, HTML, and CSS.

Running on Meteor's infrastructure

The easiest way to deploy your application is to use meteor
deploy. We provide it because it's what, personally, we've always wanted: an easy way to take an app idea, flesh it out over a weekend, and put it out there for the world to use, with nothing getting in the way of creativity.

meteor deploy myapp.meteor.com
Your application is now available at myapp.meteor.com. If this is the first time deploying to this hostname, Meteor creates a fresh empty database for your application. If you want to deploy an update, Meteor will preserve the existing data and just refresh the code.

You can also deploy to your own domain. Just set up the hostname you want to use as a CNAME to origin.meteor.com, then deploy to that name.

meteor deploy www.myapp.com
We provide this as a free service so you can try Meteor. It is also helpful for quickly putting up internal betas, demos, and so on. For more information, see meteor deploy.

Running on your own infrastructure

You can also run your application on your own infrastructure or any hosting provider that can run Node.js apps.

To get started, run

meteor build my_directory
This command will generate a fully-contained Node.js application in the form of a tarball. To run this application, you need to provide Node.js 0.10 and a MongoDB server. (The current release of Meteor has been tested with Node 0.10.36.) You can then run the application by invoking node, specifying the HTTP port for the application to listen on, and the MongoDB endpoint.

cd my_directory
(cd programs/server && npm install)
env PORT=3000 MONGO_URL=mongodb://localhost:27017/myapp node main.js
Some packages might require other environment variables. For example, the email package requires a MAIL_URL environment variable.

## Writing packages

Writing Meteor packages is easy. To initialize a meteor package, run meteor create --package username:packagename, where username is your Meteor Developer username. This will create a package from scratch and prefill the directory with a package.js control file and some javascript. By default, Meteor will take the package name from the name of the directory that contains the package.js file. Don't forget to run meteor add [packagename], even if the package is internal to the app, in order to use it.

Meteor promises repeatable builds for both packages and applications. This means that, if you built your package on a machine, then checked the code into a repository and checked it out elsewhere, you should get the same result. In your package directory, you will find an automatically generated .versions file. This file specifies the versions of all packages used to build your package and is part of the source. Check it into version control to ensure repeatable builds across machines.

Sometimes, packages do not just stand on their own, but function in the context of an app (specifically, packages in the packages directory of an app). In that case, the app's context will take precedence. Rather than using the .versions file as a guide, we will build the package with the same dependencies as used by the app (we think that, in practice, it would be confusing to find your local packages built with different versions of things).

Meteor uses extended semver versioning for its packages: that means that the version number has three parts separated by dots: major version, minor version and patch version (for example: 1.2.3) with an optional pre-release version. You can read more about it on semver.org. Additionally, because some meteor packages wrap external libraries, Meteor supports the convention of using _ to denote a wrap number.

You can read more about package.js files in the API section.

A word on testing: since testing is an important part of the development process, there are two common ways to test a package:

Integration tests (putting a package directly into an application, and writing tests against the application) is the most common way to test a package. After creating your package, add it to your app's /packages directory and run meteor
add. This will add your package to your app as a local package. You can then test and run your app as usual. Meteor will detect and respond to changes to your local package, just as it does to your app files.

Unit tests are run with the command meteor test-packages
package-name. As described in the package.js section, you can use the package.js file to specify where your unit tests are located. If you have a repository that contains only the package source, you can test your package by specifying the path to the package directory (which must contain a slash), such as meteor test-packages ./.

To publish a package, run meteor publish from the package directory. There are some extra restrictions on published packages: they must contain a version (Meteor packages are versioned using strict semver versioning) and their names must be prefixed with the username of the author and a colon, like so: iron:router. This namespacing allows for more descriptive and on-topic package names.
