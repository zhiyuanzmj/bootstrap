<p align="center">
  <a href="https://getbootstrap.com/">
    <img src="https://getbootstrap.com/docs/4.3/assets/brand/bootstrap-solid.svg" alt="Bootstrap logo" width="72" height="72">
  </a>
</p>

<h3 align="center">Bootstrap</h3>

<p align="center">
圆滑，直观，强大的前端框架，更快，更容易的web开发。
  <br>
  <a href="https://getbootstrap.com/docs/4.3/"><strong>Explore Bootstrap docs »</strong></a>
  <br>
  <br>
  <a href="https://github.com/twbs/bootstrap/issues/new?template=bug.md">Report bug</a>
  ·
  <a href="https://github.com/twbs/bootstrap/issues/new?template=feature.md&labels=feature">Request feature</a>
  ·
  <a href="https://themes.getbootstrap.com/">Themes</a>
  ·
  <a href="https://blog.getbootstrap.com/">Blog</a>
</p>

## 目录

- [快速开始](#quick-start)
- [状态](#status)
- [包括什么](#whats-included)
- [Bugs 和问题](#bugs-and-feature-requests)
- [文档](#documentation)
- [贡献](#contributing)
- [社区](#community)
- [版本](#versioning)
- [创作者](#creators)
- [谢谢](#thanks)
- [版权和许可](#copyright-and-license)

## 快速开始

有几种快速开始选项：

- [下载最新版本。](https://github.com/twbs/bootstrap/archive/v4.3.1.zip)
- Clone 版本库: `git clone 
    https://github.com/twbs/bootstrap.git`
- 用 [npm](https://www.npmjs.com/) 安装: `npm install bootstrap`
- 用 [yarn](https://yarnpkg.com/) 安装: `yarn add bootstrap@4.3.1`
- 用 [Composer](https://getcomposer.org/) 安装: `composer require twbs/bootstrap:4.3.1`
- 用 [NuGet](https://www.nuget.org/) 安装: CSS: `Install-Package bootstrap` Sass: `Install-Package bootstrap.sass`

有关框架内容，模板和示例等的信息，请阅读[入门页面](https://getbootstrap.com/docs/4.1/getting-started/introduction/)。

## 状态

[![Slack](https://bootstrap-slack.herokuapp.com/badge.svg)](https://bootstrap-slack.herokuapp.com/)
[![Build Status](https://img.shields.io/travis/twbs/bootstrap/v4-dev.svg)](https://travis-ci.org/twbs/bootstrap)
[![npm version](https://img.shields.io/npm/v/bootstrap.svg)](https://www.npmjs.com/package/bootstrap)
[![Gem version](https://img.shields.io/gem/v/bootstrap.svg)](https://rubygems.org/gems/bootstrap)
[![Meteor Atmosphere](https://img.shields.io/badge/meteor-twbs%3Abootstrap-blue.svg)](https://atmospherejs.com/twbs/bootstrap)
[![Packagist Prerelease](https://img.shields.io/packagist/vpre/twbs/bootstrap.svg)](https://packagist.org/packages/twbs/bootstrap)
[![NuGet](https://img.shields.io/nuget/vpre/bootstrap.svg)](https://www.nuget.org/packages/bootstrap/absoluteLatest)
[![peerDependencies Status](https://img.shields.io/david/peer/twbs/bootstrap.svg)](https://david-dm.org/twbs/bootstrap?type=peer)
[![devDependency Status](https://img.shields.io/david/dev/twbs/bootstrap.svg)](https://david-dm.org/twbs/bootstrap?type=dev)
[![Coverage Status](https://img.shields.io/coveralls/github/twbs/bootstrap/v4-dev.svg)](https://coveralls.io/github/twbs/bootstrap?branch=v4-dev)
[![CSS gzip size](https://img.badgesize.io/twbs/bootstrap/v4-dev/dist/css/bootstrap.min.css?compression=gzip&label=CSS+gzip+size)](https://github.com/twbs/bootstrap/tree/v4-dev/dist/css/bootstrap.min.css)
[![JS gzip size](https://img.badgesize.io/twbs/bootstrap/v4-dev/dist/js/bootstrap.min.js?compression=gzip&label=JS+gzip+size)](https://github.com/twbs/bootstrap/tree/v4-dev/dist/js/bootstrap.min.js)
[![BrowserStack Status](https://www.browserstack.com/automate/badge.svg?badge_key=SkxZcStBeExEdVJqQ2hWYnlWckpkNmNEY213SFp6WHFETWk2bGFuY3pCbz0tLXhqbHJsVlZhQnRBdEpod3NLSDMzaHc9PQ==--3d0b75245708616eb93113221beece33e680b229)](https://www.browserstack.com/automate/public-build/SkxZcStBeExEdVJqQ2hWYnlWckpkNmNEY213SFp6WHFETWk2bGFuY3pCbz0tLXhqbHJsVlZhQnRBdEpod3NLSDMzaHc9PQ==--3d0b75245708616eb93113221beece33e680b229)
[![Backers on Open Collective](https://opencollective.com/bootstrap/backers/badge.svg)](#backers)
[![Sponsors on Open Collective](https://opencollective.com/bootstrap/sponsors/badge.svg)](#sponsors)

## 包括什么

下载后，您将看到以下目录和文件，它们对公共资产进行逻辑分组，并提供编译后的和缩小后的变体。看起来就像下面这样:

```text
bootstrap/
└── dist/
    ├── css/
    │   ├── bootstrap-grid.css
    │   ├── bootstrap-grid.css.map
    │   ├── bootstrap-grid.min.css
    │   ├── bootstrap-grid.min.css.map
    │   ├── bootstrap-reboot.css
    │   ├── bootstrap-reboot.css.map
    │   ├── bootstrap-reboot.min.css
    │   ├── bootstrap-reboot.min.css.map
    │   ├── bootstrap.css
    │   ├── bootstrap.css.map
    │   ├── bootstrap.min.css
    │   └── bootstrap.min.css.map
    └── js/
        ├── bootstrap.bundle.js
        ├── bootstrap.bundle.js.map
        ├── bootstrap.bundle.min.js
        ├── bootstrap.bundle.min.js.map
        ├── bootstrap.js
        ├── bootstrap.js.map
        ├── bootstrap.min.js
        └── bootstrap.min.js.map
```

我们提供编译后的CSS和JS (`bootstrap.*`)，以及编译后的CSS和JS (`bootstrap.min.*`)。[源映射](https://developers.google.com/web/tools/chrome-devtools/debug/readability/source-maps) (`bootstrap.*.map`)可用于某些浏览器的开发工具。打包后的JS文件(`bootstrap.bundle).js`和缩小版 `bootstrap.bundl.min.js`)包括[Popper](https://popper.js.org/)，但不包括[jQuery](https://jquery.com/)。

## Bugs 和问题

有bug或问题吗?请先阅读[问题指南](https://github.com/twbs/bootstrap/blob/master/CONTRIBUTING.md#using-the-issue-tracker)，并搜索现有和已关闭的问题。如果你的问题或想法还没有解决，请打开一个新的问题。

## 文档

Bootstrap的文档包含在根目录中的这个repo中，它是用 [Jekyll](https://jekyllrb.com/) 构建的，并公开托管在GitHub页面上，地址是 [https://getbootstrap.com/](https://getbootstrap.com/)。文档也可以在本地运行。

Documentation search is powered by [Algolia's DocSearch](https://community.algolia.com/docsearch/). Working on our search? Be sure to set `debug: true` in `site/docs/4.3/assets/js/src/search.js` file.

### 在本地运行文档

1. 运行[工具设置](https://getbootstrap.com/docs/4.1/getting-started/build-tools/#tooling-setup)来安装Jekyll(站点构建器) 用`bundle install`安装Ruby依赖。
2. 运行 `npm install` 来安装 Node.js依赖.
3. 运行 `npm start` 编译CSS和JavaScript文件，生成我们的文档，并观察者模式监听更改。
4. 在浏览器中打开 `http://localhost:9001`, 就可以看到文档了.

通过阅读Jekyll的[文档](https://jekyllrb.com/docs/home/)了解关于使用Jekyll的更多信息。

### 以前版本的文档

您可以在下面找到我们之前发布的所有文档[https://getbootstrap.com/docs/versions/](https://getbootstrap.com/docs/versions/).

[以前的版本](https://github.com/twbs/bootstrap/releases)及其文档也可以下载。

## 贡献

请阅读我们的[投稿指南](https://github.com/twbs/bootstrap/blob/master/CONTRIBUTING.md)。其中包括开放问题的说明、编码标准和关于开发的说明。

此外，如果您的pull请求包含JavaScript补丁或特性，则必须包含[相关的单元测试](https://github.com/twbs/bootstrap/tree/master/js/tests)。所有HTML和CSS都应该符合[Code Guide](https://github.com/mdo/code-guide)，该指南由[Mark Otto](https://github.com/mdo)维护。

编辑器首选项可在[编辑器配置](https://github.com/twbs/bootstrap/blob/master/.editorconfig)中获得，以便在普通文本编辑器中轻松使用。更多信息，请访问[https://editorconfig.org/](https://editorconfig.org/)下载插件。

## 社区

获取有关Bootstrap开发的更新以及与项目维护人员和社区成员的聊天方式。

- 推特 [@getbootstrap on Twitter](https://twitter.com/getbootstrap).
- 阅读和订阅 [Bootstrap 官方博客](https://blog.getbootstrap.com/).
- 加入 [官方 Slack 房间](https://bootstrap-slack.herokuapp.com/).
- 在IRC中与其他人聊天。在`##bootstrap`通道的`irc.freenode.net`服务器上。
- 可以在 Stack Overflow ([`bootstrap-4`](https://stackoverflow.com/questions/tagged/bootstrap-4) 标签) 上找到帮助.
- 当开发者使用 [npm](https://www.npmjs.com/browse/keyword/bootstrap) 或类似的工具添加或修改Bootstrap的新功能时,应该在package文件中使用 `bootstrap` 关键字,来获得最多的传播的可能性.

## 版本

为了实现发布周期的透明性并努力保持向后兼容性，Bootstrap在[语义版本控制准则](https://semver.org/)下维护。有时我们搞砸了，但我们会尽可能遵守这些规则。

有关Bootstrap的每个发行版本的更改日志，请参阅[我们的GitHub项目的版本部分](https://github.com/twbs/bootstrap/releases)。 [官方Bootstrap博客](https://blog.getbootstrap.com/)上的发布公告帖子包含每个版本中最值得注意的更改的摘要。

## 创作者

**Mark Otto**

- [https://twitter.com/mdo](https://twitter.com/mdo)
- [https://github.com/mdo](https://github.com/mdo)

**Jacob Thornton**

- [https://twitter.com/fat](https://twitter.com/fat)
- [https://github.com/fat](https://github.com/fat)

## Thanks

<a href="https://www.browserstack.com/">
  <img src="https://live.browserstack.com/images/opensource/browserstack-logo.svg" alt="BrowserStack Logo" width="192" height="42">
</a>

感谢[ BrowserStack ](https://www.browserstack.com/)提供允许我们在真实浏览器中测试的基础架构！

## Backers

谢谢所有支持者！🙏 [[成为支持者](https://opencollective.com/bootstrap#backer)]

[![Bakers](https://opencollective.com/bootstrap/backers.svg?width=890)](https://opencollective.com/bootstrap#backers)

## 赞助商

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/bootstrap#sponsor)]

[![](https://opencollective.com/bootstrap/sponsor/0/avatar.svg)](https://opencollective.com/bootstrap/sponsor/0/website)
[![](https://opencollective.com/bootstrap/sponsor/1/avatar.svg)](https://opencollective.com/bootstrap/sponsor/1/website)
[![](https://opencollective.com/bootstrap/sponsor/2/avatar.svg)](https://opencollective.com/bootstrap/sponsor/2/website)
[![](https://opencollective.com/bootstrap/sponsor/3/avatar.svg)](https://opencollective.com/bootstrap/sponsor/3/website)
[![](https://opencollective.com/bootstrap/sponsor/4/avatar.svg)](https://opencollective.com/bootstrap/sponsor/4/website)
[![](https://opencollective.com/bootstrap/sponsor/5/avatar.svg)](https://opencollective.com/bootstrap/sponsor/5/website)
[![](https://opencollective.com/bootstrap/sponsor/6/avatar.svg)](https://opencollective.com/bootstrap/sponsor/6/website)
[![](https://opencollective.com/bootstrap/sponsor/7/avatar.svg)](https://opencollective.com/bootstrap/sponsor/7/website)
[![](https://opencollective.com/bootstrap/sponsor/8/avatar.svg)](https://opencollective.com/bootstrap/sponsor/8/website)
[![](https://opencollective.com/bootstrap/sponsor/9/avatar.svg)](https://opencollective.com/bootstrap/sponsor/9/website)

## 版权和许可

代码和文档版权所有2011-2018 [ Bootstrap Authors ](https://github.com/twbs/bootstrap/graphs/contributors)和[ Twitter，Inc。](https://twitter.com)在[麻省理工学院执照](https://github.com/twbs/bootstrap/blob/master/LICENSE)下发布的代码。 根据[知识共享](https://github.com/twbs/bootstrap/blob/master/docs/LICENSE)发布的文档。
