tb-common-utils
===============

tbsys and tbnet repository mirror for alibaba

1.下载tbnet 
    下载地址：http://code.taobao.org/p/tb-common-utils/src/trunk/tbnet/ ，它的svn地址为：http://code.taobao.org/svn/tb-common-utils/， 直接用svn checkout即可。 
    下载那天官方网站不能打开，从一个人的gibhub下下载了代码：https://github.com/kayaklee/tb-common-util/tree/master/trunk
2.设置环境变量 
    export TBLIB_ROOT=$HOME/ob-install-dir 
    注1：$HOME/ob-install-dir指代的是安装位置 
    注2：安装和使用tbnet和tbsys之前，要设置TBLIB_ROOT这个环境变量，这个环境变量指示了安装tbnet和tbsys库的路径。 
    注3：=号两边不能有空格
3.设置include头文件路径 
    因为tbnet和tbsys在两个不同的目录，但它们的源码文件里头文件的互相引用却没有加绝对或相对路径，需要使用环境变量添加tbnet和tbsys的头文件路径：export CPLUS_INCLUDE_PATH=$CPLUS_INCLUDE_PATH:/home/tb-common-utils/tbsys/src:/home/tb-common-utils/tbnet/src，否则编译时会出现：“fatal error:tysys.h: No such file or directory”的错误。
4.下载的代码有个错误：具体是tbsys/src/tblog.cpp中323行代码:需要将CLogger::CLogger& CLogger::getLogger()改为CLogger& CLogger::getLogger()
5.安装 
    cd tb-common-utils 
    sh build.sh 
注：安装成功后，TBLIB_ROOT所指示的目录下会有include和lib两个目录
