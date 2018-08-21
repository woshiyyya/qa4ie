python2环境下按教程安装nel  
安装Spark框架，配置环境变量  
下载wikipedia Article并解压
下载wikidata数据并解压   
安装JAVA并配置JDK、JRE PATH  
安装TOMCAT并配置JVM虚拟机最大堆内存Xmx参数（procceding）




# 从头开始配置nel
## 1.安装anaconda3
下载anaconda3 （https://www.anaconda.com/download/#linux）
```
wget https://repo.anaconda.com/archive/Anaconda3-5.2.0-Linux-x86_64.sh
bash Anaconda3-5.2.0-Linux-x86_64.sh
```
新建python2环境
```
conda create -n py2 python=2.7
```

## 2.安装配置JAVA
下载jdk8_xxx.tar.gz
```
tar -xzvf jdk8_xxx.tar.gz
```
添加PATH到/etc/profile
```
sudo vi /etc/profile
```
将下列内容添加到最后
```
export JAVA_HOME=/[usr]/jdk1.8.0_181
export JRE_HOME=$JAVA_HOME/jre
export CLASSPATH=.:$CLASSPATH:$JAVA_HOME/lib:$JRE_HOME/lib
export PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
```
立即激活并检查
```
source /etc/profile
java -version
```

## 3.安装配置TOMCAT
```
sudo apt-get install tomcat8 tomcat8-docs tomcat8-examples tomcat8-admin
```
安装目录为 **/usr/share/tomcat8**
```
sudo chmod 777 -R tomcat8
cd tomcat8/bin
bash startup.sh
```
若出现cannot touch /usr/share/tomcat8/log/catalina.out, 手动建立logs文件夹并修改权限  
启动成功！

### 更改JVM最大堆内存参数
在catalina.sh 添加,(这里设置了40G) 
```
JAVA_OPS="-Xmx40960m"
```

## 4. 安装scala
从 https://www.scala-lang.org/download/ 找到压缩包
```
sudo mkdir /sur/lib/scala
sudo tar -zxvf scala-2.12.6.tgz -C /usr/lib/scala
```

打开/etc/profile, 在最后添加配置
```
export SCALA_HOME=/usr/lib/scala/scala-2.12.6
export PATH=${SCALA_HOME}/bin:$PATH
```
激活profile，输入scala测试是否安装成功。

## 5.安装配置Spark

## 6. 安装nel及sift库
