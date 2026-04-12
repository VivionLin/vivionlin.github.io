---
title: 用 200 元的 TV 棒收看全球流媒体
date: 2024-03-29 20:46:00 Z
categories:
- tools
layout: post
---

个人需求：
- 收看跨地区的体育直播 / 实时节目 / 影视作品
- 需要海量资源作“沉浸式”外语听力训练
- 不刷机的前提下，替换投影仪点播的内容
- 差旅或回家，替换电视看到的内容

### 购置 TV 棒

海鲜市场淘个 240 包邮的 Google Chromecast HD（或 Amazon Fire TV，Apple 用户可选 Apple TV）：
![Chromecast HD](https://tse2.mm.bing.net/th/id/OIP.v1qt7aOl5EhPSAO5sjnigwHaHa?rs=1&pid=ImgDetMain&o=7&rm=3)

像用了一半的肥皂一样小，非常适合携带。带一个 HDMI 口接显示，Type C 接 5V1A 电流。操作系统 Google TV 是 based on Android，所以能看到大多数眼熟的系统配置。不同之处在于这个系统针对 TV 的场景做了定制，开屏首页就是内容推荐，另外通过 Play Store 只能搜到的特定的 app 种类。
![Google TV](https://cdn.mos.cms.futurecdn.net/XE45okrybPWAy32eeSXCee.jpg)

网络环境方面，如果没有官方业务支持的网络导致要通过 VPN 访问的话，需要注意机器激活时由于不能设置网络连接高级选项，会导致无法走代理，可参考 [不良林](https://bulianglin.com/archives/sharenetwork.html) 的思路解决问题：
- 软路由
- 部分在 Network & internet > Hotspot & tethering 下有 **Allow clients to use VPNs** 的 Android 机（如亲儿子 Pixel）可以直接通过分享热点共享手机接上的 VPN 网络
- root 的 Android 手机可通过 VPNHotspot 共享网络
- 某些 VPN 软件可以在 windows 创建 TUN/TAP 虚拟网卡，配合 windows 10/11 的 mobile hotspot 功能（会自动创建一张新的虚拟网卡）、或机子本身有的多余网卡，进行网络连接共享

激活成功后，如需单独为 Chromecast 安装 VPN，但对应的 app 无法通过 Play Store 安装，可转油管找 ADB 推送安装的教程。
此外，中国区可能会显示网络连接受限，需要修改时间更新服务器的地址。

### 流媒体订阅

一旦网络环境没有问题，可以选择订阅更多流媒体服务：
* 优秀原创剧集比较多的是 Netflix，$6.99 起/月，合租可以做到 ¥15/月
* 资源收录最丰富的 Amazon Prime Video，印度地区费用最便宜，合租差不多 ¥15/月
* 要动画 / 体育直播的，Hulu + Disney + ESPN 合租可以做到 ¥40/月
* 喜欢看 NBA 原声的，赛季初拼 League Pass Premium 可以做到 ¥72/年
* 不差钱可直接上 Youtube TV，base plan $72.99/月，ABC、CBS、FOX、NBC、National Geography、HBO 一批频道全都能解锁
* 跟 Youtube TV 类似的 Sling TV 定价要便宜 10 刀，但是有地域判断

即便用 Chromecast 收看流媒体也是不能避开相应平台的地域 / IP 检测行为的，甚至 Netflix 对 TV 端的判断还要更加严格，需要切 IP 区域还是要注意所用的 VPN 的解锁能力。

一旦摆平网络问题，就可以带着它四处顶替无聊的 xx 智能电视 / xx 投影仪 / 老家旧电脑上的影视内容磨耳朵啦。
