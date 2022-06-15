# BigData帮助文档

### 1.Linux

[TOC]

#### 1.1 设置无密码 ssh

```shell
 # 可以先检查
 $ ssh localhost

 # 如果没有密码就无法 ssh 到 localhost
 $ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
 $ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
 $ chmod 0600 ~/.ssh/authorized_keys
```

#### 1.2 安装JDK

下载解压：[Java Downloads | Oracle](https://www.oracle.com/java/technologies/downloads/)

```she
tar -zxvf jdk-8u144-linux-x64.tar.gz
```

放到usr/local，修改环境变量

```shell
vi /etc/profile
```

```shell
#java environment
export JAVA_HOME=/usr/local/jdk1.8.0_211 #其中这行，需要改成你安装的实际路径，其它不用改。
export CLASSPATH=.:${JAVA_HOME}/jre/lib/rt.jar:${JAVA_HOME}/lib/dt.jar:${JAVA_HOME}/lib/tools.jar
export PATH=$PATH:${JAVA_HOME}/bin

export JAVA_HOME=/usr/local/jdk1.8.0_311

export JRE_HOME=${JAVA_HOME}/jre

export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib:$CLASSPATH

export JAVA_PATH=${JAVA_HOME}/bin:${JRE_HOME}/bin

export PATH=$PATH:${JAVA_PATH}
```

检查是否生效

```shell
source /etc/profile
java -version
```

#### 1.3 安装JDK

Xshell连接问题：

* 1.检查防火墙

```shell
# 查看防火墙状态
systemctl status firewalld.service
# 关闭防火墙
systemctl stop firewalld.service
# 开机自动启动防火墙 -> 关闭
systemctl disable firewalld.service 
```

* 2.ping，检查本地和远程虚拟机的ip地址

修改网络适配器在同一个网段
