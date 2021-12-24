# Doppler Simulator

A demonstration of Doppler's Effect, with pre-generated sound and real-time-generated video.

Supports customization with `config.json`. But the source code was quite a mess so it will not be uploaded.

The whole thing took me 8h of work during Aug 15-18 in 2021.

# Sample Video

The two videos below may take a while to load. Turn on your speaker to hear the sound.

![pedestrian's view](./straight.mp4)

![chaos](./cycle.mp4)

# Doppler Simulator: Watch & listen. / 多普勒效应模拟器。

【工作时间】8h / 4d。

V1：我站在人行道，救护车以10m/s速度驶过。
V2：动 感 漂 移。

## 涉及到的技术：

Node.js + Electron + pixi.js 总体逻辑调度+动画绘制。 https://github.com/LAGameStudio/pixitron
C++ with github/AudioFile 操作WAV格式音频文件。 https://github.com/adamstark/AudioFile

## 一些细节：

- 核心计算不基于“速度改变频率”，而是基于“距离改变传播时间”。简单的物理模型就可以展现丰富。
- 实现了“靠近声源音量变大”：认为声波振幅与距离成反比，因为网上说声波能量与振幅平方成正比。（如果有错请告诉我！）
- 人高2m，车长6m，绘出的图是按比例的，xy轴方向缩放比一致。
- 简单演算知车速达到 0.056倍音速 = 20m/s 就可以产生一个半音的频率变化，V1中的频率变化要稍小不过完全可感。
- 根据国标 GB8108-2014 指出的救护车警报声800/1000Hz 1/1s，取正弦声波，导出结果已经十分接近实际。

## 存在的问题：

- 架构混乱，pixi的代码组织、js与C++的协作非常原始。
- 扩展性不好，中途预留了接口，但是做出成品视频之后不想干了（瘫）。
- 跨平台性未知，不指望给高中物理老师当教案了。有兴趣把我视频拷走吧。
- 正弦单音听起来很怪，播放起来有奇怪的“喳喳”声。

## 过去和未来：

- 偶然间想到的点子，以作练手项目的动机实现了。没啥技术含量，主要是熟悉一些概念。
- 后来回忆起看过一个项目“当光速很慢时视觉会如何”的演示作品 http://gamelab.mit.edu/games/a-slower-speed-of-light/ ，可我既不会相对论也不会3D渲染。




