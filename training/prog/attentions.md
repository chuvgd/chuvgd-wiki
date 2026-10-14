---
title: 主要事情
description: 
published: true
date: 2026-10-14T12:35:55.585Z
tags: 
editor: markdown
dateCreated: 2026-10-14T12:35:55.585Z
---

不要 using namespace
- 经常冲突，尤其是min max啥的，很多库都有这种
- opencv里就有，还有矩阵运算什么的

万能头也不要用，虽然没问题，但是会
- 增加编译时长，如果赛场改代码了，编译时长太长会编译不完
- 有的编译环境不支持万能头