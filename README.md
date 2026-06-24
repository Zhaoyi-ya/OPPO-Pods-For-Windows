# OPPO Pods For Windows

[中文](#中文) | [English](#english)

---

## English

Windows desktop OPPO earbuds Bluetooth controller, supporting Enco Free4 / X3 / Air5 / Air2 Pro series.

> **Only OPPO Enco Free4 has been fully tested — all features work correctly.** Other models' adaptation logic is ported from open-source reference projects and has not been verified on real devices. Full functionality is not guaranteed.

Built on the OPPO proprietary RFCOMM protocol reverse-engineered by [Leaf-lsgtky/OppoPods](https://github.com/Leaf-lsgtky/OppoPods), with feature matrix reference from [1812z/OppoPods](https://github.com/1812z/OppoPods).

### Features

- Battery display (L / R / Case, with charging status ⚡)
- Wear detection (in-case / worn / removed)
- ANC control (Off / Noise Cancelling / Adaptive / Transparency)
- ANC sub-modes: Smart / Light / Medium / Deep
- Spatial sound toggle (Free4 / Air5)
- Spatial audio 3-mode: Off / Fixed / Head Tracking (X3)
- Game mode (Standard / Compatible)
- Dual-device connection toggle
- Master EQ (5 presets, model-adaptive)
- System tray: left-click toggle window, right-click function menu
- Tray hover shows real-time battery
- Win11-style battery toast on connection
- Minimize to tray / Auto-start with Windows
- Auto-reconnect on disconnection
- Follows system light/dark theme + manual override

### Requirements

- Windows 10 / 11
- .NET 9.0 Desktop Runtime ([Download](https://dotnet.microsoft.com/en-us/download/dotnet/9.0))
- Bluetooth adapter + paired OPPO earbuds

### Quick Start

**Run directly:**

Download `OppoPodsWPF.exe` from [Releases](https://github.com/Zhaoyi-ya/OPPO-Pods-For-Windows/releases) and double-click.

**Build from source:**

```bash
git clone https://github.com/Zhaoyi-ya/OPPO-Pods-For-Windows.git
cd OPPO-Pods-For-Windows
dotnet run
```

**Publish single-file exe:**

```bash
dotnet publish -c Release -r win-x64 -o publish
```

### Device Support

| Model      | ANC | Adaptive | Spatial FX | 3D Audio | Dual Device | Master EQ |
|:-----------|:---:|:---:|:---:|:---:|:---:|:---:|
| Enco Free4 | ✅ | ✅ | ✅ | —  | ✅ | 5 presets |
| Enco X3    | ✅ | —  | —  | ✅ | ✅ | 5 presets |
| Enco Air5  | ✅ | —  | ✅ | —  | —  | 5 presets |
| Enco Air2 Pro | ✅ | —  | —  | —  | —  | 5 presets |

Other Bluetooth devices whose name contains "OPPO" will auto-connect with a generic feature set.

### Project Structure

```
OPPO-Pods-For-Windows/
├── OppoPodsWPF.csproj    # .NET 9 WPF + WinForms project
├── App.xaml/.cs          # Entry point & theme
├── MainWindow.xaml/.cs   # Main UI + tray + settings
├── ToastWindow.xaml/.cs  # Connection battery toast
├── OppoProtocol.cs       # OPPO RFCOMM protocol definitions
├── RfcommService.cs      # Winsock2 Bluetooth connection & polling
├── DeviceCapabilities.cs # Model detection & feature matrix
├── PodState.cs           # State data model
└── Assets/               # Icons & images
```

### Acknowledgements

- [Leaf-lsgtky/OppoPods](https://github.com/Leaf-lsgtky/OppoPods) — OPPO proprietary protocol reverse engineering
- [1812z/OppoPods](https://github.com/1812z/OppoPods) — Feature implementation reference
- [lepoco/wpfui](https://github.com/lepoco/wpfui) — Windows 11 Fluent Design UI framework

### License

GPL-3.0

---

## 中文

Windows 桌面端 OPPO 耳机蓝牙控制器，支持 Enco Free4 / X3 / Air5 / Air2 Pro 系列。

> **当前仅完整测试过 OPPO Enco Free4，功能均正常。** 其他机型适配逻辑移植自开源参考项目，未做真机验证，不保证全部功能可用。

基于 [Leaf-lsgtky/OppoPods](https://github.com/Leaf-lsgtky/OppoPods) 逆向的 OPPO 私有 RFCOMM 协议，参考 [1812z/OppoPods](https://github.com/1812z/OppoPods) 的功能矩阵实现。

### 功能

- 电量显示（左耳 / 右耳 / 充电盒 + 充电状态 ⚡）
- 佩戴检测（入盒 / 佩戴 / 摘下）
- 降噪控制（关闭 / 降噪 / 自适应 / 通透）
- 降噪子模式：智能 / 轻度 / 中度 / 深度
- 空间音效开关（Free4 / Air5）
- 空间音频三模式：关闭 / 固定 / 头部追踪（X3）
- 游戏模式（标准 / 兼容两种实现）
- 双设备连接开关
- 大师调音 EQ（5 种预设，按型号适配）
- 系统托盘常驻，左键切换显隐，右键功能菜单
- 托盘悬浮提示实时电量
- 连接时弹出 Win11 风格电量提示
- 关闭到托盘 / 开机自启
- 断连自动重连
- 跟随系统深浅色主题 + 手动切换

### 系统要求

- Windows 10 / 11
- .NET 9.0 Desktop Runtime（[下载](https://dotnet.microsoft.com/zh-cn/download/dotnet/9.0)）
- 蓝牙适配器 + 已配对的 OPPO 耳机

### 快速开始

**直接运行：**

下载 [Releases](https://github.com/Zhaoyi-ya/OPPO-Pods-For-Windows/releases) 中的 `OppoPodsWPF.exe`，双击运行。

**从源码编译：**

```bash
git clone https://github.com/Zhaoyi-ya/OPPO-Pods-For-Windows.git
cd OPPO-Pods-For-Windows
dotnet run
```

**发布单文件 exe：**

```bash
dotnet publish -c Release -r win-x64 -o publish
```

### 设备支持

| 型号 | 降噪 | 自适应 | 空间音效 | 空间音频 | 双设备 | 大师调音 |
|:---|:---:|:---:|:---:|:---:|:---:|:---:|
| Enco Free4 | ✅ | ✅ | ✅ | — | ✅ | 5 种 |
| Enco X3 | ✅ | — | — | ✅ | ✅ | 5 种 |
| Enco Air5 | ✅ | — | ✅ | — | — | 5 种 |
| Enco Air2 Pro | ✅ | — | — | — | — | 5 种 |

其他名称包含 "OPPO" 的蓝牙设备可自动连接，使用通用功能集。

### 项目结构

```
OPPO-Pods-For-Windows/
├── OppoPodsWPF.csproj    # .NET 9 WPF + WinForms 项目
├── App.xaml/.cs          # 应用入口，主题设置
├── MainWindow.xaml/.cs   # 主界面 + 托盘 + 设置
├── ToastWindow.xaml/.cs  # 连接电量提示弹窗
├── OppoProtocol.cs       # OPPO RFCOMM 协议定义
├── RfcommService.cs      # Winsock2 蓝牙连接与轮询
├── DeviceCapabilities.cs # 设备型号识别与功能矩阵
├── PodState.cs           # 状态数据模型
└── Assets/               # 图标 & 图片素材
```

### 致谢

- [Leaf-lsgtky/OppoPods](https://github.com/Leaf-lsgtky/OppoPods) — OPPO 耳机私有协议逆向
- [1812z/OppoPods](https://github.com/1812z/OppoPods) — 功能实现参考
- [lepoco/wpfui](https://github.com/lepoco/wpfui) — Windows 11 Fluent Design UI 框架

### 开源协议

GPL-3.0
