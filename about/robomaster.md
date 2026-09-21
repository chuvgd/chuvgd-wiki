---
title: 关于 RoboMaster 比赛
description: 
published: true
date: 2026-09-21T06:44:56.082Z
tags: 
editor: markdown
dateCreated: 2026-09-21T06:39:16.775Z
---

# 关于 RoboMaster 比赛

<!--
在下面我调用了一个自制的小工具，他的js代码在 左上角-页面-脚本 中，usage如下：
<span class="show-anniversary" data-begin="2014"></span>
他会返回现在到 2014 年隔了多少年
-->
<script>
window.boot.register('page-ready', () => {
  document.querySelectorAll('.show-anniversary').forEach(el => {
    el.textContent = new Date().getFullYear() - el.dataset.begin;
  });
});
</script>

RoboMaster 是由 DJI 大疆举办的全国机器人大赛，至今已有<span class="show-anniversary" data-begin="2014"></span>年了
