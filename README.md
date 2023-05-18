# Ti
采集Ti毫米波 128激光雷达adc与点云，海康视频的采集软件
文档内容：介绍软件环境搭建，方便软件在其它的系统进行编译
第一步：安装qt (如果安装则省略)
    `sudo apt-get install qt5-default qtcreator `
第二步：安装opencv （如果安装则省略）
    （1）sudo apt-get install libopencv-dev（编译好的二进制库和头文件） 
    （2）如果已经安装，使用如下命名查找相关库路径:
        `sudo find / -name libcudart.so.11.0`
        使用如下命令查找opencv的头文件:
        `sudo find / -name opencv.hpp`
第三步：安装海康工业相机软件，里面含有sdk相关的动态库
    见附件：MVS-2.1.1_x86_64_20220511.deb
    安装命令：`sudo dpkg -i MVS-2.1.1_x86_64_20220511.deb`
第四步：更改工程中引用opencv 的头文件路经与opencv库的相关路径
    详见CMakeLists.txt中的注释
第五步：编译radar_lidar工程步骤如下：
    `mkdir build`
    `cd build`
    `cmake ..`
    `make -j4`
    执行成功后即可生成可执行文件，在build中单击radar_lidar即可
