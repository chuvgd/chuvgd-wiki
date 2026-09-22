---
title: 技术文档
description: 
published: true
date: 2026-09-22T07:31:45.302Z
tags: 
editor: markdown
dateCreated: 2026-09-20T14:08:08.124Z
---

# 这里是技术文档！！！

在 `/document/` 文件夹下，可以放置所有你们的技术文章，包括但不限于：

1. 队内/对外开源
2. 经验分享
3. 学习指北/指南

希望大家积极发表文章，积累经验，为 VGD 传承和协作付出贡献！

## 创建新文章

你可以在 `/document/` 文件夹下创建命名为 `文章标题-你的名字` 的页面（约定）。

下面是一个简单的创建工具：

<!-- 工具开始 -->

<div class="doc-create-form">
  <div class="doc-form-row">
    <label for="doc-title">文章名</label>
    <input type="text" id="doc-title" placeholder="请输入文章名" autocomplete="off">
    <div class="doc-form-hint" id="doc-title-hint"></div>
  </div>

  <div class="doc-form-row">
    <label for="doc-name">名字</label>
    <input type="text" id="doc-name" placeholder="请输入你的名字 / 昵称" autocomplete="off">
    <div class="doc-form-hint" id="doc-name-hint"></div>
  </div>

  <div class="doc-form-note">
    命名规范：只能使用字母、数字、汉字、<code>-</code>、<code>_</code> 符号；<strong>区分大小写</strong>；建议尽量使用英文和数字，使用汉字会收到警告；如果跳转后进入编辑页面，说明该名字已被占用。
  </div>

  <div class="doc-form-actions">
    <button type="button" id="doc-confirm">确定</button>
    <button type="button" id="doc-reset">清空</button>
  </div>
</div>

<!-- 工具结束 -->

## 归档

<div id="pageTree">Loading pages ...</div>
