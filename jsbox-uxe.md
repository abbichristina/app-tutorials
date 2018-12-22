# 前情提要

如果你还不知道 JSBox 是什么，这里有一篇文章可以供你参考：[JSBox: 一个创造工具的工具](https://sspai.com/post/42361)。

简单说，JSBox 是一个为效率工具爱好者设计的 iOS 应用，你可以用他编写、运行标准的 JavaScript 脚本。更酷的是你可以通过 JavaScript 来实现各种原生的 iOS 插件，甚至定制自己的 widget 和键盘，我们提供丰富的接口让你无需对 iOS 有所了解就能制作出自己的应用。

在过去的几个月时间里，我们不断地完善 JSBox 的功能，在这次大版本里面我们为大家带来了全新的界面编辑器，是时候为大家做一个介绍了。

# 图形用户界面

人机交互必须要有接口，而用户界面是最为直观的接口。以捷径为例，虽然不支持真正意义上的图形界面，但也支持简单的、以一问一答对话为基础的交互方式。例如菜单选项：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/shortcuts-menu.jpg)

或是弹出的简单是非题：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/shortcuts-alert.jpg)

也支持简单的文字输入方式：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/shortcuts-input.jpg)

这些都在一定程度上为捷径提供了用户输入输出，是人机交互的基础之一，但这是不够的。JSBox 从一开始就设计了完备的用户图形界面接口，可以通过简单的脚本创建完善而美观的界面，例如这样：

![image](https://github.com/cyanzhong/xTeko/raw/master/collections/assets/0000-14.jpg)
![image](https://github.com/cyanzhong/xTeko/raw/master/collections/assets/0000-15.jpg)

你可以在 JSBox 里面创建类似“小程序”的脚本，而不仅仅是纯命令行的脚本或是只支持简单的输入输出，这一切在 JSBox 的第一个版本就已经支持，并在之后的一年时间里面不断地优化，支持越来越多的组件，比如对 Markdown 组件和 Lottie 动画组件的支持。

# 界面编辑器

因为 JSBox 已经有了良好的骨架，提供一个**所见即所得**的界面编辑器就成了水到渠成的事情。实际上界面编辑器也不是一个新鲜玩意儿，早在远古的 Visual Basic 时代，我们就在用拖拽的方式制作软件的界面，iOS 和 Android 的开发者工具也都提供了可视化的界面设计工具。但，在移动平台上完备地实现这么一套系统，仍然是一件极其复杂的的事情，工程量不可谓不大。

简要来说，界面编辑器可以让界面开发变得极为容易，只用拖拽对应的控件到画布上，然后设置一些属性就行了，你无须写一行代码就能制作出一个酷炫的界面。除了更快的制作脚本，也能让新手也体验编程的乐趣。

那么我现在就展示一下在 JSBox 新版里面界面编辑器如何工作。

在画布界面你可以选中控件，进行移动、调整大小、复制和删除等操作：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-canvas.png)

编辑器支持所有通过代码能够实现的控件和效果，你需要的只是将他们添加到画布或者控件上（支持控件的嵌套）：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-components.png)

即便是复杂如列表、网格等基于模板的视图，也可以通过简单的配置快速生成。

# 属性设置

你可以可视化地调整视图的全部属性，例如这样调整这个输入框的样式：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-props.png)

有些属性比较复杂，比如`颜色`和`字体`，也都支持非常直观的选择操作：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-color-picker.png)
![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-font-picker.png)

由于某些原因，例如控件太小或者是被隐藏，你可能无法在画布里面选中它，这种时候你可以通过`层级`这个页面将视图展开，方面进行操作：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-hierarchy.png)

# 页面设置

你可以轻松地设置页面的行为，比如配置导航栏的按钮、打开调试模式等等：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-page.png)

打开调试模式你可以在运行时动态地查看视图的结构和属性：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-inspector.png)

你甚至可以动态地移动控件和调整属性，这将大大地方便界面开发过程中的调试过程。

# 自动布局技术

JSBox 的界面编辑器支持 iOS 的 Auto Layout，这可以让你轻松地设计出在不同尺寸屏幕下运行都能够**自适应**的用户界面。在这里我并不会深入地去讲自动布局的原理，而仅仅是展示一下在界面编辑器里面如何轻松地为控件设置布局约束：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-layout.png)
![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-constraint.png)

界面编辑器甚至能发现你的布局问题，并提出建议的解决方案：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-conflicts.png)

如果只是制作脚本在自己的设备上使用，你无须理解什么是自动布局，而如果需要运行在不同尺寸的设备上，界面编辑器也能很好的帮你完成自动布局。

# 绑定事件

“用户按下了一个按钮”这是一个事件，将事件绑定到代码上就实现了用户界面的逻辑。

界面上的控件总是和发生的事件息息相关，不同的控件支持的事件也不尽相同，你当然可以通过代码的方式实现事件的绑定，但通过界面编辑器则会更容易。

事件编辑器上面会展示该控件支持的全部事件：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-events.png)

你只需点进去为它添加一个函数，JSBox 就会自动把控件和事件绑定起来，如果函数在代码中不存在还会自动为你创建：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-code.png)

在函数里面添加代码，就完成了这个控件的逻辑。

# 运行起来

界面编辑器工作到任何时候，你都可以点击下方的运行按钮将脚本跑起来，这个例子运行起来长这样：

![image](https://github.com/cyanzhong/app-tutorials/raw/master/asset/uxe-run.png)

和在编辑器里面看到的效果完全一致，这就是所见即所得追求的效果，做到这个效果，也就让界面制作的成本大大地降低了。

# 对未来的思考

拖拽界面甚至可以让小白制作出用户界面，但他仍需编写逻辑来实现程序的功能。我们希望在未来能够尽可能的简化“实现逻辑”这一步，例如将一些常见的功能模块化：下载文件、保存图片等等，让小白用户可以通过“拖拽模块”的方式来实现逻辑，同时保留代码的部分，方便习惯用代码实现逻辑的用户。

让更多人参与到编程这件有趣的事，是我们始终在思考的。

我们很高兴在过去的几个月为 JSBox 实现了这个版本，这是对我们而言的一个里程碑版本，希望大家可以喜欢。同时我们也意识到 JSBox 目前仍然处于初级阶段，我们仍然在为更多令人兴奋的特性而努力。

欢迎来自各个方面的意见和建议，联系我们：

- [社区](https://jsboxbbs.com)
- [邮件](mailto:log.e@qq.com)
- [Telegram](https://t.me/PinTG)
- [Twitter](https://twitter.com/cyanapps)
- [微博](https://weibo.com/0x00eeee)
