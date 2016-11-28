# Linux OS

[TOC]

## 安装系统更新

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist upgrade
```



## 安装Flash Player 和 Pepper Flash 插件

```
sudo apt-get install flashplugin-installer pepperflashplugin-nonfree
sudo update-pepperflashplugin-nonfree --install
```



## 禁用访客模式     

```
sudo sh -c 'printf "[SeatDefaults]nallow-guest=falsen" >/usr/share/lightdm/lightdm.conf.d/50-no-guest.conf'
  执行完后重启
```



## 文本编辑器gedit

```
sudo apt-get install gedit
```



## 修改hosts 

​    获取hosts  ： [老D博客](https://laod.cn/hosts/2016-google-hosts.html)

```
cd /etc/ 
sudo gedit hosts
```

```
sudo systemctl restart NetworkManager
```



## 安装chrome

```
sudo apt-get install google-chrome-stable
```



## Java SE Development Kit



### 下载最新版本 JDK 

​	Downloads | [Oracle]( https://www.oracle.com/downloads/index.html)

### 解压文件

```
$ sudo mkdir /usr/lib/jvm
$ sudo mv jdk-8u5-linux-i586.tar.gz /usr/lib/jvm/
$ cd /usr/lib/jvm/
$ sudo tar -zxvf jdk-8u5-linux-i586.tar.gz
$ rm ./jdk-8u5-linux-i586.tar.gz
```

### 配置

```
$ sudo gedit /etc/environment

在environment中修改PATH，追加JDK路径，添加CLASSPATH与JAVA_HOME后如下：
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/lib/jvm/jdk1.8.0_05/bin"
CLASSPATH="/usr/lib/jvm/jdk1.8.0_05/lib"
JAVA_HOME="/usr/lib/jvm/jdk1.8.0_05"

然后就是要告诉系统，我们使用的sun的JDK，而非OpenJDK了：
$ sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.8.0_05/bin/java 300
$ sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk1.8.0_05/bin/javac 300
$ sudo update-alternatives --config java
有 2 个候选项可用于替换 java (提供 /usr/bin/java)。
选择 路径 优先级 状态
------------------------------------------------------------
* 0 /usr/lib/jvm/java-6-openjdk/jre/bin/java 1061 自动模式
1 /usr/lib/jvm/java-6-openjdk/jre/bin/java 1061 手动模式
2 /usr/lib/jvm/jdk1.8.0_05/bin/java 300 手动模式
要维持当前值[*]请按回车键，或者键入选择的编号：2
=======

如上所示，这样就设置好了要使用的java了。

```

##  Audio 音频插件

```
sudo apt-get install libpulse-dev
```


## 安装 TLP 以延长电池寿命，减少发热

```
sudo add-apt-repository ppa:linrunner/tlp
sudo apt-get update
sudo apt-get install tlp tlp-rdw
sudo tlp start
```

## ************************************************************************

## Steam

### Install

```
 sudo apt-get install steam
 Fix // sudo apt-get install libgtk2.0-0:i386 libidn11:i386 libglu1-mesa:i386
```

### Run

```shell
 LD_PRELOAD='/usr/$LIB/libstdc++.so.6 /usr/$LIB/libgcc_s.so.1 /usr/$LIB/libxcb.so.1 /usr/$LIB/libgpg-error.so' steam
```



 ***

# © Created by huni1lian

## 2016年10月

## 