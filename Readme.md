# 在 Chrome 浏览器里体验杜比视界
Chrome 122 版本（至少）已经具有播放杜比视界的能力，只是默认处于关闭的状态，通过这篇文档可以了解如何开启并体验杜比视界。
> 本文测试版本 Chrome 122.0.6261.70 (Official Build) (64-bit)

## 先决条件
#### HEVC(H265) 解码器
可以参考这篇专栏安装 HEVC 解码器：[Windows 10/11 自带播放器如何播放 HEVC(H265) 编码视频](https://www.bilibili.com/read/cv11274235)

> 项目 [enable-chromium-hevc-hardware-decoding](https://github.com/StaZhu/enable-chromium-hevc-hardware-decoding) 实现了 Chrome 硬解 HEVC，但是这种调用方式不能调用系统层面的杜比视界解码器，所以无法解码杜比视界 profile5 等。

#### 杜比视界解码器
使用此链接在 Windows 应用商店安装 [杜比视界扩展](https://apps.microsoft.com/store/detail/dolby-vision-extensions/9PLTG1LWPHLF)
> 完整的杜比视界支持需要：符合杜比视界规格的显示器（笔记本显示器面板）、杜比视界授权、杜比视界解码器等。如果你的电脑出厂时没有预装杜比视界，那么只安装这个杜比视界解码器只能确保基本的色彩映射。

## 在Chrome里启用杜比视界
1. 找到 Chrome 安装目录, 默认一般是`C:\Program Files\Google\Chrome\Application`
2. 在此目录下通过下面命令行运行 chrome:（如果你熟悉windows的话，可以直接把下面的参数加到桌面快捷方式）
    ```
    .\chrome.exe --enable-features=PlatformEncryptedDolbyVision,AllowClearDolbyVisionInMseWhenPlatformEncryptedDvEnabled,HardwareSecureDecryption:force_support_clear_lead/true
    ```
3. chrome 启动后在地址栏输入 `chrome://flags/`, 然后找到 `MediaFoundation for Clear` 并且其设置为 enabled（启用），然后关闭浏览器，用第2步的命令重新启动chrome。（修改后它会提示你重启，但不要用他的那个重启按钮，因为它重启后不会携带第2步的参数）
4. 去提供杜比视界的流媒体平台体验（比如Bilibili)

## 测试片源
1. [杜比视界Profile 8] [【杜比视界·全景声】00后摄影师带你走近治愈系「秘境桂林」](https://www.bilibili.com/video/BV1zv411w7Aj)
2. [杜比视界Profile 5] [穿越5000公里，我们拍到了抹香鲸｜4K杜比视界·杜比全景声](https://www.bilibili.com/video/BV1QX4y1i7B1)
   > 注意，目前B站播放 Profile5 的杜比视界存在问题，会显示切换失败。
