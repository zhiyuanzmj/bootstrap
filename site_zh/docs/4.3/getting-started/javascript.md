---
layout: 文档
title: JavaScript的
description: 使用基于jQuery构建的可选JavaScript插件，将Bootstrap带入生活。了解每个插件，我们的数据和编程API选项等。
group: 入门
toc: 真正
---

## 个人或编译

插件可以单独包含（使用Bootstrap的单独`js/dist/*.js` ），也可以使用`bootstrap.js`或缩小的`bootstrap.min.js` （不包括两者）一次性包含。

如果使用bundler（Webpack，Rollup ...），则可以使用UMD就绪的`/js/dist/*.js`文件。

## 依赖

一些插件和CSS组件依赖于其他插件。如果单独包含插件，请确保在文档中检查这些依赖项。另请注意， **所有插件都依赖于jQuery** （这意味着必须在插件文件**之前**包含jQuery）。 [请参阅我们的`package.json` ]（{{site.repo}} / blob / v {{site.current_version}} / package.json）以查看支持哪些版本的jQuery。

我们的下拉，弹出窗口和工具提示也取决于[Popper.js](https://popper.js.org/) 。

## 数据属性

几乎所有的Bootstrap插件都可以通过HTML单独使用数据属性（我们使用JavaScript功能的首选方式）来启用和配置。确保**只在一个元素上使用一组数据属性** （例如，您不能从同一个按钮触发工具提示和模态。）

但是，在某些情况下，可能需要禁用此功能。要禁用数据属性API，请使用`data-api`取消绑定文档命名空间上的所有事件，如下所示：

{％highlight js％} $（document）.off（'。data-api'）{％endhighlight％}

或者，要定位特定的插件，只需将插件的名称作为命名空间以及data-api命名空间包含如下：

{％highlight js％} $（document）.off（'。alert.data-api'）{％endhighlight％}

{％capture callout％}

## 选择

目前，为了查询DOM元素，出于性能原因，我们使用本机方法`querySelector`和`querySelectorAll` ，因此您必须使用[有效的选择器](https://www.w3.org/TR/CSS21/syndata.html#value-def-identifier) 。如果使用特殊选择器，例如： `collapse:Example`务必转义它们。 {％endcapture％} {％include callout.html content = callout type =“warning”％}

## 活动

Bootstrap为大多数插件的独特操作提供自定义事件。通常，它们以不定式和过去的分词形式出现 - 在事件开始时触发不定式（例如`show` ），并且在动作完成时触发其过去的分词形式（例如`shown` ）。

所有不定式事件都提供[`preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault)功能。这提供了在动作开始之前停止执行的能力。从事件处理程序返回false也会自动调用`preventDefault()` 。

{％highlight js％} $（'＃myModal'）。on（'show.bs.modal'，function（e）{if（！data）{return e.preventDefault（）//停止显示模态}} ）{％endhighlight％}

## 程序化API

我们还相信您应该能够纯粹通过JavaScript API使用所有Bootstrap插件。所有公共API都是单一的，可链接的方法，并返回所采取的集合。

{％highlight js％} $（'。btn.danger'）。button（'toggle'）。addClass（'fat'）{％endhighlight％}

所有方法都应该接受一个可选的选项对象，一个以特定方法为目标的字符串，或者什么都不接受（它启动一个默认行为的插件）：

{％highlight js％} $（'＃myModal'）。modal（）//使用默认值初始化$（'＃myModal'）。modal（{keyboard：false}）//初始化没有键盘$（'＃myModal' ）.modal（'show'）//初始化并立即调用show {％endhighlight％}

每个插件还在`Constructor`属性上公开其原始构造`Constructor` ： `$.fn.popover.Constructor` 。如果您想获得特定的插件实例，请直接从元素中检索它： `$('[rel="popover"]').data('popover')` 。

### 异步函数和转换

所有编程API方法都是**异步的** ，一旦转换开始但**在结束之前**返回给调用者。

为了在转换完成后执行操作，您可以收听相应的事件。

{％highlight js％} $（'＃myCollapse'）。on（'shown.bs.collapse'，function（e）{//展开可折叠区域后执行的操作}）{％endhighlight％}

此外， **将忽略**对**转换组件**的方法调用。

{％highlight js％} $（'＃myCarousel'）。on（'slid.bs.carousel'，function（e）{$（'＃myCarousel'）。carousel（'2'）//将滑到幻灯片2一旦完成到幻灯片1的过渡}）

$（'＃myCarousel'）。carousel（'1'）//将开始滑动到幻灯片1并返回给调用者$（'＃myCarousel'）。carousel（'2'）// !!将被忽略，因为幻灯片1的过渡未完成!! {％endhighlight％}

### 默认设置

您可以通过修改插件的`Constructor.Default`对象来更改插件的默认设置：

{％highlight js％} //将模态插件的`keyboard`选项的默认值更改为false $ .fn.modal.Constructor.Default.keyboard = false {％endhighlight％}

## 没有冲突

有时需要将Bootstrap插件与其他UI框架一起使用。在这些情况下，偶尔会发生命名空间冲突。如果发生这种情况，您可以在要恢复其值的插件上调用`.noConflict` 。

{％highlight js％} var bootstrapButton = $ .fn.button.noConflict（）//将$ .fn.button返回到先前分配的值$ .fn.bootstrapBtn = bootstrapButton //给$（）。bootstrapBtn Bootstrap功能{％ endhighlight％}

## 版本号

可以通过插件构造函数的`VERSION`属性访问每个Bootstrap的jQuery插件的`VERSION` 。例如，对于工具提示插件：

{％highlight js％} $ .fn.tooltip.Constructor.VERSION // =>“{{site.current_version}}”{％endhighlight％}

## 禁用JavaScript时没有特殊的后备

禁用JavaScript时，Bootstrap的插件不会特别优雅地退回。如果您关心这种情况下的用户体验，请使用[`<noscript>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noscript)向用户解释情况（以及如何重新启用JavaScript），和/或添加自己的自定义回退。

{％capture callout％}

##### 第三方库

**Bootstrap不正式支持** Prototype或jQuery UI等**第三方JavaScript库** 。尽管`.noConflict`和命名空间事件，但您可能需要自行修复兼容性问题。 {％endcapture％} {％include callout.html content = callout type =“warning”％}

## UTIL

所有Bootstrap的JavaScript文件都依赖于`util.js` ，它必须与其他JavaScript文件一起包含在内。如果你正在使用编译的（或缩小的） `bootstrap.js` ，则不需要包含它 - 它已经存在了。

`util.js`包含实用程序函数和`transitionEnd`事件的基本帮助程序以及CSS转换模拟器。其他插件使用它来检查CSS转换支持并捕获挂起转换。

## 消毒剂

工具提示和弹出窗口使用我们的内置清洁剂来清理接受HTML的选项。

默认的`whiteList`值如下：

{％highlight js％} var ARIA_ATTRIBUTE_PATTERN = / ^ aria  -  [\ w-] *$ / i var DefaultWhitelist = {//以下任何提供的元素允许的全局属性。 '* '：['class'，'dir'，'id'，'lang'，'role'，ARIA_ATTRIBUTE_PATTERN]，a：['target'，'href'，'title'，'rel']，area：[ ]，b：[]，br：[]，col：[]，代码：[]，div：[]，em：[]，hr：[]，h1：[]，h2：[]，h3：[ ]，h4：[]，h5：[]，h6：[]，i：[]，img：['src'，'alt'，'title'，'width'，'height']，li：[] ，ol：[]，p：[]，pre：[]，s：[]，small：[]，span：[]，sub：[]，sup：[]，strong：[]，u：[] ，ul：[]} {％endhighlight％}

如果要向此默认`whiteList`添加新值，可以执行以下操作：

{％highlight js％} var myDefaultWhiteList = $ .fn.tooltip.Constructor.Default.whiteList

//允许表元素myDefaultWhiteList.table = []

//允许td元素上的td元素和数据选项属性myDefaultWhiteList.td = ['data-option']

//您可以推送自定义正则表达式来验证属性。 //小心你的正则表达式太宽松了var myCustomRegex = / ^ data-my-app  -  [\ w  - ] + / myDefaultWhiteList ['*']。push（myCustomRegex）{％endhighlight％}

如果您想绕过我们的清洁剂，因为您更喜欢使用专用库，例如[DOMPurify](https://www.npmjs.com/package/dompurify) ，则应执行以下操作：

{％highlight js％} $（'＃yourTooltip'）。tooltip（{sanitizeFn：function（content）{return DOMPurify.sanitize（content）}}）{％endhighlight％}
