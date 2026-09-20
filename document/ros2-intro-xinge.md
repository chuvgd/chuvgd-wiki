---
title: ROS2入门学习指南
description: ROS2入门指南，包括官方文档和网课视频推荐
published: true
date: 2026-09-20T14:38:12.527Z
tags: ros2
editor: markdown
dateCreated: 2026-09-20T14:38:12.527Z
---

# ROS2入门学习指南

本指南目的是让算法组组员更好学习ros2以快速适应队伍工程，里面包含了笔者个人学习的相关路线和资源，不一定正确，但是一定是非常适合刚入队的读者进行学习（默认有语言基础，且基本能熟练运用cpp11一些新特性——匿名函数，智能指针等）

## 一.基础篇

首先我们要知道ros2有不同的发行版本，目前在robomaster中主流的版本是ubuntu22.04+ros2 humble，一些头部强队更推荐使用ubuntu24.04+ros2 jazzy，笔者建议学习阶段用ubuntu22.04+ros2 jazzy进行学习，相关生态已经趋于成熟和稳定

![ros2 humble官方图标](https://ros2docs.robook.org/humble/_static/humble-small.png)

对于初学者，我推荐的是鱼香ros的b站网课视频，以下是链接：

[《ROS 2机器人开发从入门到实践》课程介绍](https://www.bilibili.com/video/BV1GW42197Ck/?share_source=copy_web&vd_source=53f60017d07eb4cbe3c0f6733b050a0a)

```
要求学习到：第六章仿真结束
基本学习目标：对ros2这个系统有基础认知，初步理解四大通信的机制，明白ros2一些常用工具——rqt，rviz，rosbag2等，对仿真有一定认识
```

## 二.进阶篇

想要更好地理解ros2这个系统，不仅仅是看网课这么简单，笔者认为需要去真正地复刻一个项目或者跟着项目进行进一步的学习，这里推荐的项目是**基础篇**里面的第九章，笔者认为这个是一个很好的实践项目，进行实践之前，笔者建议还是要学习一下有关的导航知识——即第七章和第八章，由于目前队内只有导航框架是基于ros2 nav2，自瞄已经去ros2化，所以学习第七章和第八章也能对想要接触无人车导航的同学提供一个帮助和入门（网课里面介绍的就是ros2 nav2这个框架），在这个过程中你需要开始慢慢理解代码背后的知识，比如说生命周期管理，还有ros2背后的通信机制的原理——DDS，这些我更推荐用官方文档进行学习，ros2的官方文档写的是非常规整和详细，适用于在实践过程中发现问题进行反思时**深入从头学习**

```
这个过程我认为是在一个项目的驱动下的自上而下，然后发现往下不了之后需要重新在理论上自下而上，这个是非常非常重要的，也就是脚踏实地学理论，勤勤恳恳做项目
```

这里是官方文档的链接：

[ros2 humble官方英文文档](https://docs.ros.org/en/humble/Tutorials/Beginner-CLI-Tools/Configuring-ROS2-Environment.html)

[ros2 humble官方文档中文翻译（但是比起原版不全）](http://dev.ros2.fishros.com/doc/Tutorials/Configuring-ROS2-Environment.html)

### 三.补充

这里推荐一个公众号：智驾芯视野

**里面有对ros2相关机制的讲解**


看到这篇文档的同学，都可以加笔者qq：2237200336来和笔者交流相关学习心得，笔者能力有限，甚至连ros2的基础都没有完全吃透，文档有所问题，请大家直接进行指正和包涵

