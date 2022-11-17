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


#### 人脸数据库
- http://www.face-rec.org/databases/
- 耶鲁大学人脸数据库（Yalefaces），http://vision.ucsd.edu/content/yale-face-database
- 扩展的耶鲁大学人脸数据库B，http://vision.ucsd.edu/content/extended-yale-face-database-b-b
- 人脸数据库（来自剑桥AT&T实验室），http://www.cl.cam.ac.uk/research/dtg/attarchive/facedatabase.html

#### OpenCV4 中的几种人脸识别算法
- 特征脸(EigenFace)
- FisherFace
- 局部二值模式直方图(Local Binary Pattern Histogram, `LBPH`)
  
其中特征脸(EigenFace)和FisherFace来自主成份分析(Principal Component Analysis, PCA)的通用算法。在OpenCV的人脸识别器中，`LBPH`的实现是唯一允许
模型样本人脸和检测到的人脸具有不同形状、不同大小的人脸识别
器。

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

