# public_test

> [!TIP]
>
> - 本工具vpick意在数据安全相关问题的学习与研究，请勿作为其他商业活动及用途，如因此发生相关法律问题，请自行承担
> - 工具分为两个模块，【数据包 + 数据还原工具】、【数据备份工具】
> - 数据包 + 数据还原工具 = vpick-V1.0.X.tar.gz，用于安卓手机的数据还原，包里已含默认数据包
> - 数据备份工具 = vpick-V1.0.X-win64.tar.gz，PC桌面工具，用于给安卓手机做备份数据使用
> - 由于不同品牌和型号数据备份方法不同，安装vpick后请选择品牌/型号参数，即可匹配对应品牌型号的手机的备份数据
> - 当匹配到多款机型时，将随机选中其中一款

**安装步骤**：

```
#1.工具放到安卓手机
adb push vpick-1.0.X.tar.gz /data/local/tmp/
#2.解压工具包
tar -zxvf vpick-1.0.X.tar.gz
#3.安装工具
cd vpick-1.0.X && ./install.sh
#4.重启手机
```

**查询当前数据包内容**：

```
vpick list
```

**数据功能操作**：

```
#一键机型匹配到系统，例：
gif config -a device.brand=Xiaomi -a device.model=Mi10
```

**扩展数据采集**：

> [!TIP]
>
> - 提取工具包：vpick-1.0.X-win64.tar.gz
> - vpick-win64是一个在window端运行的，用于备份真机参数的工具

```
#1.需要安装adb与usb驱动，并打开真机的开发者模式，连接真机到电脑且真机给予usb连接权限（且使用传输文件模式）使用如下命令查看真机的硬件序列号,如: HWXXXXX
adbdevices.bat
#2.设置备份目标真机, 如：setsn.bat HWXXXXX
setsn.bat <硬件序列号>
#3.使用如下命令一键备份目标真机的参数,完成后将自动打开备份文件所在目录
vpick.bat
#4.采集到的tar包，例如下述例子中的命令放到实例的该路径：/data/logcal/tmp/plugin/meta/vpk/
adb push Xiaomi=POCO=POCOF2Pro=12=SKQ1.211006.001=N=cf9b5186516f8e33684598d9865a73d.tar.gz /data/logcal/tmp/plugin/meta/vpk/
```
