---
title: 下载 Qv2ray
sidebarDepth: 2
---

# 下载 Qv2ray

你需要先下载 Qv2ray 的某个版本的 Release 文件才能开始使用 Qv2ray。

## 1 方法一：下载 GitHub Release 二进制文件

从 [Qv2ray GitHub Release](https://github.com/Qv2ray/Qv2ray/releases) 页面下载 Qv2ray 编译好的二进制版本。 推荐 **Windows** 和 **macOS** 用户采取这种方法。 这种方法同样适用于没有合适的 Qv2ray 软件包的 Linux 发行版来安装，因为他们可以使用我们的 AppImage 发行版。

遵循如下步骤:

1. 在浏览器中打开 [Qv2ray GitHub Release 页面](https://github.com/Qv2ray/Qv2ray/releases) 。
2. 选择一个 Release 版本。 或者直接下载[最新版](https://github.com/Qv2ray/Qv2ray/releases/latest)。
3. 选择一个能在你的系统平台上运行的软件版本，然后下载。 例如:
   - 对于 Windows x86_64 (即常说的 64 位系统） 用户： `Qv2ray.VERSION.win-x64.zip`
   - 对于 Windows ARM64 （高通 CPU）用户与 Windows x86 （即常说的 32 位系统）用户：`Qv2ray.VERSION.win-x86.zip`
   - 对于 Windows XP、Windows Vista、Windows RT 8、Windows RT 8.1 以及 Windows 10 ARM32 用户：您的系统不被 V2Ray 项目所支持，因此也不被 Qv2ray 所支持。
   - 对于 macOS 用户：`Qv2ray.VERSION.macOS-x64.tar.gz`
   - 对于 Ubuntu 19.04 / Debian 10 (或更高)： `qv2ray_VERSION_amd64.deb`
   - 对于全部 Linux 64bit 用户：`Qv2ray.VERSION.linux-x64.AppImage`

其中 `VERSION` 是当前 Release 的版本。

:::tip Linux AppImage 用户注意事项

虽然我们已经将 `glibc` 和一些基本的 C++ 库绑定到 **AppImage** 包中，以支持一些旧的但是受支持的发行版，但是强烈建议您使用发行版 / 操作系统的新版本。

:::

## 2 方法二：GitHub Actions 编译版

不喜欢稳定版的功能，想要尝试不断开发中的新功能？你可以下载 GitHub Actions 中的编译版本：

1. 在浏览器中打开 [Qv2ray GitHub Actions 页面](https://github.com/Qv2ray/Qv2ray/actions) 。
2. 选择一个最近的成功编译的版本（会显示为✔️）然后点击。 你会进入这个版本的详细页面。比如 [这里](https://github.com/Qv2ray/Qv2ray/commit/de88bfc69e50bf7c4ce034756720bf06df42612a/checks?check_suite_id=377218225).
3. 点击 **Artifacts** 展开下拉菜单, 然后根据你的平台选择一个二进制包并下载。

:::tip 提示

你必须先登录 GitHub 账号才能访问 GitHub Actions 进行白嫖~

:::

## 3 方法三：在 Linux 发行版的软件包管理系统中安装

### 3.1 Arch Linux（或基于 Arch 的发行版）

#### 3.1.1 直接从 archlinuxcn 安装（推荐）

我们已登陆 `archlinuxcn` 仓库。若您已在使用，只需在你的终端输入：

```bash
sudo pacman -Syy qv2ray # 或者 qv2ray-dev-git, 见下
```

然后就 OK 啦！

:::tip 提示

你可能还需要安装 `v2ray` 包组来使用系统 V2Ray 核心。

:::

#### 3.1.2 使用 AUR Helper 从 AUR 获取

您可以从 AUR (Arch User Repository, [AUR (en)-Home](https://aur.archlinux.org/)) 获得官方维护的 `PKGBUILD` 文件，这将指导 Qv2ray 的构建过程。

您可以使用 AUR Helper（如 `yay`、`yaourt`、`pikaur` 等）来自动处理 AUR 包的构建过程。

:::tip 提醒

下面的例子将会使用 `yay`。对于其他 AUR Helper，检查各自文档中的用法。

:::

首先在 AUR 中搜索 `qv2ray`：

```bash
$ yay -Ss qv2ray
aur/qv2ray-dev-git 1.99.4.r47514d2-1 (+2 0.98%)
     Qt cross platform v2ray GUI client (Dev branch build release)
aur/qv2ray 1.3.8.0-1 (+4 1.23%)
     Qt cross platform v2ray GUI client
```

然后，选择合适的版本来安装 Qv2ray：

- **稳定版本**，使用名为 `qv2ray` 的包。这个软件包是基于 Git 仓库的 `master` 分支构建的，对于谨慎的用户来说应该足够稳定。

- **开发版本**，使用名为 `qv2ray-dev-git` 的包。这个包是从 Git 仓库的 `dev` 分支构建的。除了最新的特性和改进之外，使用不稳定的发行版还存在潜在的风险。

根据您的实际情况选择。在这里，我们选择安装 `qv2ray-dev-git`：

```bash
$ yay -S qv2ray-dev-git
```

Qv2ray 在完成命令后就可以使用了。

#### 3.1.3 从 AUR 获取（硬核方法）

您可能不希望使用 AUR Helper 从 AUR 安装 Qv2ray。请见下面的例子：

```bash
# 1. Clone AUR 仓库 (例如 `qv2ray-dev-git`)：
$ git clone https://aur.archlinux.org/qv2ray-dev-git.git

# 2. 进入 `PKGBUILD` 文件夹：
$ cd qv2ray-dev-git

# 3. 构建 Qv2ray：
$ makepkg -sf

# 4. 安装构建得到的软件包：
$ sudo pacman -U qv2ray-dev-git-v1.99.4.2550-1-x86_64.pkg.tar.zst
```

这样就可以了。

:::tip 提示

包文件名（`qv2ray-dev-git-v1.99.4.2550-1-x86_64.pkg.tar.zst`）取决于 Qv2ray 的实际版本，在你的机器上可能有所不同。

:::

### 3.2 openSUSE

> openSUSE 上的 Qv2ray 由 [@zzndb](https://github.com/zzndb) 于 [openSUSE Build Service](https://build.opensuse.org/) 提供。

::: tip

由于 Qt 版本的限制，包管理器安装方式我们**只支持 Tumbleweeds，Leap 15.2 和之后的 Leap 版本**。

:::

与 AUR 类似，Qv2ray 也有两个版本，你可以根据自己的口味来选择：

- 稳定版： [Qv2ray](https://build.opensuse.org/package/show/home:zzndb/Qv2ray)
- 预览版： [Qv2ray-preview](https://build.opensuse.org/package/show/home:zzndb/Qv2ray-preview)

或者你可以直接从下面的链接获取更详细的安装指导:

- 获取稳定版: [Qv2ray](https://software.opensuse.org/download.html?project=home%3Azzndb&package=Qv2ray)
- 获取预览版: [Qv2ray-preview](https://software.opensuse.org/download.html?project=home%3Azzndb&package=Qv2ray-preview)

## 4 方法四：在 Linux 通用的应用商店中安装

### 4.1 Snapcraft

请参照我们的 [Snapcraft](https://snapcraft.io/qv2ray) 页面上的说明。

```bash
# 安装 Qv2ray:
$ snap install qv2ray
# （或者用 snap install qv2ray --edge 来使用开发版）

# 升级 Qv2ray：
$ snap refresh qv2ray
```
**注意**:在使用 Snapcraft 安装应用之前，你需要确保 `snap` 命令已经正确被设置好。Ubuntu 18.04 LTS 以上系统自带此命令。

### 4.2 Flathub

1. 设置 Flatpak 环境：[官方文档](https://flatpak.org/setup/)。

2. 安装 Qv2ray：

```bash
# 安装 Qv2ray：
$ flatpak install com.github.Qv2ray

# 升级 Qv2ray：
$ flatpak update
```

## 5 方法五：从源码编译

- 请参考 [手动构建 Qv2ray](/hacking/manuallybuild/) 页面。
