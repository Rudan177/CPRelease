# ConcertPlay (CPD)

ConcertPlay 是一个本地优先的跨平台音乐播放与下载客户端，支持 Linux / Android（Windows 版随后续版本提供）。

- **应用名**：ConcertPlay
- **简称**：CPD
- **开发者**：ByRUDAN
- **当前版本**：`0.1.21`（`0.1.21:01-BS33`）

## 功能

- 单曲：粘贴链接或搜索，识别封面与标题后直接播放或下载
- 歌单：导入网易云 / QQ 音乐歌单，整单播放或下载
- 播放：队列、随机、循环、音量、音质选择；播控面板从底部迷你条展开
- 下载：进行中 / 已完成 / 失败统计、下载历史（最近 500 条）、终端日志面板
- 元数据：写入 MP3（ID3v2.3）与 FLAC（Vorbis Comment）标签，支持内嵌封面 / 歌词
- 设置：主题、主色、色彩风格、解析网关（内置默认值，开箱即用）、下载目录
- 快捷键：桌面端 `Ctrl/⌘ + 1..4` 切换单曲 / 歌单 / 下载 / 设置

### 音源支持

| 音源 | 链接解析 | 搜索 | 歌单 |
|---|:---:|:---:|:---:|
| 网易云音乐 | ✅ | ✅ | ✅ |
| QQ 音乐 | ✅ | ✅ | ✅ |
| 酷我 / 酷狗 / 咪咕 / 汽水 / B 站 | ✅ | — | — |
| 直链 | ✅ | — | — |

> 在线播放与下载依赖内置解析网关，安装后即可使用，无需手动配置。

## 当前版本产物（v0.1.21）

| 平台 | 文件 | 安装方式 |
|---|---|---|
| Linux | `concertplay_0.1.21_amd64.deb` | `sudo apt install ./concertplay_0.1.21_amd64.deb` |
| Linux | `ConcertPlay-0.1.21-x86_64.AppImage` | `chmod +x ConcertPlay-0.1.21-x86_64.AppImage && ./ConcertPlay-0.1.21-x86_64.AppImage` |
| Android | `ConcertPlay-0.1.21-arm64-v8a.apk` | `adb install -r ConcertPlay-0.1.21-arm64-v8a.apk` |
| Android | `ConcertPlay-0.1.21-universal.apk`（通用，含全部 ABI） | `adb install -r ConcertPlay-0.1.21-universal.apk` |

> Linux 播放依赖系统 `libmpv`（Debian/Ubuntu：`sudo apt install libmpv2`）。

## 本版更新

详见 [`CHANGELOG.md`](./CHANGELOG.md)

## 校验

```
57545bb35fe90c2f46264467c9f26c50662a7bb37b1aade8715dcab30286f69e  concertplay_0.1.21_amd64.deb
98cb2b387c165251c2be7703ac86e93be3c9b7dbaf48c9105eaebd62d20390dd  ConcertPlay-0.1.21-x86_64.AppImage
014887baa3fe2ddc432225fa9f1bed4f31b5503d91b339b0a601cd9496fb369a  ConcertPlay-0.1.21-universal.apk
c7dfab90224abac6cde8fcf1bfd622c23a19391e40f209acd8b040120e9ac018  ConcertPlay-0.1.21-arm64-v8a.apk
```

校验命令：`sha256sum -c`（Linux）/ `Get-FileHash`（Windows）

## 合规说明

- 本应用仅用于个人学习与研究，请遵守当地法律法规、平台条款，支持正版音乐。
- 应用不提供任何 DRM 解密能力；网关返回加密音频时会中止下载并提示。
- 解析网关配置完全存储在本机，不上传。
