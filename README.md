# public_test

> [!TIP]
>
> - 本工具vpick意在技术学习与研究，请勿作为其他商业活动及用途，如因此发生相关法律问题，请自行承担
> - 工具分为两个模块，【数据包 + 生效包】、【数据搜集工具】
> - vpick会监控品牌和型号的变化，当两者同时匹配上机型库的机型时将把具体的机型参数展开
> - 当匹配到多款机型时，将随机选中其中一款

**安装步骤**：

```
#1.工具放到实例
adb push vpick-1.0.5.tar.gz /data/local/tmp/
#2.解压工具包
tar -zxvf vpick-1.0.5.tar.gz
#3.安装工具
cd vpick-1.0.5 && ./install.sh
#4.重启实例
```

**查询当前机型库**：

```
vpick list
```

**机库功能操作**：

```
#一键机型匹配到系统，例：
gif config -a device.brand=Xiaomi -a device.model=Mi10
```

**扩展机型采集**：

> [!TIP]
>
> - 第三方专用提取工具包：vpick-1.0.4-win64.tar.gz
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

> [!IMPORTANT]
>
> - 当前支持 pm list features、指纹、厂商、品牌、型号、设备名称、构建ID、构建服务主机名称、构建者、构建日期、安全补丁、平台、主板、boot、bootloader、硬件序列号、硬件版本等
> - 指纹：ro.build.fingerprint不直接修改该值，转成persist.build.v-fingerprint，工具可检测
> - 品牌：ro.product.odm.model会同步到设备名称
> - 硬件序列号：ro.serialno不是直接拷贝，会参按照机型的ro.serialno随机生成
> - 硬件版本号：小米的ro.boot.hwversion将转成AOSP的ro.boot.hardware.revision
