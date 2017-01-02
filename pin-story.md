# Pin 的故事

大家好，我是一名开发者，我打算给你讲一个程序员的故事，一个关于 `Pin` 的故事。

## 故事的开始

2015年9月2日，我为「Pin - 剪贴板扩展」这个项目写下了第一行代码，当时的想法非常简单：**市面上已经有太多的剪贴板工具和启动器工具了，我希望通过一种新的方式将这两种工具有机的结合起来**。

【最早的代码】
![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/the-first-line-code.png)

大约在两三周后我发布了 Pin 的第一个版本，那时候 Pin 极为轻巧（不到 1M），图标和界面都很简陋，如果还有人记得的话：

【图标】
![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/pin-1.0-icon.jpg)

【通知中心】
![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/pin-1.0-screenshot-1.jpg)

【主界面】
![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/pin-1.0-screenshot-2.jpg)

是的，这是一个纯粹由工程师自己的需求发起的，短期内完成的作品，可能大家一看到这个颜值都不会想要去下载。

那时候在与 `AppSo` 同属于 ifanr 的 `MindStore` 做过一些版本更新的推广，为 Pin 积累了最早一批的用户。

## 不断改进

Pin 内建了一个邮件反馈渠道，长期以来是我听到用户声音最主要的方式。与一般的产品**收集统计数据并以此来改进产品**的方式不同，Pin 完全不收集任何数据，甚至不关心目前 Pin 到底有多少活跃用户，这一点是很多用户和同行都想象不到的。而一开始做出这个决定的原因也十分荒唐：**主流数据统计平台的 SDK 实在是不太好，弄上去之后 Pin 的安装包体积明显的变大。**

![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/feedback.png)

不过后来我发现，对于独立开发者而言，直接从用户反馈中获得改进的想法似乎是更好的一个做法。与用户交流的过程中可以学到很多东西，同时也是一个很有趣的事情。所以说给我反馈的内容，绝大部分在我看到的情况下都会回复，**除非特别不友善的。**

Pin 发展到现在其实很多功能都是用户的智慧，虽然我会对主体功能有自己的把握，不会做出严重跑偏的功能。**让大家参与进来，不断让产品变得更好，这是我觉得独立应用开发里面最有趣的部分。**

## 做有趣的事

相比让 Pin 有更多的用户，我更在乎的其实是`有趣`。我曾多次提到，Pin 是一个充斥着我个人想法的产品，有些功能可能并不是对所有人都适用，但我绝对不会去复制功能，因为这不有趣。其实我把 Pin 当成了我产品和技术上的试验田，我在上面尝试过很多很疯狂的想法和实践，例如`预览`和`分词`功能。

长期以来，我认为 Pin 的核心价值是**能够最大限度的利用 iOS 的剪贴板，能够缩短一些文本操作的流程，让效率类软件的爱好者受益。**为了实现这个目标，我在 iOS 的 `widgets` 上面做了一些有趣的尝试，这些功能可能一开始就没有同类产品这么试过，他们很疯狂，也可能完全会失败。

![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/preview.png)

`通知中心预览`功能，可以让用户在复制文本之后直接在通知中心获得想要的结果，而不用离开当前的 app，这是我自己最喜欢的功能之一。一开始在这里只能做有限的交互，随着 iOS 自身的不断改进，现在已经完全支持和 Safari 同样的浏览体验。

![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/segmentation.png)

`分词`功能，旨在解决 iOS 平台上文本选取的难题。我们常常在微信或者短信应用里面复制整段的文本，如果你想单独搜索某个单词就会十分尴尬，于是我在 Pin 的早期版本里面引入了分词 widget，用户只要复制文本后打开通知中心，文本就会被划分成一个个词块。

## 渐入佳境

Pin 一点点被用户熟知，不断的出现在国内各种媒体的推荐榜上面，之后也得到了 App Store 官方的推荐和年度十佳的称号。这里要特别对 [`AppSo`](http://www.ifanr.com/app) 表示感谢，在 Pin 的成长过程中，AppSo 给予了 Pin 很多帮助，从一开始的推荐，到后来 2015 年度应用，再到后来邀请我分享 Pin 的技巧，以及现在给我机会讲故事给大家听。AppSo 提供了很多机会，在此郑重地表示感谢。

![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/appso.jpg)

## 突破极限

Pin 在技术和产品方面都做了很多努力，例如说始终保持安装包轻量（最新版本 4.4M），Pin 是一个包含了多个插件的应用，做到这一点其实并不简单。同时也一直在探寻技术上的突破，例如在通知中心输入文字，以及目前仍在开发中的全新`扩展中心`。在大公司里面做产品其实不容易有这样的态度，很多时候我会觉得我有责任让 Pin 变得更好，不管是技术上还是产品上。我常常会冒出疯狂的想法，实现它或者否定它，将沉淀下来的内容带给用户。

![image](https://raw.githubusercontent.com/cyanzhong/app-tutorials/master/pin-story/input.png)

Pin 在最新版本里面支持了通知中心直接输入文字，让效率更上一个台阶，这应该是目前独一无二的尝试。

一个小剧透，目前 Pin 在开发一个绝对 `hard core` 的功能，同时希望能够建立起一个大家为这个功能贡献的机制，将 Pin 的很多功能变成可动态扩展的，让开发者们迸发出各种各样的脑洞。当然这个尝试很可能会失败，让我们拭目以待吧。

## 后话

诚然，作为我个人兴趣爱好催生的独立作品，Pin 有着各种各样的缺陷，他当然不完美。不过我从来没有想过让他完美，我享受着开发过程中和交流过程中带来的乐趣，同时也自豪我把这份乐趣带给了一部分用户。我想这是一个独立开发者最开心的事情。

2017 年开始了，Pin 才一岁出头，他的人生才刚刚开始。
