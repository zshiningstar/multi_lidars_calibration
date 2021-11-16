## 多激光雷达外参自动标定（ROS）

> 使⽤多激光雷达进⾏环境感知的前提是对各雷达的外参进⾏精准的标定，本代码介绍⼀种基于NDT算法的⾃动多激光雷达标定技术
> 传感器外参标定本质上是获得两个传感器的位移量（x,y,z）和旋转量（roll,pitch,yaw），三维空间中可以⽤⼀个**⻬次变换矩阵**（Homogeneous transformation matrix）来描述这样的变换关系，在三维数据处理领域，点云配准（Point Cloud Registration）就是⽤于处理两个点云间位姿匹配问题的⼀类x,y,z,roll,pitch,yaw⽅法，其中NDT(Normal Distribution Transform，正态分布变换)和ICP(Iterative Closest Point,迭代最近点算法)是其中的代表

### 0 参考:https://www.bilibili.com/read/cv10769496

### 1 NDT算法简介

### 2 标定实例
* 选取其中⼀个Lidar作为主要的坐标系（TF中的parent frame），建⽴起其他lidar到它的TF变换关系，就完成了多个激光雷达的外参标定。本实例选取**左雷达**为只要坐标系
* ⻬次变换矩阵 R T ,R是3×3矩阵,T是3行1列,一起构建成 4×4矩阵
              0 1




