# TVRemoteIME 
电视盒子的远程输入法应用，可跨屏远程输入、跨屏远程控制盒子、HTTP/RTMP/MMS网络视频直播、ED2K/种子文件的视频文件边下边播

# 应用的诞生
自从家里有电视盒子以来，电视收看、电影播放、娱乐小游戏什么的都是直接在盒子里运行，因为电视屏幕比起手机屏幕大，玩起来那效果是手机没法比的，但是在娱乐的过程中也总是有一些不便，比如玩游戏过程中想聊天什么的，在电视盒子里输入文字用遥控器按？只有用过才知道痛苦！外挂物理键盘，可惜很多输入法都不支持物理键盘的同时输入，远远达不到电脑的效果！于是找了很多遥控与跨屏输入的软件，但可惜没有一款是比较理想的，特别家里的一个创维Q+二代盒子，只要一进游戏的聊天界面，不管外面设置了什么跨屏输入法，都会自动切换为厂家自带的百度输入法，非常的可恶！于是就有了自己做一款远程跨屏的输入法，于是这TVRemoteIME就这样诞生了…………  

# 它能做什么  
它能帮助盒子实现跨屏输入，以后在盒子里聊天打字要多快就有多快；它能代替盒子遥控器，用手机，电脑，IPAD摇控盒子都不是问题；它能管理盒子的应用，一键快速启动/卸载应用；它能跨屏安装应用与传送文件到盒子；还能实现HTTP/RTMP/MMS网络视频直播、ED2K/种子文件的视频文件边下边播。

# 安装方法
## 一、通过adb命令安装应用  
1、电视盒子开启adb调试 

2、电脑通过adb命令连接电视盒子（假如电视盒子的内网ip为：192.168.1.100）  
`adb connect 192.168.1.100:5555`  
注意,手机要与盒子在同一个WIFI网络(内网网络)  执行`adb devices`命令显示有device列表，则表示已连接上盒子，可继续下一步

3、通过以下命令安装输入法apk包  
`adb install IMEService-release.apk`  

4、设置为系统默认输入法  
`adb shell ime set com.android.tvremoteime/.IMEService`  

5、电脑或者手机访问远程输入法的控制页面
`http://192.168.1.100:9978/`  

## 二、通过U盘或者其它方式安装  
1、安装后在盒子应用列表里找到TVRemoteIME的图标点击运行  

2、根据应用的提示进行设置即可。  

## 控制界面示例截图  
注： 输入控制端不需要安装任何APK应用，直接浏览器操作  

![示例截图](https://raw.githubusercontent.com/kingthy/TVRemoteIME/master/released/screenshot.jpg "控制界面示例截图")  

# 引用第三方包/资源说明
1、[NanoHttpd](https://github.com/NanoHttpd/nanohttpd "NanoHttpd")  用于实现HTTP WEB服务  

2、[ZXing](https://github.com/zxing/zxing/ "QRCode") 用于实现二维码的输出
 
3、[悟空遥控](http://www.wukongtv.com/views/input.html "悟空遥控")  非常棒的一款遥控软件。  
注：本软件远程控制端的遥控导航面板设计图和小部分CSS代码参考于它。

4、[AFAP Player](https://github.com/AFAP/Player "ijkplayer") 用于实现视频播放

5、[MiniThunder](https://github.com/oceanzhang01/MiniThunder "MiniThunder") 用于实现视频文件下载功能