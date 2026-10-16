# 更新日志

## [1.1.1] - 2026-10-16

### 新增
- 设置中可分别调整整体界面缩放（90%–125%）和文字大小（90%–140%）。
- 调整时即时预览并自动保存；支持恢复默认显示大小。

### 改进
- 默认界面和文字略微放大，提升可读性。
- 设置页分为“外观与可读性”和“下载程序”区域，并加入文字预览。

## [1.1.0] - 2026-10-16

### 新增
- 播放列表预览：显示歌曲标题和封面，并可选择要下载的歌曲。
- 下载前按歌曲名称检查本地音乐文件夹，标记可能重复的曲目；匹配不依赖歌手名。
- 增加“版本与更新”窗口：新版本首次启动时显示一次，也可从应用顶部再次打开。
- 增加 yt-dlp 版本检查、安装入口和 PowerShell 命令复制功能。
- 增加下载过程日志和停止下载按钮。

### 改进
- 修正 Windows 程序文件图标资源的写入配置，安装程序、开始菜单/桌面快捷方式及任务栏使用项目品牌图标。
- 播放列表中可只下载未重复的选中曲目。
- README 增加 Windows 构建与依赖说明。

## [1.0.9]
- 初始公开版本，提供音视频下载、重复歌曲检查和浅色/深色主题。

---

# Changelog

Notable user-facing changes are listed here. The app shows release notes once after each version update; open **Version & updates** in the app to view them again.

## [1.1.1] - 2026-10-16

### Added
- Separate controls for overall interface scale (90%–125%) and text size (90%–140%).
- Live preview, automatic preference saving, and a reset-to-default action.

### Improved
- Slightly larger default interface and text for better readability.
- Reorganized settings into Appearance & readability and Download program sections, with a text preview.

## [1.1.0] - 2026-10-16

### Added
- Playlist preview with track titles and cover art, plus per-track download selection.
- Local music checks by song title, with likely duplicates flagged before download.
- A version dialog that appears once on first launch of a new release and remains available from the app header.
- yt-dlp version checking and installation actions, PowerShell command copying, download logs, and a stop button.

### Improved
- Enabled embedding the branded icon into the Windows executable so the app, taskbar, and shortcuts use the YtDlp Easy logo.
- Playlist downloads can exclude tracks already present in the selected folder.
- Added Windows build, dependency, and upgrade guidance to the README.

## [1.0.9]
- Initial public release with audio/video downloads, duplicate-title checks, and light/dark themes.
