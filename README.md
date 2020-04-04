 ```
  _______                     ________        __
 |       |.-----.-----.-----.|  |  |  |.----.|  |_
 |   -   ||  _  |  -__|     ||  |  |  ||   _||   _|
 |_______||   __|_____|__|__||________||__|  |____|
          |__| W I R E L E S S   F R E E D O M
 -----------------------------------------------------
 
 ```
# OpenWrt Stable 1907 with lean's package

![OpenWrt-1907 x86_64](https://github.com/iyuangang/openwrt/workflows/OpenWrt-1907%20x86_64/badge.svg) ![OpenWrt-1907 RaspberryPi3B+](https://github.com/iyuangang/openwrt/workflows/OpenWrt-1907%20RaspberryPi3B+/badge.svg)

This is the stable buildsystem for the `OpenWrt Linux distribution`.

这是 `OpenWrt Linux 发行版` 稳定版本编译系统。

All released version of my project is used for more than a week, and released after the test is stable.

本项目版本均为使用一周以上，测试稳定后发布。

This project can use `Github Actions` to achieve automatic compilation. Copy the `openwrt-ci-v2.yml` in the directory `.github /workflows/` and rename then modify the content to your own configuration. Note: In order to successfully synchronize the changes after the fork, please do not make any modifications to the original `openwrt-ci-v2.yml`, otherwise it will cause errors in the synchronization upstream.

本项目可利用 `Github Actions` 实现自动编译。拷贝目录 `.github/workflows/` 下的 `openwrt-ci-v2.yml` 重命名并修改内容为自己的配置即可。注意事项：为了顺利同步Fork 后的更改内容，请不要对原版 `openwrt-ci-v2.yml` 做任何修改，否则会导致同步上游出错。

To build your own firmware you need a `Linux`, `BSD` or `MacOS` system (case sensitive filesystem required). `Cygwin` and `Windows linux subsystem` are unsupported because of the lack of a case sensitive file system.

要构建属于您自己的固件，您需要一个 `Linux` ，`BSD` 或 `MacOS` 系统（需要区分大小写的文件系统）。 由于缺少区分大小写的文件系统，因此不支持 `Cygwin` 和 `Windows linux subsystem`。

You need `gcc`, `binutils`, `bzip2`, `flex`, `python`, `perl`, `make`, `find`, `grep`, `diff`, `unzip`, `gawk`, `getopt`, `subversion`, `libz-dev` and `libc` headers installed.

您需要安装 `gcc`, `binutils`, `bzip2`，`flex`, `python`, `perl`, `make`, `find`, `grep`, `diff`, `unzip`, `gawk`, `getopt`, `subversion`, `libz-dev`, `libc`.

1. Run `./scripts/feeds update -a` to obtain all the latest package definitions defined in `feeds.conf / feeds.conf.default`

   运行`./scripts/feeds update -a`获取`feeds.conf / feeds.conf.default`中定义的所有最新软件包定义。

2. Run `./scripts/feeds install -a` to install symlinks for all obtained packages into `package/feeds/`

   运行`./scripts/feeds install -a`将所有获得的软件包的符号链接安装到`package/feeds/`中。

3. Run `make menuconfig` to select your preferred configuration for the toolchain, target system & firmware packages.

   运行 `make menuconfig` 为工具链，目标系统和固件包选择首选配置。

4. Run `make download -j8 && make -j8 || make -j1 V=s` to build your firmware. This will download all sources, build the cross-compile toolchain and then cross-compile the Linux kernel & all chosen applications for your target system.

   运行`make download -j8 && make -j8 || make -j1 V=s`来构建固件。 这将下载所有源代码，构建交叉编译工具链，然后交叉编译目标系统的Linux内核和所有选定的应用程序。

Sunshine!
	Your [OpenWrt](http://www.openwrt.org) Community
	
Thanks to 
	[Lean's OpenWrt source ](https://github.com/coolsnowwolf/lede)
