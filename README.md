# Vieux-catalina


**针对mac电脑用户catalina 10.15.7系统下使用，Vieux降级iphone设备（Linux、Windows用户绕道）**



机器说明

* 机器：macbook pro
* 系统：macOS Catalina 10.15.7



**1、下载当前项目进入根目录**

```bash
$ cd Vieux-catalina
```



**2、执行CatalinaFix.sh脚本**

```bash
# In MacOS Catalina, there is a new security feature that causes issues with the script
$ ./CatalinaFix.sh
```



**3、查看设备支持的降级版本**

```bash
$ ./vieux -l
Currently supported device:

Device iPhone4,1, iOS 6.1.3
Device iPhone4,1, iOS 8.4.1

Device iPhone5,1, iOS 8.4.1
Device iPhone5,2, iOS 8.4.1
# ...
```



**4、下载对应固件**

* https://ipsw.me/download/iPhone6,1/14G60 （iphone 5s - 10.3.3 固件）
* 下载的文件 iPhone_4.0_64bit_10.3.3_14G60_Restore.ipsw



**5、手机进入DFU模式**

以iphone5s为例

1. 手机关机后连接电脑（现实充电图标）
2. 按开机按键 2s 后，立马加按home键一起持续10s（黑屏）
3. 松开开机按键，保持home建继续按10s即可



**6、sudo方式执行脚本**

```
sudo ./vieux -i "/Users/Kang/work/iPhone_4.0_64bit_10.3.3_14G60_Restore.ipsw"
```



*（使用的python3.8、手机走进度条，终端中途报错无视）*



**如果出现错误"ValueError: The device has no langid!"**

尝试重新折腾安装libusb

```bash
$ brew install  libusb
# 根据提示一顿操作
$ brew link --overwrite libusb
```

