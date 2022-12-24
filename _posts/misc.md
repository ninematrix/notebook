 # Something

## Convert image to some size

Use `convert` command in ImageMagic
```shell
#!/bin/bash
for size in 16 32 64 128 256 512 1024; do
    convert icon.png -resize ${size}x${size} app_icon_$size.png
done
# from ImageMagick 
#/bin/rm 16.png 32.png 48.png 128.png 256.png

```

## TexLive ISO mount

```shell
mount -t iso9660 -o ro,loop,noauto ./texlive.iso /mnt

```


## Safenet eToken 5110

```
echo "deb http://security.ubuntu.com/ubuntu focal-security main" | sudo tee /etc/apt/sources.list.d/focal-security.list

sudo apt-get update
sudo apt-get install libssl1.1

//to remove 
sudo rm /etc/apt/sources.list.d/focal-security.list

```

初始化token SO
```
pkcs11-tool --module /usr/lib/libeToken.so --init-token --label nmtoken
```

pin:102000

修改pin
```
pkcs11-tool --module /usr/lib/libeToken.so --change-pin
```

创建RSA公钥与私钥
```
pkcs11-tool --module /usr/lib/libeToken.so --login --keypairgen --key-type RSA:2048 --id 1 --label "ninematrix@gmail.com"
```

列出token中的对象
```
pkcs11-tool --module /usr/lib/libeToken.so --login --list-objects
```

创建自签名证书
```
OpenSSL>engine dynamic -pre SO_PATH:/usr/lib/engines/engine_pkcs11.so -pre ID:pkcs11 -pre LIST_ADD:1 -pre LOAD -pre MODULE_PATH:libeToken.so

```

使用token中的证书ssh
```
ssh -I /usr/lib/libeToken.so smartcard@server
```

## HID - Human Interface Device 人体工学设备
> 人体学接口设备 (HID) 是一个设备类定义，用于将 PS/2 样式的连接器替换为支持 HID 设备（例如键盘、鼠标、游戏控制器等）的通用 USB 驱动程序。 在 HID 之前，设备只能对鼠标和键盘使用严格定义的协议。 硬件创新要求使用现有协议重载数据，或使用其自己的专用驱动程序创建非标准硬件。 HID 为这些“启动模式”设备提供了支持，同时通过可扩展、标准化且易于编程的接口添加对硬件创新的支持。

> 目前，HID 设备包括各种设备，例如字母数字显示器、条码读取器、扬声器/耳机上的音量控制、辅助显示器、传感器等。 许多硬件供应商还对其专用设备使用 HID。

> HID 一开始为 USB，但设计为与总线无关。 它为低延迟、低带宽设备而设计，但可以灵活地指定基础传输中的速率。 1996 年，基于 USB 的 HID 的规范被 USB-IF 批准。不久之后，对其他传输的支持又获得批准。 有关当前支持的传输的详细信息，可参阅 Windows 中支持的 HID 传输。 此外，还允许通过自定义传输驱动程序进行特定于供应商的第三方传输。

- [微软 - HID简介](https://learn.microsoft.com/zh-cn/windows-hardware/drivers/hid/)

## REF
- [Using tokens in Ubuntu with PGP](https://craftware.xyz/securitybricks/2017/07/17/using-tokens-in-Ubuntu-with-pgp.html)

