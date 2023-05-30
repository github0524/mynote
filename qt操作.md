书中代码选择qmake和x86

需要将qt的bin目录加入path目录下才能直接运行程序

qt操作

预览界面alt+shift+r ，相当于工具的界面预览

### qt5

5.12之后的版本都不提供离线下载，可以先下载一个在线下载器

需要账号密码是最少三种的

[QT 5.15 最新安装指南（针对不同系统）_qt5.15_Home_8181的博客-CSDN博客](https://blog.csdn.net/qq_43125185/article/details/117426594)



### icon程序图标设置

![image-20230522153304773](image/qt操作.assets/image-20230522153304773.png)

这种问题要看清楚寻找的路径是那个

这里的helloworld有两层

### QPlayer视频

没有插件报错：DirectShowPlayerService::doRender: Unresolved error code 0x80040266

如果文件路径不对或者文件名是中文的，则会显示如下错误：

DirectShowPlayerService::doSetUrlSource: Unresolved error code 0x80004005 ()
https://blog.csdn.net/qq_41071706/article/details/89855986



### 多媒体播放器的解码器qplayer

[Releases · Nevcairiel/LAVFilters (github.com)](https://github.com/Nevcairiel/LAVFilters/releases)

如果不好用可以用另一个



### qt打包发布

先复制release下面的exe到一个新的文件夹下面

打开开始里面的对应的cmd 然后跳转到exe所在目录用windeploqt 加exe文件名

![image-20230522191836922](image/qt操作.assets/image-20230522191836922.png)