---
title: 直播探索
author: "@h1u2i3"
---

# 前提

## Webinar2you Demo
1. 类似直播的需求(音视频+聊天)
2. 需要共享桌面
3. 直播视频存储在云端
4. 支持全平台浏览器

## Prototype

![Preview](images/webinar.png){ width=70% }

# 直播简介

## 简单架构

![简单直播流程](images/simple_progress.png){ width=50% }

## 复杂架构

![直播流程](images/progress.jpg){ width=80% }

# 详细介绍

## 数据采集

1. Obs(https://obsproject.com/)
2. StreamApi(getUserMedia)
...

## getUserMedia

![Support](images/support.png){ width=80% }

## 推流(数据传输)

1. Rtmp
2. HLS
3. WebRtc

## 拉流(播放)

1. Rtmp(Flash插件, 不支持 Html5, rtmp://)
2. HLS(http://...simple.m3u8)
3. Http-flv
4. WebRtc

# 服务器

## Rtmp(Flash) Gateway

1. Red5
...

## WebRtc GateWay

1. janus-gateway
2. kurento

## janus-gateway

- janus-protocol (协议)
- RubbitMQ (队列工具)
- MQTT
- 支持录制视频
- Javascript SDK

## kurento

- kurento-protocal (协议)
- 支持录制视频
- Gstream(filter/hub)
- Javascript SDK

# 技术选择

## 总览

![结构图](images/structure.png){ width=70% }

## 数据采集

### Electron
1. chrome 内核 & kurento-client-js
2. getUserMedia/StreamApi

## 推流
1. kurento-client
2. Webrtc

## Gateway
1. Kurento 录制视频/转发WebRtc流
2. WebRtc 转 Rtmp (解决跨平台问题)

## 播放器
### Video.js
1. WebRtc
2. Rtmp/HLS (nginx-rtmp-module)

# Demo
