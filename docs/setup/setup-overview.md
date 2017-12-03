---
Order: 1
Area: setup
TOCTitle: Overview
PageTitle: Setup VS Code
MetaDescription: Get Visual Studio Code up and running.
MetaSocialImage: quicksetup_QuickSetup.png
Translate: AiJiangnan
Date: 12/1/2017
---
# Visual Studio Code

使用Visual Studio Code是快速的和简单的，它很小以致于你只需花少许的时间来下载来试一试。

## 平台

VS Code是一款可以运行在Mac、Linux和Windows操作系统上的免费代码编辑器。下面是各平台的教程：

* [Mac](/docs/setup/mac.md)
* [Linux](/docs/setup/linux.md)
* [Windows](/docs/setup/windows.md)

VS Code是轻量的，它可以运行在大多数版本的硬件和平台上，你可以看[系统要求]()来检查你的电脑配置是否支持。

## 更新

VS Code会每月发布一个新的版本来推出新特性和重大的Bug修复。大多数平台支持自动更新，并且在有新版本更新的时候提示你。你也可以使用**帮助** >**检查更新...**来手动获取更新。

>注意：如果你更愿意按照自己的计划更新，你可以设置[禁用自动更新]()。

## 内测

如果你想尝试我们的日更内测版本来更早地了解新特性或者参证一些Bug的修复，你可以安装[内测版]()。内测版和月更的稳定版可以同时安装在你的机器上，并且都是免费易安装的。内测版每天更新都是由同样的开发团队来完成的，并且我们真的很愿意让人们来尝试我们的新特性并提供一些反馈。

## 组件

VS Code首先是一款以小为美的编辑器，它不像传统的集成开发环境尽其所能地包含所有的东西，你只需选择你关心的开发技术来进行安装。在你阅读平台指南了解自定义VS Code安装后，一定要看看[组件]()主题的教程。

## 扩展

VS Code的[扩展]()添加了额外的第三方支持：

* 语言 - [C++](/docs/languages/cpp.md), [C#](/docs/languages/csharp.md), [Go](/docs/languages/go.md), [Java](/docs/languages/java.md), [Python](/docs/languages/python.md)
* 工具 - [ESLint](https://marketplace.visualstudio.com/items/dbaeumer.vscode-eslint), [JSHint](https://marketplace.visualstudio.com/items/dbaeumer.jshint) , [PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell), [Visual Studio Team Services](https://marketplace.visualstudio.com/items?itemName=ms-vsts.team)
* 调试器 - [Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome), [PHP XDebug](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-debug).
* 快捷键 - [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim), [Sublime Text](https://marketplace.visualstudio.com/items?itemName=ms-vscode.sublime-keybindings), [IntelliJ](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings), [Emacs](https://marketplace.visualstudio.com/items?itemName=hiro-sun.vscode-emacs), [Atom](https://marketplace.visualstudio.com/items?itemName=ms-vscode.atom-keybindings), [Visual Studio](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vs-keybindings), [Eclipse](https://marketplace.visualstudio.com/items?itemName=alphabotsec.vscode-eclipse-keybindings)

你添加的扩展集成进了VS Code的用户界面、指令和任务运行系统，所以你可以很容易地通过使用VS Code共享的接口来适应不同的技术工作，你可以去[应用商城](https://marketplace.visualstudio.com/vscode)看看已经支持的扩展。

## 后续

当你安装并配置好了VS Code，这些话题能让你更深入了解VS Code：

* [组件](/docs/setup/additional-components.md) - 学习怎么安装Git、Node.js、TypeScript和像Yeoman一样的工具。
* [UI](/docs/getstarted/userinterface.md) - VS Code的核心方向。
* [编辑](/docs/editor/codebasics.md) - 学习强大的VS Code文本编辑器。
* [导航](/docs/editor/editingevolved.md) - 快速地在源代码中来回穿梭。
* [调试](/docs/editor/debugging.md) - 在VS Code中可以直接调试源代码。
* [代理](/docs/setup/network.md) - 配置代理服务器。

如果你想要一些东西运行更快，你可以参考[Node.js](/docs/nodejs/nodejs-tutorial.md)，看看VS Code是如何快速调试一个Node.js的web应用程序的。

## 常见问题

**问：使用VS Code有什么系统要求？**

**答：**请参阅[系统要求](https://code.visualstudio.com/docs/supporting/requirements) 。

**问：VS Code有多大？**

**答：**VS Code的下载包 (< 100 MB) ，安装后硬盘占用小于200MB。

**问：如何新建和运行一个项目？**

**答：**VS Code没有传统的**文件** > **新建项目**这样的菜单，也没有预装的项目模板。你只需按照你的开发意愿来添加[组件]()和构建工具。像[Yeoman](http://yeoman.io/)这样的构建工具，像使用[NPM](https://www.npmjs.com/)包管理器来获取大量的模块。

**问：怎么查看VS Code的运行版本？**

**答：**在Linux和Windows上，选择**帮助** > **关于**，在Mac上，选择**代码** > **关于Visual Studio Code**。

**问：VS Code提示安装有误？**

**答：**VS Code检测到一些安装文件被修改了，可能是被一个组件修改的。重装后VS Code会替换被修改的文件。登录[FAQ topic](https://code.visualstudio.com/docs/supporting/faq#_installation-appears-to-be-corrupt)查看更多详情。