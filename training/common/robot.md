---
title: 机器人系统
description: 
published: true
date: 2026-09-25T09:47:01.032Z
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

- 机械：设计机器人机械结构
- 硬件：设计机器人上的电路模块（超级电容、无线充电、电池缓启动、主控模块）
- 电控：主要在单片机做感知、控制（实时控制）
- 算法：在工控机做感知、控制（视觉识别，slam和自主导航，机械臂轨迹规划）

## Reference

感谢 pnx 战队的资料：[PNX 培训中心 | PNX Robotics](https://hkustgz-robomaster-pnx.github.io/training/?doc=Zuw7dRErhoBzuWxvo3tcNLNknqg#section-doxcnVkldk2DBfhH42pzpfikG8d)
