<p align="center">
  <img src="logo.png"/>
</p>

**[English](README.md "Click to go")** | **中文**

*Lightly* 是breeze主题风格的一个分支，旨在视觉上现代和简约。

## 开发 ⚠️

Lightly 是一个还在开发中的主题，还有很多地方要改变，所以能猜到有BUG！某些应用程序可能会突然崩溃或故障。

如果您有任何反馈或遇到一些错误，请随时提一个issue或者pr(功能类请往父分支提交，这里只处理翻译内容).

## 截图

![默认](https://github.com/Luwx/Lightly/blob/master/Lightly-default.png)

关闭透明Dolphin界面和没有侧边栏透明:
![custom](https://github.com/Luwx/Lightly/blob/master/Lightly-custom.png)

采用全窗口毛玻璃方案 (目前全窗口毛玻璃配色方案非常有问题，不完全支持):
![fullglass](https://github.com/Luwx/Lightly/blob/master/Lightly-fullglass.png)

## 配置

![配置页面](https://github.com/Luwx/Lightly/blob/master/config.png)

Lightly 配置页面可以在 KDE 系统设置的 应用程序风格 部分下找到。

这些选项大部分都继承自 Breeze 风格，但 Lightly 有一些默认启用的专有选项，包括:

* 透明 Dolphin 界面 (在 **外框** 选项卡)。 此选项禁用 Dolphin 视图小部件的背景和阴影，并在视图具有可滚动内容时绘制顶部和底部分隔符。

* 侧边栏不透明度 (在 **透明度** 选项卡)。 默认为60，低于100会自动绘制阴影. 

工具栏和菜单栏将遵循 **标题栏** 不透明度。 要配置标题栏不透明度， 您将不得不直接更改配色方案文件 ~/.local/share/color-schemes。打开您想要的配色方案，然后， 在 `[WM]` 部分， 向 `activeBackground`和`inactiveBackground`添加四个值, 例如 `activeBackground=0,0,0,127` 其中最后一个值是alpha， 范围从 0 (完全透明) 到 255(完全不透明)。

## 安装

### 在 ArchLinux 及其 [derivatives](https://wiki.archlinux.org/title/Arch-based_distributions) 上从 [chaotic-aur](https://aur.chaotic.cx/) 轻松安装

  1. 按照 [此处](https://aur.chaotic.cx/) 的说明设置 chaotic-aur
  2. 运行: `sudo pacman -Syyu lightly-qt`

### 从 openSUSE Tumbleweed 上的 RPM 存储库安装 Lightly:

1. 添加"sputnik-look-and-feel"存储库:
`sudo zypper ar -ef https://download.opensuse.org/repositories/home:/sputnik:/look-and-feel/openSUSE_Tumbleweed/ sputnik-look-and-feel`
2. 刷新存储库列表:`sudo zypper ref`
3. 您将收到有关收到新存储库密钥的通知。 系统会询问您是否要接受密钥。 此存储库是在 OBS 上创建的。 所有构建都是可重现的。
输入"`a`"并按回车键。
4. 安装Lightly:`sudo zypper in Lightly`

### Fedora

```bash
sudo dnf install Lightly
```

### Fedora 32 RPM 仓库

1. 创建repo文件:

```bash
echo  "[sputnik-look-and-feel]
name=Look And Feel (Fedora_32)
type=rpm-md
baseurl=https://download.opensuse.org/repositories/home:/sputnik:/look-and-feel/Fedora_32/
gpgcheck=1
gpgkey=https://download.opensuse.org/repositories/home:/sputnik:/look-and-feel/Fedora_32/repodata/repomd.xml.key
enabled=1" | sudo tee -a /etc/yum.repos.d/sputnik-look-and-feel.repo
```

1. 安装Lightly:
```sudo dnf install Lightly```

## 手动安装(没错，这个仓库的中文语言版本只能手动安装)

### 依赖项

摘自 https://github.com/n4n0GH/hello

#### Ubuntu

```bash
sudo apt install cmake build-essential libkf5config-dev libkdecorations2-dev libqt5x11extras5-dev qtdeclarative5-dev extra-cmake-modules libkf5guiaddons-dev libkf5configwidgets-dev libkf5windowsystem-dev libkf5coreaddons-dev libkf5iconthemes-dev gettext qt3d5-dev
```

#### Arch Linux

```bash
sudo pacman -S cmake extra-cmake-modules kdecoration qt5-declarative qt5-x11extras
```

#### Fedora

```bash
sudo dnf install cmake extra-cmake-modules "cmake(Qt5Core)" "cmake(Qt5Gui)" "cmake(Qt5DBus)" "cmake(Qt5X11Extras)" "cmake(KF5GuiAddons)" "cmake(KF5WindowSystem)" "cmake(KF5I18n)" "cmake(KDecoration2)" "cmake(KF5CoreAddons)" "cmake(KF5ConfigWidgets)" "cmake(Qt5UiTools)" "cmake(KF5GlobalAccel)" "cmake(KF5IconThemes)" kwin-devel libepoxy-devel "cmake(KF5Init)" "cmake(KF5Crash)" "cmake(KF5KIO)" "cmake(KF5Notifications)" kf5-kpackage-devel
```

#### openSUSE

```bash
sudo zypper install cmake gcc-c++ extra-cmake-modules libQt5Gui-devel libQt5DBus-devel libqt5-qttools-devel libqt5-qtx11extras-devel libQt5OpenGL-devel libQt5Network-devel libepoxy-devel kconfig-devel kconfigwidgets-devel kcrash-devel kglobalaccel-devel ki18n-devel kio-devel kservice-devel kinit-devel knotifications-devel kwindowsystem-devel kguiaddons-devel kiconthemes-devel kpackage-devel kwin5-devel xcb-util-devel xcb-util-cursor-devel xcb-util-wm-devel xcb-util-keysyms-devel
```

#### Solus

```bash
sudo eopkg install extra-cmake-modules kdecoration-devel qt5-declarative-devel qt5-x11extras-devel qt5-base-devel kcoreaddons-devel kguiaddons-devel kconfigwidgets-devel kwindowsystem-devel ki18n-devel kiconthemes-devel kcmutils-devel libxcb-devel xcb-util-devel qt5-wayland-devel kwayland-devel wayland-devel frameworkintegration-devel
```

### 构建并安装

```bash
git clone --single-branch --depth=1 https://github.com/MemoryShadow/Lightly.zh_cn.git Lightly
cd Lightly && mkdir build && cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_INSTALL_LIBDIR=lib -DBUILD_TESTING=OFF ..
make
sudo make install
```

### 卸载

在上面那里的build目录里，执行下面这句:

```bash
sudo make uninstall
```

## 致谢

Breeze 作者和 Kvantum 开发人员 Pedram Pourang。
