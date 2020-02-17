# JSBox 2.0

经过大半年时间的开发工作，我们近期上线了 JSBox 2.0，又经过两周时间完成了一些优化和修复，现在是时候向大家介绍这个里程碑版本了。

我们在 2.0 版本里面主要做了两件事情：

- 支持 Node.js
- 改变了付费模式

这篇文章将详细介绍这两件事情给我们和用户带来的影响。

# Node.js 运行时

了解 JSBox 的朋友可能知道，JSBox 基于 Apple 的 [JavaScriptCore](https://developer.apple.com/documentation/javascriptcore) 提供了一套运行时，让你编写的 JavaScript 可以通过我们提供的 API 与 iOS 交互。例如：

- 读取系统相册
- 发送 HTTP 请求
- 绘制图形用户界面
- ...

我们都知道，JavaScript 社区很多现成的轮子，比如 npm 上面各式各样的 package。由于 JavaScriptCore 和平台的限制，只有很少量的 package 可以被直接用于 JSBox 的脚本。

所以我们在 2.0 里面直接支持了 [Node.js](https://nodejs.org)，并且十分完善：

- 完整的 Node.js 环境
- REPL 环境
- 包管理器
- 丰富的 native 模块用于与 iOS 进行交互
- 与 JSBox 脚本相互调用的能力

如果你已经有 Node.js 的相关知识，那么这些内容对你来说应该并不陌生。简单来说，你可以在 iOS 设备上直接写 Node.js 程序，直接使用各种各样的 npm 模块。

除此之外，我们还提供一系列原生模块，让你的 Node.js 程序可以直接与 iOS 原生功能进行交互，就像 JSBox 脚本之前能做到的那样，相关文档可以在[这里](https://cyanzhong.github.io/jsbox-nodejs/#/)找到。

如果你对 Node.js 的概念感到一头雾水，那么接下来我们会通过一些实际的例子来介绍 Node.js 如何让 JSBox 更实用。

## 使用 Express 构建网站

[Express](https://expressjs.com/) 是一个著名的 Web 应用开发框架，基于 Node.js。在 JSBox 里面新建一个 Node 模块时，你会看到这个样例代码：

![Express](https://github.com/cyanzhong/app-tutorials/raw/master/asset/0217-00.png)

运行起来之后，将会看到 Safari 打开了一个网站，而网站背后的应用服务器，正是由 Express 所提供。这是一个简单的样例，用于展示一个 Node 模块如何工作。

## 为 JSBox 提供 Git 支持

我们为 JSBox 2.0 编写了一个 Git 客户端 GitBox（[下载](https://xteko.com/install?id=153&lang=zh-Hans)），它使用 JSBox 编写界面部分，用 Node.js 实现了其中的 Git 命令：

![GitBox](https://github.com/cyanzhong/app-tutorials/raw/master/asset/0217-01.png)

这个客户端支持了 Git 大部分的常用功能，例如：

- 检出和初始化 Git 仓库
- 查看提交记录和文件改动（并提供 diff 视图）
- 分支操作：查看、切换、新建以及合并两个分支
- 标签操作：查看、检出以及新建标签
- fetch, pull, commit 以及 push

这是一个**完整**的 Git 实现，虽然说在手机上常用的操作可能也就是检出项目和查看提交记录，但 GitBox 还是实现了大部分功能。你甚至可以在 JSBox 上完成一些修改，然后将改动推送到远端。

完成这个 Git 客户端，得益于开源项目 [isomorphic-git](https://isomorphic-git.org/)，这也正是支持 Node.js 带给我们的好处。

P.S. 最棒的是，你可以用 GitBox 来检出下面的项目，因为他们都放在了 GitHub。

## 下载 YouTube 视频

如果想要把 YouTube 视频下载下来的话，只需要复制视频链接，然后打开这个脚本就好了：

![youtube-dl](https://github.com/cyanzhong/app-tutorials/raw/master/asset/0217-02.png)

这个样例基于 [ytdl-core](https://www.npmjs.com/package/ytdl-core)， 可以在[这里](https://github.com/cyanzhong/jsbox-youtube-dl)找到。

## 下载磁力链接

想要下载磁力链接也不是什么难事，复制链接打开这个脚本就好了：

![磁力链接](https://github.com/cyanzhong/app-tutorials/raw/master/asset/0217-03.png)

这个样例基于 [webtorrent](http://webtorrent.io/)，可以在[这里](https://xteko.com/install?id=154&lang=zh-Hans)下载。

## 开发 React.js 程序

因为支持 Node.js，你可以使用 [webpack](https://webpack.js.org/) 和 [babel](https://babeljs.io/) 搭建出一个 [React.js](https://reactjs.org/) 的开发环境，就像这样：

![React.js](https://github.com/cyanzhong/app-tutorials/raw/master/asset/0217-04.png)

JSBox 的编辑器也提供了高亮支持，虽然写起来不是那么舒服，但验证一下想法是没有问题的，你可以在[这里](https://github.com/cyanzhong/jsbox-react-demo)找到这个项目。

## 开发 Vue.js 程序

基于同样的方式，你还可以搭建出一个 [Vue.js](https://vuejs.org/) 的开发环境：

![Vue.js](https://github.com/cyanzhong/app-tutorials/raw/master/asset/0217-05.png)

这个项目和 React.js 的项目类似，都是基于 webpack 和本地的应用服务器搭建出来的开发环境，你可以在[这里](https://github.com/cyanzhong/jsbox-vue-demo)找到这个项目。

# 后续开发计划

以上就是关于 JSBox 2.0 里面目前主要更新的介绍，同时我们也在不断地开发新的功能，例如：

- Dark Mode
- 自定义主题
- 编辑器支持多个标签
- 更好的 iPad 支持

这些功能我们将会在今年的晚些时候提供，敬请期待。

# 新的付费机制

为了让 JSBox 得到持续地发展，让我们能够投入更多精力去完善这个产品，2.0 采用了全新的付费模式：**通过一次付费来解锁当前以及接下来一年的功能，解锁过的功能永久可用。**

老用户最关心的问题是：是不是不继续付费，JSBox 就不能用了？不是的。对于老用户而言，2.0 发布以前的全部功能，你都是可以永久免费用下去的。

JSBox 2.0 虽然采用了订阅解锁功能的机制，但相较于“不订阅就不能使用高级功能”的设定而言，最大的区别是功能“一经解锁解锁便永久可用”。停止付费不会损失任何功能，仅在后续看到感兴趣的高级功能时付费，完全可选。

曾经我们也想过将 2.0 版本单独上线成一个新应用，但那种方式会造成版本的分裂，进而老版本里面的一些问题不能得到修复。

为什么不提供永久解锁高级版的机制？基于目前国内黑产的状况，我们不想提供直接通过付费买断应用的机制。但如果用户已经长时间在连续支持，我们可能会直接解锁永久版本，目前具体的方案仍在考虑中。

付费的问题总是会很敏感，而改变付费模式更是复杂，我们写了[一篇文章](https://jsboxbbs.com/d/1047)来介绍付费模式的思考过程，以及全部细则，感兴趣的话可以阅读。

另外，对于老用户而言，目前还提供一个限时的 6.8 折价格。同时对于已经支持 JSBox 超过一年的朋友，解锁还将获得 4 枚特殊的应用图标。

# 最后

希望 2.0 是 JSBox 的新开始，因为我们还有很多事情要做去推动它变得更好，感谢大家的支持。