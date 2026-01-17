---
title: 回到 Arch Linux 和 KDE 的拥抱
date: 2026-01-12
tags:
	- 技术
    - 记录
cover: /img/abstract_blured.jpg
---

换了新电脑之后，~~旧的怎么办呢？当然是上转转~~我也就顺理成章开始用已经好多年没有再碰过的巨硬 Windows. 一直以来使用还算差强人意，除了很神秘地有一堆内置软件打架导致开机之后屏幕会变黄，打开任意带模糊的界面之后才能回到正常状态以外，还算是可用。

但是我最近越来越对系统不满意了，不论是各处丑的要命的 Win 11 界面，还是到处不统一的设计语言，又或者是各种令人厌烦的小毛病，~~或者我单纯就是KDE瘾犯了~~，总之我反正是受不了把这Windows再用下去了。
<!--more-->

## 软件列表和替代品

想要换系统，首先要考虑到现在的软件有没有替换或者 Linux 版。所以我得先列一下现用的软件，方便按照列表安装。

### 社交软件：Discord, 微信，QQ，Telegram
这些软件现在都有原生的 Linux 版本，AUR 安装即可。

微信有一个沙盒包装版本`wechat`，据描述似乎更符合 Linux 哲学。

相比之下，QQ 只有 bwarp 沙盒版本，而bwarp相比上面说的 `wechat` 使用的 `portable` 沙盒似乎安全性较低。所以还是直接装 `linuxqq` 好了。

### 编程软件
用vscode很久了，感觉还是得接着用。不过我也想重新试试zed了
IDEA可以装社区版。
Godot 装 `godot`即可。

### 影音娱乐
vlc: `vlc`.
网易云音乐可以用官方包（但是之前的电脑上会神秘地出现无法访问网络的问题，导致我只好用社区的gtk版本）

### 工具
#### 编曲
从来没有搞懂过如何优雅地使用wine, 但是fl还是必须用wine的。如果不用fl，可以用bitwig。去毛子磁力网站上面
找一个下下来即可。可以用yabridge来桥接适用于windows的vst和clap插件。

#### 建模
blender有linux版本。

#### 录屏
kde自带录屏工具（不知为何之前用的时候老是会冻结），obs也有linux版本。

#### 下载
kde开发组有ktorrent。

#### 浏览器
`microsoftedge-stable-bin`.

#### 文件搜索
[fsearch](https://github.com/cboxdoerfer/fsearch)是一个很接近于windows上Everything体验的软件,虽然不像Everything一般占用小，也足够日常使用了。

安装aur的`fsearch` 软件包。

#### Office类
wps有linux版，但是我不清楚如果用linux版还能不能用上教育优惠。貌似只要登录学校邮箱即可?

### 驱动等

1. 独显
众所周知nvidia是出名地不支持linux，好在近些年情况有所改善。  
可以安装`nvidia-open`驱动。

[Arch Wiki](https://wiki.archlinuxcn.org/wiki/NVIDIA)说使用`nvidia-open`驱动时无法在Turing架构启用D3电源管理，好在5070是Blackwell(手动滑稽)

nvidia的图形加速在`nvidia-utils`包里完全包含，包含64位的OpenGL, Vulkan和DDX驱动支持。这个包还包含了硬解支持。

2. 集显
基本驱动已经在`linux`包里面包含了。

为了启用图形加速和视频硬解等，需要安装`mesa xf86-video-amdgpu vulkan-radeon`.

安装`libva-utils`并且运行`vainfo`，如果看到很多 VAEntrypointVLD 的列表，说明硬解已开启。

3. 集显-独显切换

使用`optimus-manager`。安装`optimus-manager-git`和`optimus-manager-qt`。

### 桌面环境
当然是我最爱的kde。安装`plasma`包组。  
同时，安装`sddm sddm-kcm`。  

### 安装
首先要先把bitlocker关了，不然根本无法调整Windows分区大小。
然后在PE系统调整分区大小。