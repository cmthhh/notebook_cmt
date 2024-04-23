# notebook_cmt    

# 目录    
* [目录](#目录)  
  * [How to write ?](#写作)  
    * [文本处理](#文本处理)
    * [图片](#图片)
* [COMSOL](#COMSOL)
  * [导热模块](#导热模块)
    * [导热机制](#导热机制)
    * [广义传热方程](#广义传热方程)
    * [边界条件](#边界条件)
    * [仿真-保温瓶传热](#仿真-保温瓶传热) 
  
  ## 写作 
  ### 文本处理  
  ``高亮？``  
  **加粗？**  
  *斜体？*  
~~删除线？~~  
***斜又粗***:satisfied:  
<p align="center">居中 :flushed:</p>  

**打点**  需要空行
* 一级圆点
  * 二级圆点
    * 三级圆点 :smirk:

**表格**  需要空行

 | 写 | 表 | 格 |  
 | :--- | :---: | ---: |  
 | 靠左边 | 在中间 | 靠右边 |  
 | llllllllll | mmmmmmmmmm | rrrrrrrrrr |  
 
**选择表**  

- [x] 打勾？
- [ ] 空格？

**脚注**  
脚注[^脚注]

### 图片  
  .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/hahaha.jpg "hahaha")</div>  

[^脚注]:写脚注

# COMSOL
## 导热模块  
### 导热机制
#### 热传导  
特征：导热性K[^导热性]，温差
#### 热对流  
特征：热容，质量流率[^质量流率]，温度
#### 辐射  
特征：是否透明，发射率，视角因子[^视角因子]，表面/环境温度  
### 广义传热方程  
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/7968111965b00c3f368ca332ea05261.jpg)</div>
输入：材料属性，速度场，热源 + 初始值，边界条件
### 边界条件
#### 狄氏边界条件
狄氏边界条件规定了函数在边界上的固定值。在热传递问题中，可能会指定固体边界上的温度；在电磁问题中，可能会指定导体表面上的电势。
#### 纽曼边界条件
纽曼边界条件规定了函数的导数在边界上的值，这通常对应于物理问题中的通量、力或其他导出量。在热传递问题中，纽曼边界条件可能规定边界上的热通量，而在流体力学问题中，它可能规定表面上的应力或速度的正常分量。
#### 混合边界条件
这种类型的边界条件中，函数及其导数的某种线性组合在边界上是已知的。
* 牛顿冷却定律
牛顿冷却定律实际上是一个特例的混合界条件。在热传递问题中，如果我们将牛顿冷却定律作为边界条件应用到热流方程中，该边界条件可以写成：
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/bfc684d352c96cef9891a3efade475a.png)</div>  h为对流换热系数，考虑对流内/外，自然/强制.
### 仿真-保温瓶传热 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">构造几何模型，考虑到保温瓶对称性，做二维仿真就可以。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20180618.png)</div><p align="center">选择边界，定义显式的边界组，便于后面设定参数。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20182658.png)</div><p align="center">给个各模块添加材质。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20183534.png)</div><p align="center">设置全局参数，改动方便。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20183911.png)</div><p align="center">设定初始值。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20184219.png)</div><p align="center">由于金属片比较薄，直接设定热薄近似，算的快。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20184941.png)</div><p align="center">不同表面设定不同的热通量，这里的盖子上方是自然对流。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-24%20002915.png)</div><p align="center">生成网格。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20213749.png)</div><p align="center">设定仿真时间和步长。</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20213842.png)</div>
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20214721.png)</div><p align="center">仿真结果</p> 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20215724.png)</div><p align="center">应用APP开发器功能，可以直接改参数。</p> 



[^导热性]:导热系数K，稳态热传导条件下单位时间内通过单位面积（垂直于温度梯度方向）的热量。
[^质量流率]:单位时间内通过某一截面的质量。  
[^视角因子]:发射率：定义为一个物体实际辐射能力与理想黑体在相同温度下辐射能力的比例。  
视角因子：描述了从一个表面（或一个表面元素）发射的辐射中有多少能到达另一个表面（或表面元素）。
