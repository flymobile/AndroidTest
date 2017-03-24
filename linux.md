

# CTS/GTS 运行环境 安装说明



### Linux系统安装
 
* Linux系统下载： [http://cn.ubuntu.com/download/](http://cn.ubuntu.com/download/)
 
### JDK 安装

#### 1.最新的JDK版本是：Java SE Development Kit 8u121

官方下载地址：[http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)


####  2.解压安装

将jdk 文件放到根目录
sudo mkdir java


建立好了以后，我们来到刚才下载好的压缩包的目录，解压到我们刚才新建的文件夹里面去，并且修改好名字方便我们管理

sudo tar zxvf ./jdk-7u80-linux-x64.tar.gz  -C ./java


####  3.jdk 配置环境变量

在Home界面，按Ctrl +H 按键 将隐藏文件显示出来 找到.bash_profile 文件

*  可通过Vi 工具编辑

  vi ~/.bash_profile
*  可直接通过gedit 打开（默认可双击打开）

在打开的文件的末尾添加 

      #set java environment
      export JAVA_HOME=/home/lambert/Java/jdk1.8.0_91

      export JRE_HOME=/home/lambert/Java/jdk1.8.0_91/jre

      export CLASSPATH=.:$JAVA_HOME/jre/lib/dt.jar:$JAVA_HOME/lib/tools.jar

      export PATH=$JAVA_HOME/bin:$JRE_HOME/bin:$PATH

      # Android environment
      export ANDROID_HOME=/home/lambert/Android/android-sdk-linux
      export AAPT_HOME=/home/lambert/Android/android-sdk-linux/build-tools
      export PATH=$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools:$AAPT_HOME/23.0.3/aapt:$PATH



### Android SDK 安装

国内下载[http://tools.android-studio.org/index.php/sdk](http://tools.android-studio.org/index.php/sdk)

*  下载最新SDK 并解压至Android目录

*   环境变量（同sdk且示例见上）

### 测试

##### 1 在终端上输入 java -version

显示结果：

      java version "1.7.0_80"
      Java(TM) SE Runtime Environment (build 1.7.0_80-b15)
      Java HotSpot(TM) 64-Bit Server VM (build 24.80-b11, mixed mode)
      
则说明jdk 安装成功


##### 2 进入Android 目录终端上输入 ./android

能打开android tools则成功


###  AAPT 安装

在终端上输入 apt-get install aapt

安装完成后目录终端上输入 aapt 出现相关信息则说明正常安装
      
