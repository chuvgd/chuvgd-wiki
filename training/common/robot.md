---
title: 机器人系统
description: 
published: true
date: 2026-09-21T13:23:37.983Z
tags: 
editor: markdown
dateCreated: 2026-09-21T13:14:37.341Z
---

# 机器人的构成

![](https://hkustgz-robomaster-pnx.github.io/feishu-images/DiqFwCWFshRLzwbOGUecYmLbnAb-board.png)

```mermaid
graph LR
    subgraph hardware[实体]
        gyro[陀螺仪]
        encoder[编码器]
        radar[雷达]
        stm32[stm32]
        ipc[工控机]
        motor[电机]
    end

    subgraph component[功能]
        sensor[传感器]
        controller[控制器]
        actuator[执行器]
    end

    subgraph function[算法]
        perception[感知/观测器]
        control[控制算法]
    end

    gyro --> sensor
    encoder --> sensor
    radar --> sensor
    
    stm32 --- controller
    ipc --- controller
    
    sensor --> perception
    perception --> controller
    controller --> control
    control --> actuator
    motor --> actuator
```

做一个机器人，就是在感知-控制-执行。其中：

- 机械：机器人平台的结构
- 硬件：机器人平台的电路模块
- 电控：感知、控制（主要在嵌入式运算）
- 算法：感知、控制（在工控机运算）（aka. 小电脑、上位机）

## Reference

感谢 pnx 战队的资料：[PNX 培训中心 | PNX Robotics](https://hkustgz-robomaster-pnx.github.io/training/?doc=Zuw7dRErhoBzuWxvo3tcNLNknqg#section-doxcnVkldk2DBfhH42pzpfikG8d)
