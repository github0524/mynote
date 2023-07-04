VENC

![image-20230620160652271](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230620160652271.png)

**argparse**

参数解析

argparse_option 命令行选项

typedef int argparse_callback (struct argparse *self,

​                const struct argparse_option *option);

参数解析回调，参数解析上下文和命令行参数











## GOP

group of pictures 一组完整的视频帧，完整意思是拿出来能完整的播放、显示。

也代表两个I帧的间隔 码率相同的情况下，GOP越大，P\B帧越多、图像质量越高。

应该说是两个IDR帧之间的间隔 IDR就是第一个I帧，这个I帧和前面不能有关系比如前面一个是B帧就不行

## 视频帧头信息

PTS 显示信息

DTS 解码时间



I帧是关键帧

intra picture

## IDR帧：

Instantaneous Decoding Refresh，及时解码刷新。我一般称它为immediate refresh ，立刻刷新，IDR帧必须是一个I帧，但是I帧不一定是IDR帧，这个帧出现的时候，是告诉解码器，可以清除掉所有的参考帧，这是一个全新的序列，新的GOP已经开始



## 码流：

或者称为码率，只针对视频数据，单位时间内视频数据量大小，一般以秒为单位(KB/S)。

码率=视频数据大小/视频时间长度。

对于直播之类的计算，码流=视频传输数据量/传输时间。

在直播中，两种方式计算的码流应该是近似相等的，否则就会出现类似延时，卡顿等情况。

## 叠加和遮挡

![image-20230620161354261](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230620161354261.png)