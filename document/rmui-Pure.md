---
title: 南航RoboMaster UI设计器移植说明
description: 
published: true
date: 2026-09-20T14:31:30.065Z
tags: 嵌入式, rmui
editor: markdown
dateCreated: 2026-09-20T14:31:30.065Z
---

# 南航RoboMaster UI设计器移植说明

>   本移植说明基于达妙 mc02 开发板，使用 ac6 编译器，使用动态版 【RM2024 赛季‑UI 设计器开源】南京航空航天大学‑RoboMaster社区：https://bbs.robomaster.com/article/9614

下面是移植中遇到的问题和建议

在线设计器网站以及主页面

![UI设计器主页面](/document/assets/rmui-pure-image1.webp)

使用 insert 插入所需要的图形并修改，注意文件名不要重复

![UI Window属性面板](/document/assets/rmui-pure-image2.webp)

点击 ui window 属性界面，可以修改机器人类型和队伍，这个后面要根据裁判系统返回来改

![File菜单生成动态代码](/document/assets/rmui-pure-image3.webp)

## 生成代码

全选然后下载

![导出代码界面](/document/assets/rmui-pure-image4.webp)

![文件列表](/document/assets/rmui-pure-image5.webp)

得到六个文件全部移植进工程文件夹

![文件导出](/document/assets/rmui-pure-image6.webp)

## 下面是代码要修改的部分

首先是 `ui_interface.h` 发送函数修改成

```
#define SEND_MESSAGE(message, len) HAL_UART_Transmit_DMA(&huart1, message, len); osDelay(10);
```

串口根据代码自己修改，记得引入 `usart.h` 和 `cmsis_os.h`

![ui_interface.h代码](/document/assets/rmui-pure-image7.webp)

然后是 `ui_interface.c`

![ui_interface.c代码片段](/document/assets/rmui-pure-image8.webp)

编译会提示 crc 部分重定义，解决方法是引入 `CRC.h`，使用此文件的 crc 校验表，并将其修改成

![crc外部声明](/document/assets/rmui-pure-image9.webp)

```
extern const unsigned char CRC8_TAB[256];
extern const uint16_t wCRC_Table[256];
```

然后是替换 `ui_self_id`，将其替换成裁判系统返回的机器人 id，红蓝方 id 不同，这边是替换成了 `Referee_System_Info.robot_status.robot_id`

![工程文件树](/document/assets/rmui-pure-image10.webp)

修改 `ui_g.c` 里的数字和文字可以实现映射和修改

![ui_g.c相关代码](/document/assets/rmui-pure-image11.webp)

`ui_types.h` 涉及到结构体对齐很重要

目前测试是可以正常使用的

![ui_types.h对齐代码](/document/assets/rmui-pure-image12.webp)

然后就是新建一个 freertos 任务来实现 ui 初始化和更新，可以通过网页的 simulate 功能进行测试和验证

![Simulate调试下拉菜单](/document/assets/rmui-pure-image13.webp)

需要将连接裁判系统的 3pin 串口直接通过 usb 转串口连接到电脑上，可以用达妙的 usb 转 can 模块，线序和电管相同。 可以先用 vofa+看一下是否接收到数据

![VOFA+串口接收数据界面](/document/assets/rmui-pure-image14.webp)

连接后点 start 即可出现绘制的 ui

![仿真运行UI渲染效果](/document/assets/rmui-pure-image15.webp)

Debug_log 会显示当前的问题

![Debug Log日志](/document/assets/rmui-pure-image16.webp)

目前测试导致一直初始化，有重复绘制。 Rx History 可以点开蓝色的 A5 来看发送的信息有没有对齐

![Rx History报文解析弹窗](/document/assets/rmui-pure-image17.webp)

以上移植测试就完成了，实际测试的时候需要搭建服务器进行测试才会显示 ui 界面，利用设计器可以更简便和更快的测试 ui 的绘制。

![最终界面效果](/document/assets/rmui-pure-image18.webp)