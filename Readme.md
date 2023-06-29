# 在 Chrome 浏览器里启用系统级杜比视界解码器
此项目旨在 Chrome 浏览器里播放杜比视界内容时，调用系统自带的杜比视界解码器。

> 杜比视界 等价于 Dolby Vision, 本文统一使用 `杜比视界`

# 怎么在 Windows 10/11 上看B站的杜比视界

## 先决条件

### Windows 10/11

### HEVC(H265) 解码器
可以参考这篇专栏安装 HEVC 解码器：[Windows 10/11 自带播放器如何播放 HEVC(H265) 编码视频](https://www.bilibili.com/read/cv11274235)

> 项目 [enable-chromium-hevc-hardware-decoding](https://github.com/StaZhu/enable-chromium-hevc-hardware-decoding) 实现了 Chrome 硬解 HEVC，但是这种调用方式不能调用系统层面的杜比视界解码器，所以无法解码杜比视界 profile5 等。

### 杜比视界解码器
使用此链接在 Windows 应用商店安装 [杜比视界扩展](https://apps.microsoft.com/store/detail/dolby-vision-extensions/9PLTG1LWPHLF)
> 完整的杜比视界支持需要：符合杜比视界规格的显示器（笔记本显示器面板）、杜比视界授权、杜比视界解码器等。如果你的电脑出厂时没有预装杜比视界，那么只安装这个杜比视界解码器只能确保基本的色彩映射。

## 安装步骤

### 下载安装
在 [Release](https://github.com/cjw1115/enable-chromium-dolbyvision-system-decoding/releases/tag/clear_dolby_vision) 中下载 chromium_116.0.5826.0_clear_dolby_vision_atmos.exe 并安装。
> 此版本为开发者版本，不会影响你已经安装的正式版本。

### 定制化参数启动 Chrome
1. 找到 chromium 安装目录 `C:\Users\{你的用户名}\AppData\Local\Chromium\Application`
2. 在此目录下通过下面命令行运行 chrome:（如果你熟悉windows的话，可以直接把下面的参数加到桌面快捷方式）
    ```
    .\chrome.exe --enable-features=PlatformEncryptedDolbyVision,AllowClearDolbyVisionInMseWhenPlatformEncryptedDvEnabled,HardwareSecureDecryption:force_support_clear_lead/true
    ```
3. chrome 启动后在地址栏输入 `chrome://flags/`, 然后找到 `MediaFoundation for Clear` 并且其设置为 enabled（启用），然后关闭浏览器，用第2步的命令重新启动chrome。（修改后它会提示你重启，但不要用他的那个重启按钮，因为它重启后不会携带第2步的参数）

### 安装 User-Agent 管理器
1. 打开谷歌 Web 应用商店下载安装 [User-Agent Switcher and Manager](https://chrome.google.com/webstore/detail/user-agent-switcher-and-m/bhchdcejhohfmigjafbampogmaanbfkg)
   > 如果你能上github，大概率你也可以打开谷歌应用商店，如果不行，我已经把它下载好放到了 [Release](https://github.com/cjw1115/enable-chromium-dolbyvision-system-decoding/releases/tag/clear_dolby_vision) 里面，找 `user-agent-switcher_v0.4.9.crx` 即可。 
3. 在 Chrome 扩展中找到 User-Agent Switcher, 然后依次选择 Safari, MacOS, 在列表中挑选版本号最高的一个，最后点击 应用(所有窗口)

> 因为目前B站只给 Safari 提供杜比视界和杜比全景声的流，所以需要修改 chrome 的 user-agent 为 Safari。

### 打开B站，体验杜比视界
可以用这个视频测试下，它的视频是 `dvh1.05.06`, 音频是 `ec-3`

[穿越5000公里，我们拍到了抹香鲸｜4K杜比视界·杜比全景声](https://www.bilibili.com/video/BV1QX4y1i7B1/)


# 怎么在 Windows 10/11 上听杜比全景声？
1. 同样完成 `怎么在 Windows 10/11 上看B站的杜比视界` 中的 `安装步骤`。
2. 安装 Dolby Access, 如果电脑不自带杜比全景声的授权，还需要去Dolby Access里面内购杜比全景声授权
    > Dolby Access [传送门 --->](https://www.microsoft.com/store/productId/9N0866FS04W8)


