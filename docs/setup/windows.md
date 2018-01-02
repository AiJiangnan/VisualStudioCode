---
Order: 4
Area: setup
TOCTitle: Windows
ContentId: 4670C281-5761-46E6-8C46-10D523946FFB
PageTitle: Running Visual Studio Code on Windows
DateApproved: 11/8/2017
MetaDescription: Get Visual Studio Code up and running on Windows
Date: 2018.1.2
translate: AiJiangnan
---
# Windows - VS Code

## 安装

1. 下载Windows版本的 [VS Code](https://go.microsoft.com/fwlink/?LinkID=534107) 安装包。
2. 下载完后运行`VSCodeSetup-version.exe`进行安装，只需一点点时间。
3. 在64位计算机上VS Code默认安装路径为 `C:\Program Files\Microsoft VS Code` 。

你也可以下载VS Code的Zip压缩包。

>**注意：**VS Code要求.NET Framework 4.5.2或更高版本的环境。如果你的系统是Window 7，需要安装 [.NET Framework 4.5.2](https://www.microsoft.com/en-us/download/details.aspx?id=42643) 或以上版本的环境。

>**提示：**安装时可选设置将VS Code添加到环境变量 `%PATH%` 中，添加之后就可以在控制台中输入`code .`用VS Code打开当前文件夹。在安装后需要重启控制台来使你修改的环境变量 `%PATH%` 生效。

## 32位版本

如果你需要下载32位版本的VS Code，[VS Code](https://go.microsoft.com/fwlink/?LinkId=723965) 安装包和 [VS Code](https://go.microsoft.com/fwlink/?LinkID=733265) Zip压缩包都有。

## 更新

VS Code每月提供一次更新，并且可以自动更新。你只需通过VS Code的更新提示就可获得最新版本，而不需要做任何操作。如果你想设置手动更新，请看[如何禁用自动更新？](/docs/supporting/faq.md#how-do-i-opt-out-of-vs-code-autoupdates)。

## 后续

Once you have installed VS Code, these topics will help you learn more about VS Code:

* [组件](/docs/setup/additional-components.md) - 学习怎么安装Git、Node.js、TypeScript和像Yeoman一样的工具。
* [UI](/docs/getstarted/userinterface.md) - VS Code的核心方向。
* [设置](/docs/getstarted/settings.md) - 学习如何对VS Code进行偏好设置。

## 常见问题

### 安装问题

使用压缩包而不是安装包，解压到 **Program Files** 文件夹下即可。

>**注意：**当通过压缩包渠道安装的VS Code，你需要手动要更新每个版本。

### 图标不显示

在Windows 7或8上安装VS Code，为什么在工作区和编辑区一些图标不显示？

VS Code使用的是 [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics) 格式的图标，而且我们已经知道`.SVG` 扩展名文件是否与 `image/svg+xml` 有关，我们可以进行一些设置来修复它，如下：

使用命令提示符：

1. 打开管理员权限的命令提示符。
2. 输入 `REG ADD HKCR\.svg /f /v "Content Type" /t REG_SZ /d image/svg+xml` 。

使用注册表编辑器（regedit）：

1. 打开 `regedit`.
2. 选择 `HKEY_CLASSES_ROOT` 键.
3. 找到 `.svg` 键.
4. 设置 `Content Type` 的值为 `image/svg+xml`.
5. 退出 `regedit`.
