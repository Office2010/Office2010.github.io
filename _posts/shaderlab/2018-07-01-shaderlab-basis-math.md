---
layout: article
title:  "Shaderlab-Basis(02)-数学基础"
categories: shaderlab
image:
    teaser: /shaderlab/ShaderlabBase.jpg
---
> 简介：shaderlab 基础篇

# 向量
---
1. 矢量和标量的乘/除法<br>
![shader_math_01](/images/shaderlab/base/shader_math_01.jpg)
2. 矢量的加法和减法<br>
![shader_math_02](/images/shaderlab/base/shader_math_02.jpg)
3. 矢量的模<br>
![shader_math_03](/images/shaderlab/base/shader_math_03.jpg)
4. 单位向量，单位向量也被称为归一化的向量<br>
![shader_math_04](/images/shaderlab/base/shader_math_04.jpg)
5. 矢量间的乘法<br>
<br>(1).点积 dot ， 也被称为内积，几何意义是投影，如下图<br>
![shader_math_05](/images/shaderlab/base/shader_math_05.jpg)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
①. 公式一：a·b = (a<sub>x</sub> ,a<sub>y</sub> ,a<sub>z</sub>) ·(b<sub>x</sub> ,b<sub>y</sub> ,b<sub>z</sub>) = a<sub>x</sub> b<sub>x</sub> + a<sub>y</sub> b<sub>y</sub> + a<sub>z</sub> b<sub>z</sub>
<br>投影值（点积）的正负号与俩向量的方向有关，如图：<br>
![shader_math_06](/images/shaderlab/base/shader_math_06.jpg)