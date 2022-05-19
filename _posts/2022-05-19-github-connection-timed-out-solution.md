---
layout:     post
title:      "访问 Github 远程库连接超时的解决方案"
subtitle:   "github connection timed out solution"
date:       2022-05-20 00:00:00
author:     "Liang"
catalog:    true
header-style:   img
header-img: "img/in-post/github-connection-timed-out-solution/github.jpg"
header-mask:  0.5
tags:
    - note
    - github
    - git
    - vscode
---

在使用 vs code 有时莫名其妙就会遇到连接超时的问题:

`Failed to connect to github.com port 443:connection timed out` 

## 解决方案一

第一步：在终端中输入以下命令，设置全局代理。

```bash
git config --global http.proxy http://127.0.0.1:1080
git config --global https.proxy http://127.0.0.1:1080
```

代理地址 `127.0.0.1:1080` 冒号后的 `1080` 是代理端口，每个人可能都不一样，打开你的梯子查看对应端口。

如果你电脑梯子 24 小时开着，到这一步就就可以结束了。

第二步：输入以下命令，取消代理。

```bash
git config --global --unset http.proxy 
git config --global --unset https.proxy
```

然后测试推送或同步，应该就可以成功了。

## 解决方案二

[下载 Github Desktop](https://desktop.github.com/)，专注于重要的事情，而不是与 Git 争吵。无论您是 Git 新手还是经验丰富的用户，GitHub Desktop 都能简化您的开发工作流程。

在使用解决方案一之前，我就是使用此方法进行远程库的克隆、推送、同步等操作的，非常方便。

![Github Desktop](/img/in-post/github-connection-timed-out-solution/github-desktop.png)