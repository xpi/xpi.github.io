---
layout: post
title: "树莓派+volumio+DAC声卡+WIFI热点组建DLNA HIFI播放器"
---

首先感谢以下大神的文章（本文是在以下文章中总结出来的，建议先按照大神的思路走一遍，碰到问题再来看本文）：

http://wangye.org/blog/archives/845/

http://ju.outofmemory.cn/entry/1351

硬件材料：树莓派(b2和2代都测试过)，内存卡，无线USB网卡，内存卡，U盘，淘宝那种PCM5122的DAC山寨声卡

软件材料：封装好的Volumio(http://pan.baidu.com/s/1jGgk84m 密码: fo9g),当然后面还要配置网络
<img src="/img/post/1.jpg" width='600'>
<img src="/img/post/2.jpg" width='600'>
<h2>第一步： 系统安装</h2>
Volumio开始是没有密码的，所以用SHH是登录不到，最好是用屏幕和键盘在树莓派主机上配置好密码。

配置密码在：sudo raspi-config

PS：在volumio的所有命令行操作都要加上 sudo 

<h2>第二步： 网络配置</h2>	
懒得打了：参照以下

http://wangye.org/blog/archives/845/

这里面有两种方案：第一种是能够顺利使用DLNA，但是没有DHCP服务器，不插路由器的话手机连上去是获取不了IP的.

第二种方案是路由器模式，但手机端却不能搜索到树莓派的DLNA了，修复方法是下面这篇文章给的思路.

http://ju.outofmemory.cn/entry/1351

看完后我把一下参数改了一下

listening_ip=192.168.4.1  #其实这个就wlan0的ip

friendly_name=volumio  #这里默认是注释掉了的，把它去掉

notify_interval=60  #还有这个通知改成了60秒，这样DLNA服务就更容易搜索到了

保存之后执行：

停止minidlna服务<br>
sudo service minidlna stop

让minidlna随机启动<br>
sudo update-rc.d minidlna defaults 

启动minidlna服务<br>
sudo service minidlna start 

<br>
<h2>第三步： 安装手机端APP</h2>
国内的貌似只有网易音乐支持DLNA，在设置那可以找到，打开了DLNA选到Volumio，然后就可以回到主界面播放任何音乐（包括网络音乐）
<img src="/img/post/3.png" width='400'>
<img src="/img/post/4.png" width='400'>

国外的有一个叫"DLNA Total Media"的DLNA播放器，只支持播放文件音乐，不过可以听到国外网络电台是亮点（貌似很多台)。
<img src="/img/post/5.png" width='400'>
<img src="/img/post/6.png" width='400'>


