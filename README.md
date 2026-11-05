# ConcertPlay (CPD) — 发布仓库

ConcertPlay 是一个**本地优先的跨平台音乐播放与下载客户端**，支持 Linux / Windows / Android。
本仓库仅存放各平台构建产物，不存放源代码。

- **应用名**：ConcertPlay
- **简称**：CPD
- **开发者**：ByRUDAN
- **当前版本**：`0.1.19`（`0.1.19:01-BS19`）
- **构建时间**：2026-11-05

---

## 功能一览

| 功能 | 说明 |
|---|---|
| 单曲 | 粘贴链接或搜索，识别封面与标题后直接播放或下载 |
| 歌单 | 导入网易云 / QQ 音乐歌单，整单播放或下载 |
| 播放 | 队列、随机、循环、音量、音质选择；播控面板从迷你条展开 |
| 下载 | 进行中 / 已完成 / 失败统计、下载历史（最近 500 条）、终端日志面板 |
| 元数据 | 写入 MP3（ID3v2.3）与 FLAC（Vorbis Comment）标签，内嵌封面 / 歌词 |
| 设置 | 主题、主色、色彩风格、解析网关、下载目录等 |
| 快捷键 | 桌面端 `Ctrl/⌘ + 1..4` 切换页签 |

### 音源支持

| 音源 | 链接解析 | 搜索 | 歌单 |
|---|:---:|:---:|:---:|
| 网易云音乐 | ✅ | ✅ | ✅ |
| QQ 音乐 | ✅ | ✅ | ✅ |
| 酷我 / 酷狗 / 咪咕 / 汽水 / B 站 | ✅ | — | — |
| 直链 | ✅ | — | — |

> 在线播放与下载依赖内置解析网关（无需配置即可使用）。

---

## 当前版本产物（v0.1.19）

| 平台 | 文件 | 安装方式 |
|---|---|---|
| Linux | `concertplay_0.1.19_amd64.deb` | `sudo apt install ./concertplay_0.1.19_amd64.deb` |
| Linux | `ConcertPlay-0.1.19-x86_64.AppImage` | `chmod +x ConcertPlay-0.1.19-x86_64.AppImage && ./ConcertPlay-0.1.19-x86_64.AppImage` |
| Android | `ConcertPlay-0.1.19-arm64-v8a.apk` | `adb install -r ConcertPlay-0.1.19-arm64-v8a.apk` |
| Android | `ConcertPlay-0.1.19-universal.apk`（通用，含全部 ABI） | `adb install -r ConcertPlay-0.1.19-universal.apk` |

> 系统播放（Linux）依赖 `libmpv`（Debian/Ubuntu：`sudo apt install libmpv2`）。
> Windows 产物随后续版本提供，当前 dist 目录中暂未收录 Windows 包。

---

## 本版本更新（v0.1.19）

- 弹出菜单对齐 FlClash 最新版：24 圆角卡片、16 圆角行、20 号图标，补全按压 / 悬停 / 键盘焦点状态层
- 菜单动画重写：从触发控件中心小圆点放大成卡片（platter 思路），支持减少动画
- 液态玻璃菜单使用渐变发丝线，深色模式叠淡反光
- 设置页选择行、下载操作条、歌单音质选择改为右侧药丸按钮（ElasticPress 弹簧缩放）
- 修正歌单 Hero 飞行层圆角跳变问题
- 优化播控返回动画：手机端淡出、桌面弹窗向侧边栏缩放，加入轻微压扁缓冲

---

## 校验

```
20e30d9eb5dd22694c3238d0521256831fa9affc5c92346473512132950690b1  concertplay_0.1.19_amd64.deb
e9a4cc21e28145690b4e8b399ce2d9f85a780b382c7ef785728983c3c823ca2d  ConcertPlay-0.1.19-x86_64.AppImage
4f4487bb2cde82c8f7199a241671d1756c0e92d6e883276c0347b5253bfb323c  ConcertPlay-0.1.19-universal.apk
13c8113beb3e86a2f3258f63ba642a7bcefae8fd6185f47a00d0b47ed236f970  ConcertPlay-0.1.19-arm64-v8a.apk
```

校验命令：`sha256sum -c`（Linux）/ `Get-FileHash`（Windows）

---

## 旧版本

各历史版本产物保留在 `archive-*` 子目录中：

| 目录 | 版本 |
|---|---|
| `archive-0.1.18/` | 0.1.18 |
| `archive-0.1.17/` | 0.1.17 |
| `archive-0.1.16/` | 0.1.16 |
| `archive-0.1.15/` | 0.1.15 |
| `archive-0.1.14/` | 0.1.14 |
| `archive-0.1.13/` | 0.1.13 |
| `archive-0.1.12/` | 0.1.12 |
| `archive-0.1.11/` | 0.1.11 |
| `archive-0.1.10/` | 0.1.10 |
| `archive-0.1.9/` | 0.1.9 |
| `archive-0.1.8/` | 0.1.8 |

---

## 合规说明

- 本应用仅用于个人学习与研究，请遵守当地法律法规、平台条款，支持正版音乐。
- 应用不提供任何 DRM 解密能力；网关返回加密音频时会中止下载并提示。
- 解析网关配置完全存储在本机，不上传。
