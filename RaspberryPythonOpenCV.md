# Raspberry Pi , Python and OpenCV

## Raspberry Pi 操作系统安装
不再支持NOOBS,新的安装工具为`Raspberry Pi Imager`
Ubuntu下可以下载deb包后进行安装，安装命令为
```bash
sudo dpkg -i imager_1.x.x_amd64.deb
```

Raspbian下的安装命令为
```bash
sudo apt install rpi-imager
```

## Python 环境与Geany编辑器
内置轻量文本编辑器为Ｇeany,

## OpenCV 与　计算机视觉

### HSV 颜色空间
- H:Hue 色相
- S:Saturation饱和度
- V:Value亮度
  
### 人脸检测方法
- 肤色检测法
- 直方图检测法(HOG)
- 哈尔特征检测(HAAR)


### 控制方法
- 比例调节
- 微分调节
- 积分调节

上述三种调节方式组成ＰＩＤ控制器，可以作为`平衡车`、`无人机`等系统的核心控制算法。

### 机器学习分类
- 监督学习(Supervised Learning)
- 无监督学习(Unsupervised Learning)
- 半监督学习(Semi-Supervised Learning)
- 强化学习(Reinforcement Learning)