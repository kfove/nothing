# Windows C/C++环境部署

## 1.1 打开MinGW官网

* 注意，vs是不用的，vscode有时会自带不用部署

打开[官网下载页](https://www.mingw-w64.org/downloads/)

![](https://s3.bmp.ovh/imgs/2022/08/01/8539510da83b7439.png)

主要介绍这两

MingW安装简单（推荐）

MSY32较为复杂

# 1.2 MingW教程

点击**[MingW-W64-builds](https://www.mingw-w64.org/downloads/#mingw-builds)**

<img src="https://s2.loli.net/2022/08/01/vbaG6C2TDLchPXK.png" alt="屏幕截图 2022-08-01 135929.png"  />

选择[Github](https://github.com/niXman/mingw-builds-binaries/releases)

![屏幕截图 2022-08-01 140336.png](https://s2.loli.net/2022/08/01/sBoGIaFO92me6Uv.png)

根据系统下载对于版本，下载慢请搞好网络(科学上网，hosts，镜像，cdn加速)

安装好后解压至你想的文件夹

![屏幕截图 2022-08-01 140739.png](https://s2.loli.net/2022/08/01/IQlLyDu89doSZpA.png)

然后部署path，win+s输入path打开环境变量

![屏幕截图 2022-08-01 140902.png](https://s2.loli.net/2022/08/01/hWgIsc8Cv5QTqHa.png)

选择环境变量

![屏幕截图 2022-08-01 141116.png](https://s2.loli.net/2022/08/01/6jF23KH8kuqt1U4.png)

双击path打开

![屏幕截图 2022-08-01 141234.png](https://s2.loli.net/2022/08/01/aRJcFliAKzMemuj.png)

选择浏览->选择解压文件夹？mingw32中的bin文件夹->确定保存

![屏幕截图 2022-08-01 141433.png](https://s2.loli.net/2022/08/01/1lxwySenYPKQf2r.png)

命令提示符输入，g++ --version 或 gcc --version 如下图输出，成功

![屏幕截图 2022-08-01 141806.png](https://s2.loli.net/2022/08/01/86s35IXPfKOdjuB.png)

# 1.3 msys2部署

点击MinGW官网下的[MSYS2](https://www.mingw-w64.org/downloads/#msys2)

点击[Github](https://www.msys2.org/),如下界面(哈哈哈不是github界面)

![](https://files.catbox.moe/y9xak8.png)

这里跟官网教程走就行。。。。。。。。。。。。。

下载完成后安装，根据自己配置安装

运行软件如图

![](https://files.catbox.moe/m1ill7.png)

这里Arch linux和Mac book用户操作很熟悉吧(pacman包管理器)

输入 

pacman -Syu

他会下载包，提示直接回车(下载速度根据网络环境而定或源地址)

完成后窗口消失了，再去打开MSYS2,最下面那个

![](https://files.catbox.moe/kmmd4p.png)

再次输入

pacman -Syu

提示直接回车，等待拉取包完成

输入

pacman -Ss gcc

搜索gcc的包

![](https://files.catbox.moe/elm725.png)

选择自己系统适配的

我这选择mingw64/mingw-w64-x86_64-gcc

输入以下安装

pacman -S mingw64/mingw-w64-x86_64-gcc

或

pacman -S mingw-w64-x86_64-gcc

报错在输入一次即可

然后安装调试

输入

pacman -Ss gdb

搜索包

同样安装自己系统适配的包

我在安装mingw64/mingw-w64-x86_64-gdb

pacman -S mingw64/mingw-w64-x86_64-gdb

或

pacman -S mingw-w64-x86_64-gdb

然后打开msys32安装文件夹

我下载的是ming64发行版，文件夹例：C:\msys64\mingw64\bin

如下

![](https://files.catbox.moe/pcqmbl.png)

把路径添加至环境变量中

![image-20220801151518627](C:\Users\Ryo\AppData\Roaming\Typora\typora-user-images\image-20220801151518627.png)

保存

gcc --version

g++ --version

gdb --version

![](https://files.catbox.moe/l868e4.png)

有以上输出即可，那个错误是我打错了

我安装了sdk环境所以是cd到目录

你们正常是用户目录

本人学艺不精，有错误还请见谅

