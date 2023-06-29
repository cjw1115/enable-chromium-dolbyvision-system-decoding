# Enable chromium dolbyvision system decoding

此项目目的是在 Chrome 浏览器里面调用系统自带的 Dolby Vision 解码器去解码杜比视界的内容。

Bilibili 应该是目前国内最大的支持杜比视界的UGC平台，

## 先决条件
#### Windows 10/11
#### HEVC(H265) 解码器
可以参考这篇专栏安装 HEVC 解码器：[Windows 10/11 自带播放器如何播放 HEVC(H265) 编码视频](https://www.bilibili.com/read/cv11274235)
> 项目 [enable-chromium-hevc-hardware-decoding](https://github.com/StaZhu/enable-chromium-hevc-hardware-decoding) 给 Chrome 添加了 HEVC 硬解，但是这种调用方式没法调用杜比视界解码器，所以无法解码杜比视界 Profile5 等。

#### 杜比视界解码器
通过这个链接去应用商店安装 [Dolby Vision Extensions](https://apps.microsoft.com/store/detail/dolby-vision-extensions/9PLTG1LWPHLF)
> 完整的杜比视界支持需要：符合杜比视界规格的显示器（笔记本显示器面板）、杜比视界授权、杜比视界解码器等。如果你的电脑出厂时没有预装杜比视界，那么只安装这个杜比视界解码器只能确保基本的色彩映射。
