# ConcertPlay (CPD)

ConcertPlay 是一个本地优先的跨平台音乐播放与下载客户端，支持 Linux / Android（Windows 版随后续版本提供）。

- **应用名**：ConcertPlay
- **简称**：CPD
- **开发者**：ByRUDAN
- **当前版本**：`0.1.40`（`0.1.40:01-BS52`）

## 功能

- 单曲：粘贴链接或搜索，识别封面与标题后直接播放或下载
- 歌单：导入网易云 / QQ 音乐歌单，或新建 ConcertPlay 自建歌单；支持改名、简介、自定义封面与移除曲目，外部歌单可整单转为自建歌单；支持全部歌单备份导出与导入（封面随备份迁移）；新增歌曲置顶，歌曲侧滑可直接加入歌单或删除
- 播放：队列、随机、循环、音量、音质选择；在线音频边播边加载，切换音质会重新解析；高码率解析失败自动降档；可选听歌缓存（手动开启、可设上限）；「关于」内置检查更新与彩蛋；播控面板从底部迷你条展开
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

## 当前版本产物（v0.1.40）

安装包统一发布在 [Releases](https://github.com/Rudan177/CPRelease/releases/latest)，仓库不再提交二进制文件。

| 平台 | 文件 | 安装方式 |
|---|---|---|
| Linux | `concertplay_0.1.40_amd64.deb` | `sudo apt install ./concertplay_0.1.40_amd64.deb` |
| Linux | `ConcertPlay-0.1.40-x86_64.AppImage` | `chmod +x ConcertPlay-0.1.40-x86_64.AppImage && ./ConcertPlay-0.1.40-x86_64.AppImage` |
| Android | `ConcertPlay-0.1.40-arm64-v8a.apk` | `adb install -r ConcertPlay-0.1.40-arm64-v8a.apk` |
| Android | `ConcertPlay-0.1.40-universal.apk`（通用，含全部 ABI） | `adb install -r ConcertPlay-0.1.40-universal.apk` |

> Linux 播放依赖系统 `libmpv`（Debian/Ubuntu：`sudo apt install libmpv2`）。

## 应用内更新

设置页「更新」会读取仓库根目录的 [`version.json`](./version.json) 与最新 Release：

- 有新版本时展示更新日志，可直接下载当前平台对应的安装包
- Android 按 ABI 选择 APK，下载完成后拉起系统安装程序
- Linux 优先下载 AppImage（缺失时回退 DEB），下载后自动赋予可执行权限并可在文件管理器中定位
- 下载进度实时显示，失败会保留可重试提示

## 本版更新

详见 [`CHANGELOG.md`](./CHANGELOG.md)

## 校验

```
88e52f7e5a16e99f5acb5672cea6cfeb881b8894dab63d4eca2d1fda1490351c  concertplay_0.1.40_amd64.deb
a414b932fd5e85d025bab98a2745249e45f60a947da3ceaa1b70781d907e413a  ConcertPlay-0.1.40-x86_64.AppImage
8d954c8fba7cfd213221ec2fb8567264f1d39b75039aa7d7580a948c43da1331  ConcertPlay-0.1.40-universal.apk
56a3a4ea02af9db4228482e1ab3cccc33f01eedc9c01bddd42c7016b61045344  ConcertPlay-0.1.40-arm64-v8a.apk
```

校验命令：`sha256sum -c`（Linux）/ `Get-FileHash`（Windows）

## 合规说明

- 本应用仅用于个人学习与研究，请遵守当地法律法规、平台条款，支持正版音乐。
- 应用不提供任何 DRM 解密能力；网关返回加密音频时会中止下载并提示。
- 解析网关配置完全存储在本机，不上传。
