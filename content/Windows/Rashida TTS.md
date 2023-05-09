---
title: " Rashida TTS"
description: "基于Python第三方库pytts3的文字转语音工具"
tags: [Win,TTS,Python]
categories: "电脑软件"
date: 2023-05-09T20:24:05+09:00
featured_image: "https://rashida.cab:6901/uploads/2023/05/09/645953c6e69cf.jpg"

---



# Rashida TTS

## 欢迎使用

> 注意：TXT编码格式需为UTF8

基于PYTTSX3的文本转语音工具
UI为 tkinter
测试 43000 字符没有问题

![界面展示](https://rashida.cab:6901/uploads/2023/05/09/645a2e7a734a6.png)

B站视频展示<https://www.bilibili.com/video/av442548077/>



## 常见问题

### .py 文件无法正常运行

一般是由于缺少运行库，可以尝试使用 `pip install -r requirements.txt` 解决

### Linux 系统缺少 espeak

ArchLinux 以及基于此系统的发行版 Linux 用户可以通过 yay 安装 AUR 包 `espeak` 解决这个问题

Ubuntu 系统可以通过安装 `espeak` 解决

如果尚未解决，可以尝试重新安装 `pyttsx3` 模块