---
title: 配置 V2Ray 核心
---

# 配置 V2Ray 核心

在成功安装 Qv2ray 后，在真正使用 Qv2ray 之前，还需要基于 v2ray 核心完成一些必要的配置。

## 下载 V2Ray 核心文件

由于一些原因，Qv2ray 本身并**不包含** V2ray 的核心可执行文件，这些核心文件来自一个叫做 V2Ray core 的项目，需要用户手动下载安装到指定位置。请前往 [v2ray/v2ray-core 官方 Release 页面](https://github.com/v2ray/v2ray-core/releases)，并下载最新的符合当前系统版本的稳定版软件包。

### Linux

如果你正在使用的 Linux 发行版拥有一个可以自动安装 V2Ray 核心文件的软件包管理系统，那通过软件包管理安装 Qv2ray 是最好的选择，因为系统可以自动处理 v2ray 核心的更新。例如，对于 Arch Linux 用户而言，你需要安装 `v2ray`、`v2ray-geoip` 和 `v2ray-domain-list-community` 这三个软件包。对于其它的 Linux 发行版，大多数用户可以下载 `v2ray-linux-64.zip`这个 zip 包以获取 V2Ray 内核。

::: danger 警告

如果你在 `x86_64`（`amd64`）平台上运行 Qv2ray，请不要下载 `v2ray-linux-arm64.zip`。明确地说，`arm64` 和 `amd64` 是基于**完全不同的**架构的 CPU。请确保你不会这样做。

:::

### Microsoft Windows

**提示：** Windows XP、Windows Vista 以及更低版本的 Windows 系统不被 V2Ray 内核所支持。

`v2ray-windows-32.zip`适用于全版本的 Windows 系统，x86_64 架构（即通常所说的 64 位）的用户可以使用`v2ray-windows-64.zip`以获得更好的性能。

### macOS / OS X

` v2ray-macos.zip` 是适用于 macOS / OS X 的内核。

## 放置你的 V2Ray 核心

将 v2ray 核心文件提取到一个固定的位置。 默认情况下，建议将文件提取到 `$QV2RAY_CONFIG_PATH/vcore` 中，其中 `$QV2RAY_CONFIG_PATH` 是 Qv2ray 存储其数据的目录。

目录 `vcore` 可能位于以下位置之一：

- `./` （在 Qv2ray 可执行文件旁边，建议 Windows 用户使用）

- `~/.qv2ray/`（在 home 文件夹的独立目录中）

- `~/.config/qv2ray` （标准 XDG 配置路径）

确保这些文件直接存在于 `vcore` 目录中，Windows 系统下可能还会看到两个程序有`.exe`的后缀:

```
geoip.dat geosite.dat v2ctl v2ray
```

:::warning 对于 Linux / macOS 用户的温馨提示

如果是从 GitHub 下载的 V2Ray 内核，您应该始终为 `v2ray` 和 `v2ctl` 授予**可执行权限**。这通常通过在这些文件上执行 `chmod + x` 来完成，或者在文件管理器里面右击这两个程序，然后给予可执行权限。

:::

## 配置 Qv2ray 的核心调用

打开 Qv2ray 并进入 Preference 窗口。在 **一般设置 - V2Ray 设置** 中，配置如下：

- **核心可执行文件路径**：将此设置为您的 V2Ray 可执行文件所在的位置。 这可以是 Windows 上的 `v2ray.exe` 的完整路径，也可以是 Linux / macOS 上的 `v2ray` 可执行文件的完整路径。

- **V2ray 资源目录**：将其设置为 `geoip.dat` 和 `geosite.dat` 所在的位置。

配置完成后，你可以点击 Check V2Ray Core Settings 按钮来验证你的 V2Ray Core Settings。 重复尝试，直到你通过了检查。
