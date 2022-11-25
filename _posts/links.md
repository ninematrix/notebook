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



## linux 审计
- [Linux 审计:美国国防部常见的审计要求](https://blog.51cto.com/u_7492110/1753095)
- [深入linux审计日志](https://nettingsisyphus.tech/2020/11/17/linux-audit-guide/)
- [Linux审计系统](https://zhuanlan.zhihu.com/p/337289840)
- [Linux审计系统使用详解](https://zgao.top/linux%E5%AE%A1%E8%AE%A1%E5%B7%A5%E5%85%B7auditd%E4%BD%BF%E7%94%A8%E8%AF%A6%E8%A7%A3/)
- [Ubuntu三级等保检查命令](https://www.cnblogs.com/aqicheng/p/14668187.html)
- [SUSE - 了解Linux审计](https://documentation.suse.com/zh-cn/sled/15-SP3/html/SLED-all/cha-audit-comp.html)


## Unix Bench 跑分工具
```shell
wget https://s3.amazonaws.com/cloudbench/software/UnixBench5.1.3.tgz
tar zxf UninxBench5.1.3.tgz
cd UnixBench
make all
,/Run
```

## reference
- [Logo Design Site](https://www.designevo.com/cn/apps/logo/)
- [Z-Library on Onion web](http://zlibrary24tuxziyiyfr7zd46ytefdqbqd2axkmxm4o5374ptpc52fad.onion/)
- [Linux performance](https://www.brendangregg.com/linuxperf.html)
- [Linux 内存管理](https://zhuanlan.zhihu.com/p/452427150)
- [Git Pro](https://git-scm.com/book/zh/v2/)
- [RustDesk源码阅读](https://cloud.tencent.com/developer/article/1897847)

