#### 简介

本文章主要由两部分组成
1. 颜色的叠加混合
2. 褶皱



本文章用于在Unity中复刻一个Blender项目
原项目地址
b站：[「Blender教程」实用型丝袜制作指南 | 白 丝 编_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1hsgazQEdt/?spm_id_from=333.337.search-card.all.click&vd_source=f57b2f1fa8e9a2a8e8a12a00596a3d8d)
github：[Releases · zxsama/Stocking-Project](https://github.com/zxsama/Stocking-Project/releases)

#### 目标效果
**BSDF**
![[Stocking_BSDF.png]]
**最终效果**
![[Stocking_Final.png]]
#### 原项目解析
##### 贴图
1. 拉伸贴图 用于还原腿部不同区域丝袜的拉伸情况
![[Stocking_Strenth.png]]
2. 深色贴图 用于实现一些丝袜会在指尖或者大腿处做加厚处理
![[Stocking_Darken.png]]
3. 破洞贴图 实现丝袜上的破洞效果
![[Stocking_TearMask.png]]
##### 详细计算过程
1.菲涅尔项
**公式：**
ramp(1-NdotV)
**节点：**
![[Stocking_Fresnel1.png]]
**效果：**
![[Stocking_Fresnel.png]]
**编制纹理**
通过uv程序化生成类似网格的纹理
**节点：**
![[Stocking_WeaveTexture1.png]]
**效果：**
![[Stocking_WeaveTexture.png]]
**合并贴图效果**
![[Stocking_Final1.png]]
**肤色**
贴图颜色
![[Stocking_Skin2.png]]
![[Stocking_Skin1.png]]
过BSDF
![[Stocking_Skin.png]]
![[Stocking_Skin3.png]]
**丝袜颜色**
![[Stocking_StockingColor.png]]
![[Stocking_StockingColor1.png]]
**插值**
![[Stocking_Frac.png]]
**最终效果**
![[Stocking_Final2.png]]

为了能够实现在人物运动中丝袜出现的褶皱感，参考动画混合的NormalWrinkle方式

参考教程：
https://www.youtube.com/watch?v=4roqTCOj_a4













#### Unity复刻







