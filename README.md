centos下配置git ssh
====================================
# 拿到root权限
        $ su root
        
*输入password*

*获得root权限后,以下的$符号变成#符号*
# 安装git
        $ yum install git
# git-ssh 配置和使用
## 1、设置Git的user name和email：(如果是第一次的话)
        $ git config --global user.name "humingx"
        $ git config --global user.email "humingx@yeah.net"
## 2、生成密钥
        $ ssh-keygen -t rsa -C "humingx@yeah.net"
    
运行上面命令后,连续按3个回车(如果不需要密码的话)。

最后得到了两个文件：id_rsa和id_rsa.pub。

## 3、添加密钥到ssh-agent

添加生成的 SSH key 到 ssh-agent。

        $ ssh-add ~/.ssh/id_rsa

进入ssh目录

        $ cd ~/.ssh
        
可以看到目录生成了id_rsa  id_rsa.pub两个文件

![image](https://github.com/PPMac/test/blob/master/1.png)

查看并复制id_rsa.pub的内容

        $ cat id_rsa.pub
   
![image](https://github.com/PPMac/test/blob/master/2.png)
# Gerrit用户添加ssh

进入自己的Gerrit

按下图的点击顺序找到添加公共SSH的地方

![image](https://github.com/PPMac/test/blob/master/3.png)

粘贴复制的id_rsa.pub的内容,点击add

![image](https://github.com/PPMac/test/blob/master/4.png)

# 获取代码库

cd到存放clone代码的目录

在本地运行git将代码clone到本地

        $ git clone ssh://yourname@youremail192.168.XXXXXXXXXX
        
参考:https://segmentfault.com/a/1190000002645623

http://www.jianshu.com/p/b77fd16894b6
