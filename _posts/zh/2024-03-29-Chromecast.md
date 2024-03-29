---
layout: post
title: 用 200 元的 TV 棒收看全球流媒体
lang: zh
tags: [tools]
---

**个人需求**

- 收看跨地区的体育直播 / 实时节目 / 影视作品
- 需要海量资源作“沉浸式”外语听力训练
- 在不刷机的前提下，替换投影仪点播的内容
- 差旅或回家，替换电视看到的内容

**方案**

TV 棒 + 流媒体订阅

---

在海鲜市场淘了 240 包邮的 Google Chromecast HD。

选它没选 Apple TV 或 Amazon Fire TV 完全是因为手机是原生 Android。

![Chromecast HD](https://www.maketecheasier.com/assets/uploads/2021/03/how-to-reset-chromecast-chromecast-google-tv.jpg)

像用了一半的肥皂一样小，非常适合携带。

带一个 HDMI 口接显示，Type C 接 5V1A 电流。能看 4K 视频的是单独的 4K 版本。

---

操作系统是 Google TV。Based on Android 所以能看到熟悉的 Android 机配置项。

但针对 TV 的场景做了定制和舍弃，开屏首页就是内容推荐。通过 App Store 装 app 但只能搜到的特定的 app 种类。

![Google TV](https://cdn.mos.cms.futurecdn.net/XE45okrybPWAy32eeSXCee.jpg)

---

对于网络环境，有线电缆需要接在特定的电源适配器上。

如果网络环境不受官方业务支持，则需要有 VPN 才能使用。

其中，机器激活对 wifi 连接的要求要比激活后严格。

因为激活时能选择的 wifi 连接，不能设置高级选项，这就使得需要设置代理的连接代理效果无效。

可参考 [不良林](https://bulianglin.com/archives/sharenetwork.html) 的思路和操作：

- 软路由
- 部分在 Network & internet > Hotspot & tethering 下有 **Allow clients to use VPNs** 的 Android 机（如亲儿子 Pixel）可以直接通过分享热点共享手机接上的 VPN 网络
- root 的 Android 手机可通过 VPNHotspot 共享网络
- 某些 VPN 软件可以在 windows 创建 TUN/TAP 虚拟网卡，配合 windows 10/11 的 mobile hotspot 功能（会自动创建一张新的虚拟网卡）、或机子本身有的多余网卡，进行网络连接共享

激活成功后，如果需要单独为 Chromecast 安装 VPN（方便携带），但对应 VPN app 在 App Store 搜不到，油管有大量教程教授如何用同一局域网下的电脑通过 ADB 推送安装。

中国区可能会显示网络连接受限，需要修改时间更新服务器的地址。

一旦搞定了网络环境，至少就能用它看油管视频了，也可以选择订阅更多的流媒体资源。

---

流媒体服务方面，优秀原创剧集比较多的 Netflix，$6.99 起/月，合租可以做到 ¥15/月。

资源收录最丰富的 Amazon Prime Video，印度地区费用最便宜，合租差不多 ¥15/月。

要动画 / 体育直播的，Hulu + Disney + ESPN 合租可以做到 ¥40/月。

不差钱可直接上 Youtube TV，base plan $72.99/月，ABC、CBS、FOX、NBC、National Geography、Max、NBA、Disney、HBO 等全都能解锁。

跟 Youtube TV 类似的 Sling TV 定价要便宜 10 刀，但是有地域判断。

也就是用 Chromecast 收看流媒体也是不能避开平台的地域 / IP 检测行为的，甚至 Netflix 对 TV 端的判断更加严格，需要切 IP 区域还是要注意 VPN 的解锁能力。

---

至此，便可带着它四处顶替无聊的 xx 智能电视 / xx 投影仪 / 老家的旧电脑上的影视内容，刷视频练听力啦。
