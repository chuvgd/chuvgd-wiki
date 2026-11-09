---
title: 一种NFC+飞书物资登记设想
description: 
published: true
date: 2026-11-09T11:23:26.933Z
tags: 
editor: markdown
dateCreated: 2026-11-09T11:23:26.933Z
---

## 1 NFC标签

一种无线标签，当前大部分手机都适配了，把标签贴近手机即可，功能包括：

-   显示文本
-   打开软件
-   打开网址（uri）
-   电子名片
-   etc

![](https://ts1.tc.mm.bing.net/th/id/OIP-C.9SC0sr7T-NQLRG3pAwHIdAHaFV?r=0&rs=1&pid=ImgDetMain&o=7&rm=3)

大小多样，内存也多样。如果要贴在金属上，也有防金属干扰的。淘宝3块10个差不多。

下面主要用打开网址链接的功能。

## 2 飞书表单

1.   使用多维表格，可以设置自动程序，填写表格

     ![](https://image.woshipm.com/wp-files/2023/03/aebm8fS3eEi3iniuaBUN.png)

2.   收集表可以预填写

     例如表格的分享链接为 `https://xxxxx.feishu.cn/share/base/form/xxxxxxxxxxxxxxx`，这时候你在末尾加上`?prefill_物品ID=2`，也就是`https://xxxxx.feishu.cn/share/base/form/xxxxxxxxxxxxxxx?prefill_物品ID=2`

     这时收集表你用这个链接打开，收集表中的`物品ID`就会被自动填写为`2`

3.   applink可以自动打开飞书app软件

     你想收集谁填写的表格，所以需要登录。但是如果用浏览器打开你就需要在浏览器中登录飞书再写，不如直接打开飞书。

     applink可以把一个链接用飞书软件打开，你把这个收集表链接放到 [AppLink 工具](https://webview.feishu.cn/applinktool) 中，功能选择网页，目标网页 URL就是收集表分享链接，打开H5容器模式选appCenter，下面就会生成预览链接，你用这个链接打开的网页，会自动要求跳转到飞书app。

## 3 物资管理

创建多维表格在飞书，在里面创建物资领用收集表，并创建一个总的物资信息表格。

我希望设备上有一个NFC标签，用手机扫可以跳转到飞书的领用表，并预填写这个物品的ID。

收集表分享链接加上预填写就是这个物品的专属填写链接，你可以自己随便改这个ID就可以给不同设备。然后通过applink处理得到直接打开飞书的URL链接，把链接用 NFC Writer 等软件写入到NFC标签中，贴在这个物品上即可

## 4 链接太长？

有的NFC标签里的芯片内存小，只有144字节，他型号就是这样。你可以尝试用“短链接”压缩这个很长的applink链接（具体用什么见仁见智~~因为我也没找到好的qwq~~）