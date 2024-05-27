---
layout: post
title: 国行一加 11 刷氧 OS
lang: zh
tags: [tools]
---

手里的一加 5 用了 6 年突然烧坏了主板。

一年前才刚刷了 Pixel Experience，买多了一份充电套装，希望能多用几年。
没想到一觉醒来，握住的是一块没有反应的黑砖。

我只好把换手机的计划提前。

因为执着于原生系统体验，所以直接跳过了小米、OPPO 等一众优秀厂商。
而 Google Pixel 显然不是个性价比的选择，所以我的选择再次落到了一加上。

据称，自一加 12 起，国内外系统互刷被进一步阻断，让一加 12 刷氧 OS 暂时变得无解。

看起来一加 12 成熟的刷机方案还遥遥无期，为解燃眉之急，我最终下单了一加 11。

---

### 操作步骤记录

0. 备份、拆下 SIM 卡
1. 解 BL 锁
    * 打开开发者模式
        * 设置 - 关于本机 - 版本信息 - 点5次版本号
    * 开启 OEM-unlock
    * 打开 USB 调试
        * 设置 - 其他设置 - 开发者选项 - 打开 USB 调试
    * 用 ADB 工具跑命令解锁
        * 不关机，用原装数据线连电脑
        * 下载 [ADB 工具](https://developer.android.com/tools/releases/platform-tools)
        * 执行 ```adb reboot-bootloader``` 进入 fastboot 模式
        * 执行 ```fastboot flashing unlock``` 进入解 BL 锁界面
            * 若 fastboot 提示找不到设备可[手动设置驱动](https://blog.csdn.net/weixin_45675704/article/details/105483845)解决
        * 用音量键下选 ```UNLOCK THE BOOTLOADER``` 并按下锁屏键确认解锁
2. 刷系统
     * [下载 ROM](https://yun.daxiaamu.com/OnePlus_Roms/%E4%B8%80%E5%8A%A011/)
        * 拿当前系统版本号来比较找 ROM 包，版本不要回滚（据称一加 11 存在不明确未公开的“防回滚”机制，禁止用户降级到较低的版本），需要是安卓 13（我用的 CPH2449_13.1.0.580(EX01)）
        * 用解压软件把下载下来的 ROM 解压出来，以提取里面的 payload.bin 文件
     * [下载 ocdt 分区文件](https://pan.baidu.com/share/init?surl=skHH5YBnktefB79I91YdTA&pwd=v8cn)
        * 用解压软件把里面的 oos_ocdt.img 提取出来
     * 下载[刷机辅助工具](https://github.com/libxzr/FastbootEnhance/releases)
     * 进入 fastbootd 模式
        * ADB 命令行执行 ```adb reboot-bootloader``` 进入 bootloader
        * 打开 Fastboot Enhance，可以看到自己的设备
        * 双击连接后的设备，单击“Reboot to fastbootd”
     * 删除动态分区
        * 点开 partition 选项卡，根据分区名过滤"cow"，据称要将过滤出来的分区一一删除，如无则忽略，我的没有
     * 执行刷写 payload.bin
        * 确认勾选 "Ignore Unknown Partition"
        * 确认 fastbootd is YES
        * 单击“Flash payload.bin”，等待进度条完成
        * 弹出操作完成后的对话框后，点 "Reboot to bootloader"
     * 执行刷写 ocdt 分区
        * ADB 工具执行 ```fastboot flash ocdt ${你的 oos_ocdt.img 的路径}```
        * 回到 Fastboot Enhance 转回 fastbootd 执行格式化数据
3. 回锁 BL
     * 不插卡，开机跳过所有选项，不设置 PIN 码
     * 打开开发者模式
     * 开启 OEM-unlock
     * 打开 USB 调试
     * 用 ADB 工具跑命令加锁
         * ```adb reboot-bootloader```
         * ```fastboot flashing lock```
         * ```fastboot reboot```
4. 等待开机完成，进设置把系统一版一版地更新到最新版本

---

使用了一个多月，没有发现什么问题。

原本在参数页看到海外版的一加 11 支持 ESIM 不支持双卡，担心国行版刷了氧之后双卡也不可用了。
但实测刷了也还保有双卡功能，设置里有选项提示，如果开启 ESIM 那么第二个卡槽就不能做实体卡用。

希望它陪我走过一个 6 年。

---

以上参考自：
* [一加11刷氧os办法补充](https://www.bilibili.com/read/cv29346543/)
* [一加11刷机玩机的若干个坑及其处理办法](https://www.daxiaamu.com/7694/)
