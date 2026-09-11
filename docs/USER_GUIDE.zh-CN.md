# Windows Fader Bridge for Mackie Control 使用手册

[English](USER_GUIDE.en.md) ・ [日本語](USER_GUIDE.ja.md) ・ [返回主页](../README.md)

## 它能做什么

本程序让 Mackie Control / MCU 模式的 MIDI 控制器直接控制 Windows 音量混音器。推子、旋钮、按键、灯光、峰值表和播放信息都由程序与 Windows 实时同步。

它不是某一款设备的专用驱动。iCON P1-Nano 已经过实机验证；其他 MCU 控制器的基本协议相同，但额外按键、屏幕和灯光可能不同。

## 使用前准备

- Windows 11 64 位。
- 一台带 Mackie Control / MCU 模式的 MIDI 控制器。
- 如设备需要专用 USB 驱动，请先按厂商说明安装。

本版本不需要 EuControl、Avid 软件、虚拟 MIDI 线或编译工具。

## 安装

1. 在 [Releases](https://github.com/lindelea/windows-fader-bridge-mackie/releases/latest) 下载名称以 `Setup-x64.exe` 结尾的安装程序。
2. 退出以前手动运行的便携版，双击安装程序并完成安装。
3. 从开始菜单打开 **Windows Fader Bridge for Mackie Control**。

本项目暂未购买 Windows 代码签名证书，因此 Windows 可能显示“未知发布者”。请只从本仓库下载，并可用发布页中的 SHA-256 校验值核对文件。

## 第一次连接

1. 把控制器切换到 **Mackie Control / MCU** 模式，不要选择 HUI。
2. 打开程序的 **设备** 页面，点击“添加设备”或选择已有设备。
3. 选择 MIDI 输入和输出。输入是控制器发给电脑的端口，输出是电脑反馈给控制器的端口。
4. 普通设备选择“通用 Mackie Control”；P1-Nano 可选择专用配置。
5. 保留“触摸保护”，保存设备。默认会自动连接；手动模式下点击“连接设备”。

不要让 Cubase、其他 DAW 和本程序同时占用同一对 MIDI 端口。P1-Nano 可以把 Cubase 与 Windows 控制放在不同 DAW 层；Windows 层使用你为本程序选定的独立端口。

## 默认操作

- 通道推子：对应 Windows 应用或音频设备的音量。
- Master 推子：Windows 默认输出音量。
- 旋钮 1：当前通道音量。
- 旋钮 2：当前通道声像/平衡；按下回到中心。
- Mute / Solo：切换并显示当前通道的真实状态。
- Bank / Channel：在在线通道间翻页或选择。
- 峰值表：显示实时音频电平。
- 播放控制：控制支持 Windows 媒体会话的播放器；可显示曲名、艺术家和时间。

应用关闭后会从在线列表移除，新出现的应用自动加入。正在触摸推子时不会重排目标。

## 自定义按键和旋钮

在 **按键分配**、**旋钮分配**、**Jog 与方向** 页面选择实体控件，再从命令列表中分配 Windows、媒体、窗口或音频功能。编辑当前设备时，识别到的按键只用于学习，不会同时执行命令。

旋钮 3–8 的左转、右转、按下可以分别分配。普通 Jog、Move 与 Zoom 也分别设置；Navi / Focus 保留设备原本语义。

P1-Nano 用户可在设备页使用 Windows 80 键预设功能。请先用 iMAP 备份自己的配置；该功能只修改指定的触屏位置，不会自动写入其他 DAW 层。其他设备使用按键学习进行自定义。

## 设置与快捷键

程序支持中英文界面、关闭到托盘、随 Windows 启动和全局调出快捷键。默认快捷键为 `Ctrl+Alt+Shift+M`，可以重新录制。关闭窗口通常只是隐藏；完全退出或重新启动请使用托盘菜单。

每台控制器保存独立 MIDI 端口、连接方式和分配。最多可配置 16 台独立 MCU 主控制器，但同一 MIDI 端口不能被两台配置重复使用。

## 常见问题

**找不到 MIDI 端口**：确认设备已开机且 Windows 能看到它，关闭可能占用该端口的 DAW，然后在程序中重新选择。

**推子能动但没有电机/灯光反馈**：检查输出端口是否选对，并确认没有选中 iMAP 或维护端口。

**Master 或左右切换无效**：确认设备确实处于 MCU 模式且选择了匹配的输入/输出。P1-Nano 请使用对应 DAW 层的同编号端口。

**卸载**：在 Windows“设置 → 应用 → 已安装的应用”中卸载。设备分配会保留，方便以后重装。

## 报告问题

请前往 [GitHub Issues](https://github.com/lindelea/windows-fader-bridge-mackie/issues)，写明控制器型号、固件、所选 MIDI 输入/输出、操作步骤和结果。日志可能包含应用与设备名称，上传前请检查。
