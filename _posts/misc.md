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


## REF
- [Using tokens in Ubuntu with PGP](https://craftware.xyz/securitybricks/2017/07/17/using-tokens-in-Ubuntu-with-pgp.html)
