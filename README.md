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
| 播放 | 队列、随机、循环、音量、音质选择；播控面板从底部迷你条展开 |
| 下载 | 进行中 / 已完成 / 失败统计、下载历史（最近 500 条）、终端日志面板 |
| 元数据 | 写入 MP3（ID3v2.3）与 FLAC（Vorbis Comment）标签，支持内嵌封面 / 歌词 |
| 设置 | 主题、主色、色彩风格、解析网关（内置默认值，开箱即用）、下载目录 |
| 快捷键 | 桌面端 `Ctrl/⌘ + 1..4` 切换单曲 / 歌单 / 下载 / 设置 |

### 音源支持

| 音源 | 链接解析 | 搜索 | 歌单 |
|---|:---:|:---:|:---:|
| 网易云音乐 | ✅ | ✅ | ✅ |
| QQ 音乐 | ✅ | ✅ | ✅ |
| 酷我 / 酷狗 / 咪咕 / 汽水 / B 站 | ✅ | — | — |
| 直链 | ✅ | — | — |

> 在线播放与下载依赖内置解析网关，安装后即可使用，无需手动配置。

---

## 当前版本产物（v0.1.19）

| 平台 | 文件 | 安装方式 |
|---|---|---|
| Linux | `concertplay_0.1.19_amd64.deb` | `sudo apt install ./concertplay_0.1.19_amd64.deb` |
| Linux | `ConcertPlay-0.1.19-x86_64.AppImage` | `chmod +x ConcertPlay-0.1.19-x86_64.AppImage && ./ConcertPlay-0.1.19-x86_64.AppImage` |
| Android | `ConcertPlay-0.1.19-arm64-v8a.apk` | `adb install -r ConcertPlay-0.1.19-arm64-v8a.apk` |
| Android | `ConcertPlay-0.1.19-universal.apk`（通用，含全部 ABI） | `adb install -r ConcertPlay-0.1.19-universal.apk` |

> Linux 播放依赖系统 `libmpv`（Debian/Ubuntu：`sudo apt install libmpv2`）。

---

## 本版本更新（v0.1.19）

详见 [`CHANGELOG.md`](./CHANGELOG.md)

---

## 校验

```
cbfff53fd2ea782a9a39449d0943bdaaf0838b400263b869cc59b5a4b2641f84  concertplay_0.1.19_amd64.deb
67ae665ed1e957889ec9edca002c282c1e80f597cf1ab26c7952972a0a3ddfdc  ConcertPlay-0.1.19-x86_64.AppImage
b580353462237c9ca1e153e7194ef7eac8aec1f48345f9dd8385a228def030c9  ConcertPlay-0.1.19-universal.apk
37b7fa4c333d03166fd7117c4d75814d409553797f1143bd19b46ad6fe4f7803  ConcertPlay-0.1.19-arm64-v8a.apk
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
