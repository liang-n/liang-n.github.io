---
layout:     post
title:      ".gitignore 不生效的解决方案"
subtitle:   "gitignore invalid"
date:       2022-05-17 02:00:00
author:     "Liang"
catalog:    false
header-style:   img
header-img: "img/in-post/gitignore-invalid/gitignore.jpg"
header-mask:  0.5
tags:
    - note
    - github
    - git
---

在项目开发过程中，一般都会添加 `.gitignore` 文件，规则很简单，但有时会发现规则并没有生效。

原因是 `.gitignore` 只能忽略那些原来没有被 `track` 的文件，如果某些文件在填入忽略规则之前已经被纳入了版本管理中，则修改 `.gitignore` 是无效的。

此时的解决方法就是先把本地缓存删除（改变成未 `track` 状态）：

```bash
git rm -r --cached .
```

使用此命令清理掉本地缓存之后，文件规则就会生效，确认生效后提交即可。