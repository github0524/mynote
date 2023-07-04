## aiq、tool-server、tuner

aiq 需要自己编译

tool-server 链接tuner和aiq

tuner x86上使用 

## VI结构

![image-20230629152719695](image/RKISP.assets/image-20230629152719695-1688023892530-4.png)

## 运行参数

-s  /dev/video8


​	

-i 指定iq文件的读取路径

![image-20230628110647824](image/RKISP.assets/image-20230628110647824-1688023907978-7.png)



## 在线抓取YUV图

板端，需要设置 -s /dev/video8

下图中可设置

文件名

抓取的帧数

抓取YUV

![image-20230627182451303](image/RKISP.assets/image-20230627182451303.png)

选择看见的帧

第一帧都是比较模糊的

![image-20230627182835317](image/RKISP.assets/image-20230627182835317.png)



## 编译rkaiq

camera_engine_rkaiq 

cd /build/linux

./envsetup 30 //rk3588是isp3.0

//修改下面这个环境变量的路径

export AIQ_BUILD_HOST_DIR=/home/songchuanlong/svn/AIOT/buildroot/output/rockchip_rk3588/host

编译buildroot

./make-Makefiles-aarch64.bash

下面这个版本可直接修改

![image-20230629153326395](image/RKISP.assets/image-20230629153326395.png)



## cmakelists.txt

这里对生成库的链接选项的修改，但是还没加上ld的修改

![image-20230703154001802](image/RKISP.assets/image-20230703154001802.png)

可执行程序这里我们已经加上了动态链接器的修改，相关工具还有patchelf [高版本gcc编译出的程序在低版本glibc机器上运行 - 简书 (jianshu.com)](https://www.jianshu.com/p/77d7f7dc93b3)

![image-20230703154204342](image/RKISP.assets/image-20230703154204342.png)









![image-20230629153230808](image/RKISP.assets/image-20230629153230808.png)



![image-20230630180708900](image/RKISP.assets/image-20230630180708900.png)
