# SLAM_Lib

*A collection of SLAM materials, which are all extracted online from various sources.*

## SLAM介绍

1. [一文带你读懂SLAM](https://mp.weixin.qq.com/s/k3BAnvt1UBwpgg-qNNv8pg)
2. 中文SLAM索引 [SLAMCN](http://www.slamcn.org/index.php)
3. Source Code [openslam](http://openslam.org)
4. [学习SLAM需要哪些预备知识？](https://www.zhihu.com/question/35186064)
5. [2017年10月开源SLAM汇总](https://www.cnblogs.com/Jessica-jie/p/7719359.html)

## Paper
1. [跟踪SLAM前沿动态](https://github.com/YiChenCityU/Recent_SLAM_Research), 精选paper包括纯视觉SLAM，三维重建，基础数学工具，导航路径规划，深度学习SLAM，激光与视觉融合等类别。
2. TBD


## Course & Book
1. 高翔 [视觉SLAM14讲](https://github.com/gaoxiang12/slambook2)，[视频教程](https://www.bilibili.com/video/av59593514/)on Bilibili.


## 关于SLAM（状态最优估计）
1. [State Estimation for Robotics](http://asrl.utias.utoronto.ca/~tdb/bib/barfoot_ser17.pdf), SLAM入门教材推荐，对深入理解SLAM实质非常有帮助
2. [Course on SLAM](https://raw.githubusercontent.com/joansola/slamtb/graph/courseSLAM.pdf)，作者Joan Sola关于Graph-SLAM的教程，包含位姿变换、传感器模型、图优化以及SLAM中的稀疏性求解。还有 [SLAM TOOLBOX FOR MATLAB](http://www.iri.upc.edu/people/jsola/JoanSola/eng/toolbox.html)

## Blog & Zhihu

1. [slamcode的博客](https://blog.csdn.net/learnmoreonce)
2. 黄百川 [知乎专栏](https://zhuanlan.zhihu.com/c_1007577974610210816)
3. 刘富强 [博客](https://www.cnblogs.com/liufuqiang/)
4. 任乾知乎专栏[SLAM论文和源码解读](https://zhuanlan.zhihu.com/p/83775731)
5. 紫薯萝卜[VIO/VSLAM理论与实战](https://zhuanlan.zhihu.com/c_1121353757664964608)

## Open Source Code

### Laser SLAM
1. 谷歌slam地图库 [cartographer的源码注释](https://github.com/slam-code/cartographer) ，[关于cartographer的源码分析](https://github.com/slam-code/SLAM/tree/master/9-cartographer-%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90)

2. [BLAM](https://github.com/erik-nelson/blam), B(erkeley) L(ocalization) A(nd) M(apping). [安装使用教程](https://blog.csdn.net/xmy306538517/article/details/81122663) on CSDN.  程序介绍见 
[开源激光SLAM项目BLAM-1](https://blog.csdn.net/Adam_996/article/details/81303505) .[开源激光SLAM项目BLAM-2](https://blog.csdn.net/Adam_996/article/details/82256435)

3. LOAM-纯激光，匀速运动假设，无回环。
4. V-LOAM-视觉激光融合、漂移匀速假设，无回环。
5. VELO-视觉激光融合，无运动畸变假设，有回环


### Visual SLAM

 1. [**ORB_SLAM**](https://github.com/Jinqiang/ORB_SLAM2): 
 ORB_SLAM的核心是使用ORB作为vSLAM的核心特征，是一个完整的SLAM系统，包含了视觉里程计、跟踪、闭环检测，是一种完全基于稀疏特征点的单目SLAM系统。同时也有单目、双目和RGBD相机的接口。ORB特征实际上是将FAST特征的检测方法和BRIEF特征描述子的结合起来的，并在他们原来的基础上做了改进和优化，在效果和速度上都有很大的提升。上面的地址是我们的双目产品接入了ORB_SLAM后的一个历程，ORB_SLAM并没有加入IMU的计算。

2. [**VINS-Mono**](https://github.com/HKUST-Aerial-Robotics/VINS-Mono)和 [**VINS-Mobile**](https://github.com/HKUST-Aerial-Robotics/VINS-Mobile)是香港科技大学的沈劭劼老师团队开源的单目视觉惯导SLAM方案，也是非常经典的一个单目VIO的项目。对整体算力的要求不高，精度也不错，尤其是VINS-Mobile可以在iOS系统运行。 [**VINS-Fusion**](https://github.com/HKUST-Aerial-Robotics/VINS-Fusion)是VINS-Mono的一个扩展，它支持多传感器的整合，包括单目+IMU、双目+IMU甚至纯双目，同时也提供了增加GPS的版本。

3. [**OKVIS**](https://github.com/ethz-asl/okvis): Open Keyframe-based Visual-Inertial SLAM.
OKVIS是苏黎世联邦理工学院发布的一个双目VIO项目，这也是一个非常经典的双目VIO，但是它只输出六自由度的位姿，并没有回环检测和地图，因此严格意义上说并不是一个完整的SLAM，虽然它精度不错，但是如果长时间静止会出现位姿飘走的情况，这也是该项目里的一个问题。OKVIS的代码结构框架是非常清晰的，但只限于定位功能这一部分，也包含了紧耦合和多传感器融合，代码也是非常推荐大家去学习。


4. [**maplab**](https://github.com/ethz-asl/maplab):  maplab是苏黎世理工大学继OKVIS之后推出的另一个vSLAM框架，它包含了两部分，一部分是ROVIO，另一部分是SLAM离线处理的console.

5. [**MSCKF**](https://github.com/leokoppel/msckf): MSCKF是一个经典的基于滤波理论优化的vSLAM，它的优点是对算力要求不高，而且精度也不错。

6. [**Open_VINS**](https://github.com/rpng/open_vins): 是Huang Guoquan老师团队在2019年8月份开源的一套基于MSCKF的VINS算法，黄老师曾是Tango项目的核心成员，在MSCKF这块非常的权威。
