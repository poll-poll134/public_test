# public_test

> [!WARNING]
>
> - 本工具vpick意在数据安全相关问题的学习与研究，请勿作为其他商业活动及用途，如因此发生相关法律问题，请自行承担
> - 工具分为两个模块，【数据包 + 数据还原工具】、【数据备份工具】
> - 数据包 + 数据还原工具 = vpick-V1.0.X.tar.gz，用于安卓手机的数据还原，包里已含默认数据包
> - 数据备份工具 = vpick-V1.0.X-win64.tar.gz，PC桌面工具，用于给安卓手机做备份数据使用
> - 由于不同品牌和型号数据备份方法不同，安装vpick后请选择品牌/型号参数，即可匹配对应品牌型号的手机进行数据还原
> - 当匹配到多款机型时，将随机选中其中一款




**1.vpick-V1.0.X.tar.gz 数据还原工具安装及使用方法**：

```
#1.使用如下命令把工具放到安卓手机
adb push vpick-1.0.X.tar.gz /data/local/tmp/
#2.使用如下命令解压工具包
tar -zxvf vpick-1.0.X.tar.gz
#3.使用如下命令安装工具
cd vpick-1.0.X && ./install.sh
#4.操作后重启手机即安装完成
```
**1)查询操作**：

```
vpick list
```

**2)还原操作**：

```
#选择对应的品牌和型号还原数据到您的手机，例：
gif config -a device.brand=Xiaomi -a device.model=Mi10
```



**2.vpick-V1.0.X-win64.tar.gz 数据备份工具安装及使用方法**：

> [!TIP]
> - 在PC上解压工具包后，在window终端运行，用于备份数据

> [!TIP]
>
> - 1.需要安装adb与usb驱动，并打开您需要备份的手机的开发者模式，手机连接到电脑后请给予usb连接权限（且使用传输文件模式）使用如下命令查看需要备份数据的硬件序列号,如: HWXXXXX
```
adbdevices.bat
```
> [!TIP]
>
>  2.使用如下命令给您需要备份数据的手机设置序列号便于识别, 如：setsn.bat HWXXXXX
```
setsn.bat <硬件序列号>
```

> [!TIP]
>
> 3.使用如下命令一键备份您手机的数据,完成后将自动打开备份文件所在目录
```
vpick.bat
```

> [!TIP]
>
> 4.备份的数据将形成一个tar包，例如下述例子中的命令放到需要还原手机的该路径：/data/logcal/tmp/plugin/meta/vpk/
```
adb push Xiaomi=POCO=POCOF2Pro=12=SKQ1.211006.001=N=cf9b5186516f8e33684598d9865a73d.tar.gz /data/logcal/tmp/plugin/meta/vpk/
```
