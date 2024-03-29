![face](./pictures/face.png)

## 目录
- [一、课设目标](#一课设目标) 
- [二、课设要求](#二课设要求)
- [三、课设安排](#三课设安排)
- [四、课设内容](#四课设内容)
- [五、参考资料](#五参考资料)
- [六、问题讨论](#六问题讨论)

## 一、课设目标
遥感图像处理是遥感科学与技术专业的专业基础课，其核心内容是若干遥感图像处理算法和原理。本课程设计的主要目标培养学生既懂遥感图像处理算法理论，也懂遥感图像处理算法实现的专业素养和动手能力的专业人才，其具体目标为：
1. 强化学生对遥感图像处理算法原理的**理解**
2. 培养学生解决遥感应用问题的**设计能力**
3. 培养学生遥感图像处理算法的**编程能力**
4. 培养学生**交流沟通和书面表达能力**

[**返回目录**](#目录)
---

## 二、课设要求
### 1. 基本要求
1. 独立完成课设的内容，意味着你不能直接使用第三方的源码；
2. 程序语言原则上使用C/C++，若你有更为擅长的语言，也可以使用C#、Python、IDL、Matlab等；
3. 无论你使用哪种程序语言，都需要讲核心算法从底层实现起，这意味着你不得直接调用第三方库（如ENVI-IDL、OpenCV、Egien、Matlab等）已经封装的函数；
4. 课设的每一个算法，要有算法基本原理的讲解、算法实现的流程图、程序接口设计说明、源代码、算法处理的测试结果（与主流遥感图像处理软件结果对比）。
5. 编码需符合编码规范。工程文件的命名、组织、函数的命名、变量的命名必须为英文，简洁而明晰，并添加适当注释以确保程序的可读性。
6. 课程设计结束后**1 周内**，依照[**课设报告模板**](./contents/%E8%AF%BE%E8%AE%BE%E6%8A%A5%E5%91%8A.docx)撰写课设报告。
7. 课设报告中尽量避免引用大段的代码，保留界面截图和运行结果即可。
8. 提交纸质课设报告一份，课设报告和代码工程的电子档各一份，以班级为单位刻盘上交。

### 2.课程考核
1. 课设成绩由4部分如下表：

|  序号  | 必做题  | 选做题（N选2） | 附加题（N选1） |  报告  |
| :--: | :--: | :------: | :------: | :--: |
| 分值比重 | 50%  |   20%    |   30%    | 20%  |
|  及格  |  √   |    ×     |    ×     |  √   |
|  中等  |  √   |    √     |    ×     |  √   |
|  良好  |  √   |    ×     |   √--    |  √   |
|  优秀  |  √   |    ×     |    √     |  √   |

2. 课设报告必须要封面、格式统一
3. 无论源代码或报告内容出现抄袭，一律零分处理

[**返回目录**](#目录)
---

## 三、课设安排
![TimeTable](./pictures/TimeTable.png)

[**返回目录**](#目录)
---

## 四、课设内容
本次课程的重点是图像处理算法，因此对GUI不做过多的要求，即控制台程序和GUI界面程序均可。但课设的所有算法，要能够组织到一起，需要在一个可执行程序下调用。当然我们更希望看到美观的GUI界面程序。课设内容包括以下功能：
### 0. 准备工作
#### [0.开发环境配置](./contents/D0_EnvSetup.md)
配置VS2017、Qt5、GDAL的文档。

#### [1.程序框架构建](./contents/D1_RSIP_Frame.md)
掌握Qt、MFC或其他界面框架，构建基本的系统原型，包括视图、菜单、工具栏等界面要素。

### 1. 必做题 - 50%
#### 图像增强-Enhancemen
- 功能1：**线性拉伸**
- 描述：**输入拉伸的范围，将图像DN值做线性拉伸**
- 函数名：**LinearStretch**

---

- 功能2：**直方图匹配（直方图均衡化）**
- 描述：**输入一幅图像，输入参考图像或参考的直方图，将输入图像的直方图匹配到另一幅图像**
- 函数名：**HistogramMatch**
- 备注：**函数可能需要重载，足以实现直方图均衡化**


#### 卷积滤波-Filter
- 功能：空域滤波
- 描述：输入图像和卷积核，输出结果图像
- 函数名：ConvFilter

#### PCA Transformation
- 功能：主成分变换
- 描述：输入图像、输出PCA变化结果及中间矩阵
- 函数名：Pca
- 备注：最好能实现逆PCA变换

---

#### 几何校正
- 功能1： 重采样（最近邻，双线性内插）
- 描述：输入图像和重采样类型，输出重采样结果图像
- 函数名：Resample

---

- 功能2： 仿射变换
- 描述： 输入旋转角度、缩放因子，生成变换后的图像
- 函数名：AffineTrans

---

- 功能3： 多项式校正
- 描述：按多项式次数几何校正，至少实现3次及以内的多项式校正
- 函数名：PolyTrans

#### Classification（2选1）
- ISODATA
- SVM

---

[**返回目录**](#目录)
---

### 2. 选做题 - 20%（选做其中2个功能）
- 功能1：边缘提取
- 描述：输入图像，实现一种差分方式的边缘提取算法，输出边缘二值图
- 函数名：Edge

---

- 功能2：特征点提取
- 描述： 输入图像，实现一种特征点（SIFT/SOBEL/Forest）的提取算法
- 函数名：FeatureExtraction

---

- 功能3：数学形态学
- 描述：输入二值图像，完成开运算、闭运算、膨胀、腐蚀的功能
- 函数名：MorphOpen、MorphClose、MorphDilate、MorphErosion

---

- 功能4：决策树分类
- 描述：实现决策树分类算法，输入图像，输出分类结果

---

- 功能5： 正射校正
- 描述：输入DEM和校正模型参数，完成正射校正
- 函数名：Ortho

- 功能6：傅里叶变换
- 描述：输入图像，输出频域图像，可以参考Eigen或fftw的内容
- 函数名：Fft
---

[**返回目录**](#目录)
---

### 3. 附加题 - 30% Challenges（选做1个即可）
#### 1. GeoCorrect
- 需求
  遥感图像自动配准程序。输入两幅图像，提取特征点，完成特征点的匹配，计算校正参数，完成图像重采样，实现几何校正。
- 功能分析
  -  特征点提取：SIFT 或 其他算子
  -  特征点匹配：RANSAC匹配方法
  -  几何校正参数计算：参数计算
  -  图像重采样：几何校正

---

#### 2. 快速大气校正
- 需求
  输入卫星成像时刻、成像姿态、轨道参数、定标系数和程辐射等，带入大气辐射传输的方程，计算表观反射率。
- 功能分析
  - DN转换为辐射亮度
  - 程辐射计算
  - 大气校正

---

#### 3. 温度反演
- 需求
  输入热红外图像，完成一系列温度反演算法，输出温度图。
- 功能分析
  - 地表比辐射率计算
  - 温度反演算法

---

#### 4. 土地利用分类
- 需求
  输入多光谱图像，完成土地利用分类功能，包括：监督分类、分类后处理、分类精度评价。
- 功能分析
  - ROI选取
  - ROI评价
  - 分类算法
  - 分类后处理
  - 分类精度评价

---

[**返回目录**](#目录)
---

## 五、参考资料
### 1. 开源库
- [Qt入门](https://blog.csdn.net/Louis_815/article/details/54286544)
- [GDAL](www.gdal.org)
- [OpenCV](www.opencv.org)
- [CImg](www.cimg.eu)
- [CxImage](https://www.codeproject.com/Articles/1300/CxImage)
- [Eigen](<http://eigen.tuxfamily.org/index.php?title=Main_Page>)
- Eigen的配置和安装，请参考<<https://blog.csdn.net/abcjennifer/article/details/7781936>>。
- Eigen的使用，可以参考<<https://zhuanlan.zhihu.com/p/31111908>>。

---

### 2.功能参考
- [遥感图像数据I/O](./contents/D2_RasterIO.md)
  要求实现常用遥感图像数据（GeoTiff，IMG，Pix，jpeg，bmp、Envi）的读、写操作，读取并显示遥感图像的基本信息及统计信息。

- [遥感图像的显示](./contents/D3_ImageDisplay.md)
  要求实现遥感图像的灰度显示、彩色合成显示、具备放大、缩小、屏幕适应的显示方式，具备线性拉伸、均衡化等增强显示方式。

- [遥感影像预处理](./contents/D4_Preprocess.md)
  要求实现图像滤波、PCA分析、影像融合等功能。

- [遥感影像几何校正](./contents/D5_Geocorrection.md)
  实现但不限于多项式校正的几何校正方法，包括：控制点选取（读取）、几何校正模型计算、重采样内插等功能。

- [遥感影像分类](./contents/D6_Classification.md)
  实现监督分类和非监督分类的算法至少各一种。

- [遥感图像处理过程](https://blog.csdn.net/liminlu0314/article/details/8757262)

---

### 3. 程序架构示意图
![pic](./pictures/workflow.png)

## 六、问题讨论
如果你有关于本门课程设计的任何疑问、建议、指正，欢迎在[讨论专区](https://github.com/Wanghp119/RSIP/issues)中留言，我们将第一时间回复。

[**返回目录**](#目录)
---
