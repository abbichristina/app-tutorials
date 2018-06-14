# 什么是 JSBox

如果你关注应用，尤其是国内的独立应用，你可能在最近或多或少的听过 JSBox，但却不知道他是做什么的。如果你用过 Pin，在最新的版本里面我们内置了 JSBox 的简化版，能让你通过脚本语言（[JavaScript](https://en.wikipedia.org/wiki/JavaScript)）实现很多功能，例如处理文本、分享图片等等。

JSBox 的核心设计和这一样，是一个通过脚本语言来实现各种 iOS 插件的效率工具，你可以编写自己的插件，也可以安装别人分享出来的插件。

能实现什么功能？举一些实际的例子：

通过推送通知执行脚本，查询数据（[点击安装](https://xteko.com/redir?url=https%3a%2f%2fraw.githubusercontent.com%2fcyanzhong%2fxTeko%2fmaster%2fextension-scripts%2ffund-data.js)）：

![推送通知](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-notification.gif)

实现一个属于自己的键盘，比如这个短语键盘（[点击安装](https://xteko.com/redir?url=https%3a%2f%2fgithub.com%2fcyanzhong%2fxTeko%2fraw%2fmaster%2fextension-demos%2fkeyboard.box)）：

![键盘](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-keyboard.gif)

制作一个自己的通知中心小组件，例如年进度（[点击安装](https://xteko.com/redir?name=Progress&url=https%3A%2F%2Folx97w61o.qnssl.com%2FProgress.box&types=3)）：

![小组件](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-progress.gif)

实现一个生成 Surge 规则的工具（[点击安装](https://xteko.com/redir?name=Rules-lhie1&url=https%3a%2f%2fraw.githubusercontent.com%2fFndroid%2fjsbox_script%2fmaster%2fRules-lhie1%2f.output%2fRules-lhie1.box)）：

![小应用](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-surge.gif)

制作一个练习日语五十音的小应用（[点击安装](https://t.me/Flow_Script/386)）：

![小应用](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-50.gif)

制作一个 App Store 资源获取工具（[点击安装](https://xteko.com/redir?name=iTunes%20Utilities&url=https%3A%2F%2Fgithub.com%2Faxelburks%2FJSBox%2Fraw%2Fmaster%2FiTunes%2520Utilities%2F.output%2FiTunes%2520Utilities.box)）：

![小工具](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-itunes.gif)

这些现成的脚本你只需点击上面的链接，就可以根据提示安装到 JSBox 上使用了。

# 和 Workflow 有什么区别

这是一个经常被问起的问题，甚至有一些人直接笃定 JSBox 只是一个翻版的 Workflow 而已，但其实完全不是这样，Workflow 和 JSBox 各有所长且无法互相取代。

首先 Workflow 是一个很棒的应用，我也很喜爱 Workflow，用他也能做到很多 JSBox 能做到的事情，但 JSBox 和 Workflow 还是有本质上的不同。

之所以 Workflow 也有很高的可玩性，很大程度是来自于他的 `Get Contents of URL` 模块，这能让你实现一些数据抓取并展现一类的功能。但说到底 Workflow 不是一种灵活度高的编程，在处理一些复杂逻辑上面，Workflow 的工作模式是捉襟见肘的，你常常会看到写的超级长的一个 Workflow，而只是为了对抓取到的数据做一个简单的处理。

另一方面，Workflow 能提供的用户交互是极为有限的，他可以展示给用户一个菜单，一个提示框等等，但却没有办法真正的做出一个完全自定义的用户界面。而在 JSBox 里面处理复杂的逻辑却十分容易，因为编程语言的描述能力要远超 Workflow 那种搭积木的方式。同时 JSBox 也提供了超多的编程模块，例如`网络`、`界面`、`文件`、`分享`等等，你可以用 JSBox 构建出交互远远超过 Workflow 的小插件。如果非要举一些例子的话，Workflow 不能做到下面这些内容：

- 无法实现在通知中心直接输入文字
- 无法通过推送的方式直接运行一个脚本
- 没有办法自己做一个通知中心小组件，或者自制键盘
- 无法实现一个 Safari 扩展
- 没有办法通过 Runtime 自由地调用 iOS 内置的接口

# 不会写代码能用 JSBox 吗

为了解决这个问题我们规划了几件事情，首先建立了 JSBox [官方社区](https://jsboxbbs.com)，目的就是为了给大家一个讨论和分享的地方，同时也能让一些讨论沉淀下来，避免无意义的重复动作。同时我们会每隔一段时间推荐一批脚本，可以读读看[第一期](https://jsboxbbs.com/d/249)，这样能让用户了解过去的一段时间里面又有什么新鲜内容。

但这些操作都是**零散**的，是很难让用户去**主动发现**一个脚本的，只有将脚本归类并加上搜索功能，这件事情才能得到比较好的解决。因此，我们在最近的版本中引入了“脚本商店”的功能，你可以直接在应用内找到脚本商店，这里面我们将一些脚本分类展示并且提供了搜索功能，是目前发现脚本最好的途径：

![脚本商店](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-gallery.jpg)

我们会定期更新商店里的内容，你也能够在这里方便地更新你已经安装过的脚本。同时，之后脚本商店的内容也支持用户上传，进一步地解决互相分享脚本的问题，敬请期待。

当然无论如何，我们始终更鼓励你通过学习，通过工具来解决自己的问题，因为有些问题是独一无二的，也许不见得会有别人来帮你解决。所以不要犹豫，JavaScript 学习起来，创造自己的工具不是更好吗？

# 最新特性

既然说了那么多，借此机会也介绍一下最近版本里面的一些很酷的特性，希望有能让你感兴趣的地方。

首先我们对通知中心做了改造，现在我们的通知中心小组件极为强大，不仅不会因为内存不足而崩溃，甚至支持滚动操作，很大程度上使用起来已经和在应用内没有区别，比如这个例子（[点击安装](https://xteko.com/redir?url=https%3a%2f%2fraw.githubusercontent.com%2fcyanzhong%2fxTeko%2fmaster%2fextension-scripts%2fdoutu.js&icon=055)）：

![斗图](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-doutu.gif)

另外，我们已经支持了 Safari 扩展，也就是说你可以写脚本来控制 Safari 的行为。这套方案让很多想法成为可能，我们准备了这个脚本来作为样例（[点击安装](https://xteko.com/redir?url=https%3A%2F%2Fgithub.com%2Fcyanzhong%2FxTeko%2Fraw%2Fmaster%2Fextension-scripts%2Fsafari-extensions.box&name=Safari+Extensions)）：

![Safari 扩展](https://github.com/cyanzhong/app-tutorials/raw/master/asset/jsbox-safari.gif)

这个脚本可以在 Safari 上面运行 Firebug/Eruda/vConsole 等知名调试工具，对 Web 开发者来说是一个非常不错的小工具。理论上这个方案可以支持更多的内容，比如[简悦](http://ksria.com/simpread/)也成功地通过 JSBox 运行在了 iOS Safari 上。我们相信这是一个潜力巨大的特性，未来一定会有更多有意思的内容出现。

# 最后一段

如果你觉得上述文字太过枯燥，也欢迎通过这个视频了解一下 JSBox：https://weibo.com/tv/v/GdRBGxwIK?fid=1034:12c7e1d746bc5f775a065c1ab1951627

对于有动手能力的用户，我们也提供了非常健全的开发文档：https://docs.xteko.com/ 希望你能在这里面找到实现自己 idea 的方法。

目前 JSBox 仍然是一个很年轻的应用，我们仍然在努力，为他提供更多有意思的特性，同时我们也广泛地接受来自用户的各种意见和建议，毕竟这一款为创造者制作的应用。
