# Enable chromium dolbyvision system decoding

此项目目的是在 Chrome 浏览器里面调用系统自带的 Dolby Vision 解码器去解码杜比视界的内容。

# 怎么在 Windows 10/11 上看B站的杜比视界
## 先决条件
#### Windows 10/11
#### HEVC(H265) 解码器
可以参考这篇专栏安装 HEVC 解码器：[Windows 10/11 自带播放器如何播放 HEVC(H265) 编码视频](https://www.bilibili.com/read/cv11274235)
> 项目 [enable-chromium-hevc-hardware-decoding](https://github.com/StaZhu/enable-chromium-hevc-hardware-decoding) 给 Chrome 添加了 HEVC 硬解，但是这种调用方式没法调用杜比视界解码器，所以无法解码杜比视界 Profile5 等。

#### 杜比视界解码器
通过这个链接去应用商店安装 [Dolby Vision Extensions](https://apps.microsoft.com/store/detail/dolby-vision-extensions/9PLTG1LWPHLF)
> 完整的杜比视界支持需要：符合杜比视界规格的显示器（笔记本显示器面板）、杜比视界授权、杜比视界解码器等。如果你的电脑出厂时没有预装杜比视界，那么只安装这个杜比视界解码器只能确保基本的色彩映射。

## 步骤

#### 下载安装
在 [Release](https://github.com/cjw1115/enable-chromium-dolbyvision-system-decoding/releases) 中下载 chromium_116.0.5826.0_clear_dolby_vision_atmos.exe并安装（此版本为开发者版本，不会影响你已经安装的正式版本）

#### 用参数 PlatformEncryptedDolbyVision,AllowClearDolbyVisionInMseWhenPlatformEncryptedDvEnabled 启动 chrome
1. 找到 chromium 安装目录 `C:\Users\{你的用户名}\AppData\Local\Chromium\Application`
2. 在此目录下通过下面命令行运行 chrome:（如果你熟悉windows的话，可以直接把下面的参数加到桌面快捷方式）
    ```
    .\chrome.exe --enable-features=PlatformEncryptedDolbyVision,AllowClearDolbyVisionInMseWhenPlatformEncryptedDvEnabled,HardwareSecureDecryption:force_support_clear_lead/true
    ```
3. chrome 启动后在地址栏输入 `chrome://flags/`, 然后找到 `MediaFoundation for Clear` 并且其设置为 enabled（启用），然后关闭浏览器，用第2步的命令重新启动chrome。（修改后它会提示你重启，但不要用他的那个重启按钮，因为它重启后不会携带第2步的参数）
#### 安装 User-Agnet 管理器
1. 打开谷歌Web应用商店下载安装[User-Agent Switcher and Manager](https://chrome.google.com/webstore/detail/user-agent-switcher-and-m/bhchdcejhohfmigjafbampogmaanbfkg)
   > 如果你能上github，代表你可以下载 打开谷歌应用商店，如果不行，我也放在 [Release](https://github.com/cjw1115/enable-chromium-dolbyvision-system-decoding/releases) 里面了，找 `user-agent-switcher_v0.4.9.crx` 
3. 在 chrome 扩展中找到 User-Agent Switcher, 然后依次选择 Safari, MacOS, 在列表中选择最高的一个，最后点击 应用（所有窗口）
> 因为目前B站只给 Safari 提供杜比视界和杜比全景声的流，所以需要修改 chrome 的 user-agent 为 Safari

#### 打开B站，体验杜比视界

# 怎么在 Windows 10/11 上听杜比全景声？
按照 `怎么在 Windows 10/11 上看B站的杜比视界` 中的
