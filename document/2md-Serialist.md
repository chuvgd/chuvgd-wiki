---
title: 各种文档转 Markdown 格式的方法
description: 
published: true
date: 2026-09-20T14:36:24.378Z
tags: markdown
editor: markdown
dateCreated: 2026-09-20T14:35:35.496Z
---

# 各种文档转 Markdown 格式的方法

>   将会持续更新

## HTML

HTML 是和 markdown 相性最好的，也是最简单的。你可以很容易的搜索到一些在线网站实现 HTML 转 md，不过最简单的方法就是用任意一个 AI（例如豆包、kimi、deepseek），把 HTML 文件给他，让他给你转成一个 md 文件。、

## PDF

PDF 文件可以分两种：普通、图片扫描（即 OCR）

扫描文件，我基本没什么好的解决办法，这和 “图片转markdown” 似乎没什么区别。所以重点是普通文件。

首先推荐一个免费的 PDF 阅读编辑软件 [PDFgear - 免费 PDF 编辑软件和在线工具](https://www.pdfgear.com/zh/)，他相对于那些需要花钱的pdf软件（例如wps等）好很多，至少给了我一个能正常编辑文件的权力。

用 PDFgear 打开文件，在顶部菜单栏选择 `工具`->`转换`->`PDF转HTML`，然后生成导出

![image-20260822215011578](/document/assets/2md-image-20260822215011578.webp)

![image-20260822215122162](/document/assets/2md-image-20260822215122162.webp)

会在目标文件夹生成两个东西：一个是HTML文件（主要是带排版的文本）、一个叫做`image`的文件夹（包括PDF中所有图片）
![image-20260822215649824](/document/assets/2md-image-20260822215649824.webp)

这时候你就成功把图片和文本分开了，这样你可以拿着 html 文件变成 markdown。记得要处理 md 文件中图片的链接路径哦！