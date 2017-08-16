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

查看并复制id_rsa.pub的内容

        $ cat id_rsa.pub
    

