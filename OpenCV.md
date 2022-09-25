# OpenCV 与计算机视觉


## 摄像头模型与增强现实

### 摄像头和镜头参数

- OpenCV使和摄像头矩阵(Camera Matrix)表示摄像头和镜头基本参数

$$
\begin{bmatrix}
f & 0 & c_x \\
0 & f & c_y \\
0 & 0 & 1 \\
\end{bmatrix}
$$

> $(c_x,c_y)$为图像传感器的中心点
- 如果传感器的宽度与高度分别为$w,h$
$$
c_x = w/2 \\
c_y = h/2 
$$
- 如果知道对角线视角$\theta$
  $$
  f = \frac{\sqrt{w^2 + h^2}}{2(\tan \frac{\theta}{2})}
  $$

- 如果不知道对角线视角，而是知道水平视角$\phi$和垂直视角$\psi$
  $$
  f = \frac{\sqrt{w^2+h^2}}{2\sqrt{(\tan(\frac{\phi}{2}))^2 + (\tan(\frac{\psi}{2}))^2}}
  $$

  