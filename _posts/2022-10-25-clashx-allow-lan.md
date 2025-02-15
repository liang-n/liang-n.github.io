---
layout: post
title: "如何使用 ClashX 允许局域网连接 Allow LAN"
subtitle: "How to use ClashX to allow LAN connection"
date: 2022-10-25 10:19:00
author: "Liang"
catalog: true
header-style: text
tags:
  - clashx
---

## 功能介绍

在电脑使用 ClashX 启用代理并打开 `允许局域网连接`，即可以共享网络环境给同一局域网的其他设备。

## 操作流程

第一步，打开 `允许局域网连接` 或 `Allow LAN` 开关。

![clashx](https://s2.loli.net/2022/10/25/6AxSg23wXLQGJza.png)

第二步：查看 PC 本机在局域网中的 IP 地址 `192.168.x.x`。

以 macOS 为例，打开 `系统偏好设置` -> `网络` 即可查看自己的本机 IP：

![20221025095112](https://s2.loli.net/2022/10/25/IWexoO9MPQFz4AS.png)

第三步：使用本机 IP 配置同一网络下其他设备的网络代理：`WiFi 感叹号` -> `配置代理` -> `手动`:

![20221025100716](https://s2.loli.net/2022/10/25/pwiqY4ZPzVmDEky.png)

- 服务器：填写本机 IP `192.168.x.x`
- 端口：填写 `7890`
- 认证：不开启

填写完成后保存，然后尝试打开 Google 测试一下，查看是否可以正常访问。

(o゜▽゜)o☆[BINGO!]
