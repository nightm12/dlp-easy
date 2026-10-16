# YtDlp Easy

**简单易用的 yt-dlp Windows 桌面界面。** 使用 Electron、HTML、CSS 和原生 JavaScript 构建，帮助你设置音视频下载选项，不必手动拼写命令行参数。

![[YtDlp Easy 图标](assets/logo.png)](https://iili.io/nh1LRiN.png)

YtDlp Easy 在本机调用 yt-dlp 和 FFmpeg，不托管或代理媒体内容。

## 功能

- 下载 yt-dlp 支持网站的音频和视频，可设置格式、画质、播放列表和保存目录。
- 播放列表可先预览封面和曲名，扫描保存目录中的本地音乐；疑似重复项会提示并默认排除，可逐首选择要下载的新歌。
- 音频下载前检查选定文件夹中的音频文件名，按歌名跳过相同或相似歌曲；不比较歌手。
- 下载过程中停止当前任务。
- 复制生成的 PowerShell 命令，供手动粘贴运行。
- 扫描音乐文件夹中的重复或相似歌名，并可将选中文件移到 Windows 回收站。
- 下载前检查链接标题与本地音乐目录，选择跳过已拥有的内容。
- 深色/浅色主题切换。
- 每个新版本首次启动时显示一次更新说明，也可随时点击顶部“版本与更新”查看。
- 通过 winget 安装 yt-dlp，或选择已安装的 `yt-dlp.exe`。

## 下载与依赖

从 GitHub 仓库的 **Releases** 页面下载 Windows x64 安装程序。安装程序作为 Release 附件发布，不提交到源代码仓库。已安装旧版本的用户直接运行新版安装程序即可覆盖更新；请保持原安装位置，应用设置和下载记录保存在用户数据目录，不会因升级而清除。

下载和标题检查需要 **yt-dlp**。MP3 音频提取和 MP4 合并还需要 **FFmpeg**，并且 `ffmpeg.exe` 需要在系统 `PATH` 中。

## 从源码运行

需要 Windows 10/11、Node.js 20 或更新版本，以及 pnpm。

若 PowerShell 提示找不到 `pnpm`，先安装项目指定版本，然后关闭并重新打开 PowerShell：

```powershell
npm install --global pnpm@11.25.0
pnpm --version
```

在项目目录中安装依赖并构建：

```powershell
pnpm install --frozen-lockfile
pnpm start
```

构建 Windows x64 安装程序：

```powershell
pnpm dist
```

安装程序会生成在 `outputs/`。自定义 NSIS 脚本 `build_installer.nsi` 需要另外安装 NSIS。

## 更新日志

请查看 [CHANGELOG.md](CHANGELOG.md)，也可在应用中点击顶部“版本与更新”。

## 技术栈

- Electron
- HTML、CSS、原生 JavaScript
- yt-dlp
- FFmpeg（外部依赖）

## 许可证

本项目采用 MIT License，详见 [LICENSE](LICENSE)。yt-dlp 和 FFmpeg 是独立项目，各自遵循其许可证；本仓库不会将它们打包进安装程序。

使用本工具时，请遵守相关网站条款及所在地法律。

---

## English

**YtDlp Easy is a simple Windows desktop interface for yt-dlp.** Preview playlist covers and titles, compare tracks against a local music folder, choose new songs to download, stop active downloads, or copy a PowerShell command for manual use.

The app runs locally and does not host or proxy media. It requires yt-dlp; FFmpeg is required for audio extraction and MP4 merging. See the sections above for setup and build instructions.
