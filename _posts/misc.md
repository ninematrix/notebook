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
