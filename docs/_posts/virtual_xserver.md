## 虚拟X服务器方案
在后端服务器没有图形界面的情况下，有时需要运行一些图像渲染的程序，比如OpenGL程序、office等。就需要使用虚拟一个X Server 出来。
常见的方案有

### xvfb-run
```
xvfb-run -s "-ac -screen 0 1280x1024x24" npm start
```
应用：
- [FFCreator 一个基于node.js的高速视频制作库](https://github.com/tnfe/FFCreator)

###  xserver-xorg-video-dummy
按照如下方式，设置配置文件，
```
Section "Monitor"
        Identifier "dummy_monitor"
        HorizSync 28.0-80.0
        VertRefresh 48.0-75.0
        Modeline "1920x1080" 172.80 1920 2040 2248 2576 1080 1081 1084 1118
EndSection

Section "Device"
        Identifier "dummy_card"
        VideoRam 256000
        Driver "dummy"
EndSection

Section "Screen"
        Identifier "dummy_screen"
        Device "dummy_card"
        Monitor "dummy_monitor"
        SubSection "Display"
        EndSubSection
EndSection
```
然后启动X server
```
X :0 -config dummy.conf
```
应用
- [pywpsrpc WPS Office for Linux二次开发C++接口Python绑定.](https://github.com/timxx/pywpsrpc)
