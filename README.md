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
### 场景  
#### 非等温流 
两个耦合：流动耦合与温度耦合（软件中集成）  
三个方程：
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/f7f27c12188cb5b0e02f0f7859adae4.png)</div>  
准数：判断是否为湍流 
 .<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/92736371658398a3d3a81096f123947.png)</div> 
强制对流：输远方程模型
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/5ec0db001fa2829ef2fb74a9f0d6c50.png)</div> 
#### 管道传热 
看情况可以简化为一维。  
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/41d508b33c560d9ba2c85047a3ebec0.png)</div> 
一般情况：包含三部分热阻，分别为内部膜阻，壁层热阻，外部膜阻。
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/81f18afc7a80b98f56aab4f21b92399.png)</div> 
#### 多孔介质传热  
三个控制方程：固体部分导热方程，流体部分热对流方程，局部平衡。
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/02cf2bfd742b3d6e8c9d0e464e6de38.png)</div>
局部平衡判据：Sparrow准数，Darcy准数。
流体流动方程选择
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/dee38cbf1767f15f1b8e89bffb67e24.png)</div>
#### 蒸发与冷凝
封闭区域仿真有时需要注意蒸发和冷凝带来的影响。


[^导热性]:导热系数K，稳态热传导条件下单位时间内通过单位面积（垂直于温度梯度方向）的热量。
[^质量流率]:单位时间内通过某一截面的质量。  
[^视角因子]:发射率：定义为一个物体实际辐射能力与理想黑体在相同温度下辐射能力的比例。  
视角因子：描述了从一个表面（或一个表面元素）发射的辐射中有多少能到达另一个表面（或表面元素）。

## 低频电磁场AC/DC模块
### 如何选择模块
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">模块选择参考图</p> 
### 电场分析类型
#### 静场模拟
静电，直流，静磁。（稳态电流，无放电，无感应）
#### 低频模拟
交变电流，电磁感应
#### 瞬态分析
脉冲，电机，非线性材料
### 分析依据：
#### 麦克斯韦方程组
安培定律，法拉第定律，高斯定律（电/磁），连续性方程（电荷守恒定律）
#### 边界条件
默认边界条件：零电荷，磁绝缘
静电常用边界：接地，电势，终端（可利用“电路”与外部相接），零电荷。
电流常用边界：接地，电势，终端，电绝缘。
静电其他边界条件：悬浮电位（表面电压恒定但未知，可以通过“电路”接口与外部电路相连接），表面电荷密度，薄低介电常数间隙（边界上介电常数低），介电屏蔽（边界上介电常数高）。
电流其他边界条件：悬浮电位（表面电压恒定但未知），法向电流密度（指定电流流入流出），接触阻抗（低电导率/介电常数），电屏蔽（高电导率，表面电流流动，不受外部电场影响），电接触。
### 仿真-平板电容器
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">更改箭头绘画，优化展示</p> 
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">应用全局计算，调用结果</p> 
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">连接电路</p> 
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">不同频率下的仿真结果</p> 
### 处理无限大空气域
#### 参数化几何区域尺寸，查看其结果变化趋势
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">更改几何构造</p> 
#### 应用零电荷和悬浮电位，取平均值
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">边界条件取平均值</p> 
#### 制作外层无限元域
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">无限元域</p> 
### 仿真-三接口电容器
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">无限元域</p> 
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">仿真结果</p> 
### 电路接口
#### 耦合选择（根据物理场软件辅助选择）
外部U vs. I,FEM提供电压，ODE计算电流
外部I vs. U,FEM提供电流，ODE计算电压
### 磁性材料建模
相对磁导率，BH和HB曲线
网格注意事项：线圈中由于趋肤效应的影响，边界层网格做四面体。
### 仿真-线圈磁
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">先进行线圈几何分析</p> 
.<div align=center>![加载失败](https://github.com/cmthhh/notebook_cmt/blob/main/photos/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-23%20175605.png)</div><p align="center">仿真结果</p> 


































