## Python for Android 编译文档##

**Python for Android** 集合了android sdk api和python的脚本引擎，做为应用层动态脚本框架整合前期调研的原型。

### 编译Python for Android工程 ###

首先克隆Python for Android项目，环境ubuntu 64位

    sudo apt-get install git
    git clone https://github.com/kivy/python-for-android


准备编译环境

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install build-essential patch git-core ccache ant python-pip python-dev
    sudo apt-get install ia32-libs  libc6-dev-i386
    sudo apt-get install lib32stdc++6 lib32z1
    sudo pip install --upgrade cython
    sudo pip install --upgrade virtualenv
    sudo pip install --upgrade pip
    

安装配置SDK和NDK

    参考下面的URL下载最新的SDK和NDK
    http://developer.android.com/sdk/index.html
    http://developer.android.com/sdk/ndk/index.html
    
    wget http://dl.google.com/android/android-sdk_r22.6.2-linux.tgz
    wget http://dl.google.com/android/ndk/android-ndk-r9d-linux-x86_64.tar.bz2
    
    tar -xvf android-ndk-r9d-linux-x86_64.tar.bz2 
    tar -xvf android-sdk_r22.6.2-linux.tgz 


设置环境变量
    
    export ANDROIDSDK="/home/test/android-sdk-linux/"
    export ANDROIDNDK="/home/test/android-ndk-r9d/"
    export ANDROIDNDKVER=r9d
    export ANDROIDAPI=17
    
升级SDK

    ～/android-sdk-linux/tools/./android
    echo 203.208.46.200 dl-ssl.google.com >> /etc/hosts
    升级Android SDK Build Tools (api 17)

编译工程

    ./distribute.sh -m "requests==0.10.0 pyjnius android sqlite3 msgpack openssl pyopenssl twisted"



