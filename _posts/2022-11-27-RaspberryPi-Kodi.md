# Install Kodi in Raspberry Pi 4

##
```shell
ssh-keygen -f ~/.ssh/known_hosts -R "192.168.50.231"
```
更新清华的源
- 参考[Raspbian 镜像使用帮助](https://mirrors.tuna.tsinghua.edu.cn/help/raspbian/)
`uname -m`确定系统架构 `aarch64` 

打开`/etc/apt/sources.list` 文件,替代源为

```
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-updates main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-backports main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-backports main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian-security bullseye-security main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian-security bullseye-security main contrib non-free

# 对于两个架构，编辑 `/etc/apt/sources.list.d/raspi.list` 文件，删除原文件所有内容，用以下内容取代：
deb https://mirrors.tuna.tsinghua.edu.cn/raspberrypi/ bullseye main

```

## 安装Kodi

```
sudo apt install kodi kodi-peripheral-joystick kodi-pvr-iptvsimple kodi-inputstream-adaptive kodi-inputstream-rtmp
```

安装Kodi需要的环境
```
sudo apt install build-essential python3-pip python3-dev libffi-dev libssl-dev libnss3

sudo pip install pycryptodomex win_inet_pton PySocks
```

### Run at start
`raspi-config` 后选择Login to console with user ..
执行以下后
```
crontab -e
```
加入
```
@reboot kodi --standalone
```

## 资源库CastagnaIT
需要下载CastagnaIT资源库。这个资源库用来安装Netflix插件的Kodi，并让它自动更新。可以通过运行以下命令，直接从项目的GitHub上下载最新版本的仓库。

https://github.com/castagnait

## Clash

```
[Unit]
Description=Clash service
After=network.target

[Service]
Type=simple
User=pi
ExecStart=/usr/bin/clash
Restart=on-failure
RestartPreventExitStatus=23

[Install]
WantedBy=multi-user.target

```



## PIN
`4158`


## 问题
该问题在当前版本上还是存在 [看这里](https://discourse.osmc.tv/t/netflix-error-typeerror-init-missing-2-required-keyword-only-arguments-request-and-response/93817) [以及这里](https://github.com/CastagnaIT/plugin.video.netflix/issues/1432)
> Netflix Error “TypeError:__init__() missing 2 required keyword-only arguments: ‘request’ and ‘response’”



## 参考

- [在 Raspberry Pi 上运行 Clash 作为透明代理](https://cherysunzhang.com/2020/05/deploy-clash-as-transparent-proxy-on-raspberry-pi/)
> 为 Raspberry Pi 启用 IP 转发
- [Kodi Wiki](https://kodi.wiki/view/Main_Page)
- [Kodi Netflix 插件:Login with Authentication key](https://github.com/CastagnaIT/plugin.video.netflix/wiki/Login-with-Authentication-key)

