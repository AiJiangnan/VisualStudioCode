---
Order: 3
Area: setup
TOCTitle: Mac
ContentId: EEADB50A-F5E3-41E9-89DA-35F165196691
PageTitle: Running Visual Studio Code on Mac
DateApproved: 11/8/2017
MetaDescription: Get Visual Studio Code up and running on Mac.
Translate: AiJiangnan
Date: 12/22/2017
---
# Mac - VS Code

## 安装

1. 下载Mac版 [Visual Studio Code](https://go.microsoft.com/fwlink/?LinkID=534106) 。
2. 双击下载包解压内容。
3. 将`Visual Studio Code.app`拖曳到`Applications`文件夹下，使它可以在`Launchpad`上启动。
4. 右击图标选择`Options`, `Keep in Dock`来添加到程序坞。

## 命令行运行

将VS Code添加到环境变量中，可以在终端中运行指令`code`来启动：

- 启动VS Code
- 打开**命令行面板**(`Ctrl+Shift+P`)然后输入'shell command'，选择**Shell Command: Install 'code' command in PATH**

![Mac shell commands](images/mac/shell-command.png)

- 重启终端使新的`$PATH`变量生效，你只需输入`code`，就可以在任何文件夹下编辑文件

>**注意：**如果已经存在老版本的`code`指令在你的`.bash_profile` 文件（或其它等价的文件）中，先删除它然后再执行上面的 **Shell Command: Install 'code' command in PATH**命令。

手动添加VS Code到环境变量：

```bash
cat << EOF >> ~/.bash_profile
# Add Visual Studio Code (code)
export PATH="$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
EOF
```

## Touch Bar支持

最新的VS Code将之前导航栏上的一些动作添加到了你的Touch Bar上，比如调试器。

![Mac Touch Bar](images/mac/touchbar.gif)

## 更新

VS Code每月发布一次更新，并且支持自动更新。如果VS Code提示你更新了，而后你只需接受，就可以安装最新版本（不需要做任何多余的事）。

## 首选项

你可以配置VS Code的设置、颜色主题和自定义快捷键，设置菜单组在**文件** > **首选项**中，在Mac上，**首选项**菜单组在**代码**菜单里，而不是**文件**菜单下。

## 后续

当你安装好了VS Code，这些话题会让你学到更多东西：

* [组件](/docs/setup/additional-components.md) - 学习怎么安装Git、Node.js、TypeScript和像Yeoman一样的工具。
* [UI](/docs/getstarted/userinterface.md) - VS Code的核心方向。
* [设置](/docs/getstarted/settings.md) - 学习如何对VS Code进行偏好设置。

## 常见问题

**问：**Mono和EI Capitan

**答：**在安装OS X10.11EI Capitan公共Beta版后VS Code不能运行Mono？

运行下面指令：

```bash
brew update
brew reinstall mono
```