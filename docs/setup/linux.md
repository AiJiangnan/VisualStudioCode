---
Order: 2
Area: setup
TOCTitle: Linux
ContentId: 7FDF94DB-3527-4296-BE1C-493495B89408
PageTitle: Running Visual Studio Code on Linux
DateApproved: 11/8/2017
MetaDescription: Get Visual Studio Code up and running on Linux.
Translate: AiJiangnan
Date: 12/3/2017
---
# Linux - VS Code

## 安装

### 基于Debian和Ubuntu

基于Debian/Ubuntu最简单的安装方式是下载 [.deb包 (64-bit)](https://go.microsoft.com/fwlink/?LinkID=760868) ，然后通过图形软件中心安装，如果不可用，也可以使用下面的指令安装：

```bash
sudo dpkg -i <file>.deb
sudo apt-get install -f # Install dependencies
```

在使用常规系统机制下，在安装.deb包的时候会自动安装apt仓库和签名密钥来自动更新。注意32位版本和.tar.gz二进制压缩版本都有。

通常使用下面的脚本来安装仓库和密钥：

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
```

使用下面的脚本来更新程序包和安装程序包：

```bash
sudo apt-get update
sudo apt-get install code # or code-insiders
```

### 基于RHEL、Fedora和CentOS

我们一般只将64位版本的VS Code放在yum仓库上，下面的脚本用来安装密钥和仓库：

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
```

使用`dnf`指令来更新和安装包（Fedora 22或以上）：

```bash
dnf check-update
sudo dnf install code
```

老版本使用`yum`指令：

```bash
yum check-update
sudo yum install code
```

### 基于openSUSE和SLE

基于openSUSE和SLE的系统也有yum仓库，使用下面的脚本安装密钥和仓库：

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/vscode.repo'
```

使用下面的脚本更新和安装程序包：

```bash
sudo zypper refresh
sudo zypper install code
```

### 基于Arch Linux的AUR包

社区维护的Arch User Repository (AUR)包 [VS Code](https://aur.archlinux.org/packages/visual-studio-code) 。

### 基于NixOS的Nix包（或任何基于Nix包的Linux）

在nixpkgs仓库中有社区维护的 [Nix package](https://github.com/NixOS/nixpkgs/blob/master/pkgs/applications/editors/vscode/default.nix) 。要使用Nix，在`config.nix`中设置`allowUnfree`选项为true，并设置为可执行：

```bash
nix-env -i vscode
```

### 手动安装.rpm包

64位版本的[.rpm package (64-bit)](https://go.microsoft.com/fwlink/?LinkID=760867)也常被下载和安装，然而只有下载了仓库才会自动更新。一旦你使用包管理器下载，就可以安装了，例如使用`dnf`指令：

```bash
sudo dnf install <file>.rpm
```

注意：32位版本的和.tar.gz二进制版本的也会提供下载。

## 更新

VS Code每月更新一次，你可以通过检查更新来看一次新版本的特性。如果VS Code仓库已经安装好了，你就可以使用你系统的程序包管理器像其他软件包一样来自动更新VS Code。

## Node.js

Node.js是一个流行的简单的构建和运行JavaScript应用的开发平台和运行环境。它包含[NPM](https://www.npmjs.com/)，一个Node.js模块的包管理器。我们的文档会多次提及Node.js和NPM，并且一些可选的VS Code工具也会要求Node.js。

如果你想要在Linux安装Node.js，看[安装Node.js via包管理器](https://nodejs.org/en/download/package-manager)来找到适用于你的Linux发行版的Node.js包。

了解更多关于JavaScript和Node.js，请看我们的[Node.js教程](/docs/nodejs/nodejs-tutorial.md)，在这里你将会学习如何使用VS Code来运行和调试Node.js应用。

## 设置默认编辑器

### xdg-open

使用下面的`xdg-open`指令可以设置纯文本文件（`text/plain`）的默认编辑器：

```bash
xdg-mime default code.desktop text/plain
```

### Debian alternatives system

基于Debian发行版使用[alternatives system](https://wiki.debian.org/DebianAlternatives)来设置默认编辑器，不包括mime类型，使用下面的指令来设置：

```bash
sudo update-alternatives --set editor /usr/bin/code
```

## 后续

当你安装好了VS Code，这些话题会让你学到更多东西：

* [组件](/docs/setup/additional-components.md) - 学习怎么安装Git、Node.js、TypeScript和像Yeoman一样的工具。
* [UI](/docs/getstarted/userinterface.md) - VS Code的核心方向。
* [设置](/docs/getstarted/settings.md) - 学习如何对VS Code进行偏好设置。

## 常见问题

### Azure虚拟机问题

**问：**提示“Running without the SUID sandbox”错误？

**答：**你可以大胆地忽略这个错误。

### Debian中删除文件到回收站

如果你在Debian操作系统中的VS Code文件浏览器中删除文件报错，它可能是因为VS Code使用的回收站不存在。

运行下面的指令来解决这个问题：

```bash
sudo apt-get install gvfs-bin
```

### 超出系统限制错误

当你看到这个错误，它意味着VS Code文件监视器运行超出限制了。运行下面指令来查看当前限制：

```bash
cat /proc/sys/fs/inotify/max_user_watches
```

这个限制可以通过编辑`/etc/sysctl.conf`在文件末尾添加下面的一行可以增加它的最大值。

```bash
fs.inotify.max_user_watches=524288
```

设置好的新的值使用指令`sudo sysctl -p`来重新加载。注意[Arch Linux](https://www.archlinux.org/)与此有点不同，[请查看更多帮助](https://github.com/guard/listen/wiki/Increasing-the-amount-of-inotify-watchers)。

当文件监视的最大值为524288时，如果你的运行环境内存不够，你应该设置一个更小的值。每个文件在[540 bytes (32-bit)或~1kB (64-bit)](https://stackoverflow.com/a/7091897/1156119)，所以会产生所有524288的监视会消耗256MB (32-bit)或512MB (64-bit)。

### Ubuntu中文字符不可见

选择应用菜单**文件 **> **首选项** > **设置**，然后设置`editor.fontFamily`项如下：

```json
    "editor.fontFamily": "Droid Sans Mono, Droid Sans Fallback"
```

### git安装失败

导致软件安装失败的一个典型的问题就是包管理器版本较老，使用下面指令更新后再安装：

```bash
# For .deb
sudo apt-get update

# For .rpm (Fedora 21 and below)
sudo yum update

# For .rpm (Fedora 22 and above)
sudo dnf update
```

### Ubuntu中使用code指令不能置顶打开窗口

在Ubuntu中，当VS Code在当前目录下已经运行的时候不能使VS Code置顶，这是由于系统不支持`ccsm`，运行下面指令安装：

```bash
# Install
sudo apt-get update
sudo apt-get install compizconfig-settings-manager

# Run
ccsm
```

