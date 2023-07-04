ubuntu

静态ip

1.查看网关地址

![image-20230621103252991](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230621103252991.png)

2.查看dns

![image-20230621103338795](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230621103338795.png)

![image-20230621103418419](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230621103418419.png)

## 静态ip桌面配置方法

首先查看到原来自动获取IP的信息如下

注意DNS和默认路由是一样的

![image-20230621105145764](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230621105145764.png)

在ipv4中配一样的即可

![image-20230621105332345](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230621105332345.png)

打开火狐进入知乎成功即可

## ssh免密登录

连接ssh后

在cmd输入**`ssh-keygen`**，会生成公钥，私钥

![image-20230621111052286](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230621111052286.png)

![image-20230621111210288](C:\Users\scl\AppData\Roaming\Typora\typora-user-images\image-20230621111210288.png)

设置免密登录

表示生成的公钥和秘钥，注意圈起来的路径文件，需要将其拷贝到你的远程ssh主机中，我远程主机时虚拟机，所以仅将其上上传到/home文件夹下即可，也就是吧id_rsa.pub文件拷贝（PS：刚才圈起来的按个目录一定有这个文件）。
之后操作远程ssh主机：

mkdir .ssh 可能已经有了
mv id_rsa.pub .ssh
cd .ssh
cat id_rsa.pub >> authorized_keys
sudo chmod 600 authorized_keys
service sshd restart

可能在最后一条命令要输出你的账号登录密码。
这样远程ssh主机配置免密码登录就完成了。
然后你可以在vscode重复打开远程ssh的步骤，看看是否还需要输入密码了。

https://blog.csdn.net/weixin_42397613/article/details/114983147



## 换源

[(137条消息) 解决Ubuntu apt update更新太慢的问题_apt update 慢_熹微橙光的博客-CSDN博客](https://blog.csdn.net/qq_39690706/article/details/113270222)

清华镜像站选版本

[ubuntu | 镜像站使用帮助 | 清华大学开源软件镜像站 | Tsinghua Open Source Mirror](https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/)

**操作步骤**

做个备份

sudo cp /etc/apt/sources.list  /etc/apt/sources.list.bak

编辑文件内容 把文件里的内容全部替换成上面的阿里源或者清华源

sudo vi /etc/apt/sources.list

这个时候你会发现更新速度很快很快

sudo apt-get update
sudo apt-get upgrade