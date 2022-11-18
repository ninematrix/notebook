# Some Weblinks

## TO research: OwnCloud 私有云搭建

## Ubuntu 优化
- 安装 gnome tweak tool

```shell
sudo apt install gnome-tweaks
sudo apt install gnome-shell-extension-manager
```

- KDE Connect
手机与Ubuntu 通讯工具，可以遥控、发送剪贴板、文件

- Shell Extension
	- GSConnect 插件:配合KDE Connect
	- Resource Monitor:在Shell Bar中显示CPU MEM Network	


## perf 性能调优

```shell
sudo apt install linux-tools-generic linux-tools-$(uname -r)

sudo sysctl -w kernel.perf_event_paranoid=1
```
或者在/etc/sysctl.conf中增加上述配置项，永久生效






## reference
- [Logo Design Site](https://www.designevo.com/cn/apps/logo/)
- [Z-Library on Onion web](http://zlibrary24tuxziyiyfr7zd46ytefdqbqd2axkmxm4o5374ptpc52fad.onion/)
- [Linux performance](https://www.brendangregg.com/linuxperf.html)
- [Linux 内存管理](https://zhuanlan.zhihu.com/p/452427150)
