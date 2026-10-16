# 更新日志

## [1.1.7] - 2026-10-16

### 修复
- 修复下载完成后界面仍停留在“下载进行中”的问题；改为从 yt-dlp 输出捕获视频 ID，避免下载收尾时写入历史记录阻塞完成信号。
- PowerShell 窗口仍保留下载输出，应用状态会在任务结束后更新为完成或失败。

## [1.1.6] - 2026-10-16

### 修复与改进
- 重复判断增加站点与视频 ID：同一个视频即使标题在日文和英文之间变化，也可按同一视频识别。
- 读取下载文件夹中的 `download-archive.txt`，并为之后通过应用下载的项目保存本地视频 ID 记录。
- 在重复提示中分别显示“同一视频已下载”和“歌名相似”，不再混为一种判断。

## [1.1.5] - 2026-10-16

### 修复
- 修正歌曲标题含 `/` 时被误当作文件路径截断的问题，避免像 `Fatal / GEMN` 这样的歌名漏判。
- 对 YouTube 链接补充标准封面地址，yt-dlp 未返回封面字段时仍会尝试显示缩略图。
- 新歌行显示最相似的本地文件名和相似度，方便定位漏判。

### 改进
- 将歌单预览入口改为明确的“封面、标题与逐首选择”，并在下载设置中说明开关用途。

## [1.1.4] - 2026-10-16

### 修复与改进
- 用标准化歌名和字符索引先筛选候选歌曲，再做相似度比较，减少大音乐库和长播放列表检查时的卡顿。
- 播放列表重复检查结果会显示实际扫描路径和识别到的音频数量，便于发现选错文件夹造成的漏判。
- 播放列表一次先显示 250 首，用户可分批展开，减少一次渲染大量歌曲造成的界面迟缓。
- 音乐库扫描会定期让出界面处理时间，降低大量文件比对期间的无响应感。

## [1.1.3] - 2026-10-16

### 修复
- 标题读取强制使用 UTF-8，避免日文在 Windows 控制台编码下损坏并漏掉重复匹配。
- 比对时统一平假名与片假名。

### 改进
- 可提取引号里的歌曲名进行匹配，并忽略常见 MV、OP、ED、动画标题等附加描述，减少宣传文案造成的漏判。

## [1.1.2] - 2026-10-16

### 新增
- 应用内检查 GitHub 正式版更新，查看版本、Release 说明和下载进度。
- 可直接从应用下载新版安装程序并启动更新向导。

### 安全与兼容
- 仅接受配置仓库的 GitHub Release 安装包，并验证下载内容是 Windows 可执行程序。
- GitHub 尚未发布正式版或未附安装包时，会在应用内说明。

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

Notable user-facing changes are listed here. The app shows release notes once after each version update; open **Version logs** in the app to view them again.

## [1.1.7] - 2026-10-16

### Fixed
- Fix the app staying in “Downloading” after yt-dlp finishes by capturing video IDs from yt-dlp output instead of writing its history file during finalization.
- Keep the PowerShell output visible while updating the app status to completed or failed after the task exits.

## [1.1.6] - 2026-10-16

### Fixed and improved
- Match the site and video ID so the same video is detected even when its displayed title changes between Japanese and English.
- Read yt-dlp's `download-archive.txt` and save IDs for future downloads started through the app.
- Distinguish exact video-ID matches from similar-title matches in duplicate notices.

## [1.1.5] - 2026-10-16

### Fixed
- Stop treating `/` inside a song title as a filesystem path separator, preventing missed matches such as `Fatal / GEMN`.
- Add a standard YouTube thumbnail fallback when yt-dlp does not provide a thumbnail URL.
- Show the closest local filename and similarity score on new-track rows for easier diagnosis.

### Improved
- Make playlist preview and per-track selection easier to discover in the download settings and preview panel.

## [1.1.4] - 2026-10-16

### Fixed and improved
- Filter fuzzy title comparisons through a normalized title index to reduce stalls with large music folders and playlists.
- Show the exact scanned folder and recognized audio count in playlist duplicate results to make folder-selection misses easier to diagnose.
- Render playlist entries in batches of 250 to keep large previews responsive.
- Yield to the UI during large library scans.

## [1.1.3] - 2026-10-16

### Fixed
- Force UTF-8 when reading yt-dlp titles to prevent Windows console encoding from corrupting Japanese text and missing duplicate matches.
- Normalize Hiragana and Katakana to the same form during comparison.

### Improved
- Match quoted song titles and ignore common MV, OP, ED, and anime-label text to reduce false negatives caused by promotional suffixes.

## [1.1.2] - 2026-10-16

### Added
- Check for GitHub releases in the app and view version, release notes, and download progress.
- Download the new installer from the app and launch the update wizard directly.

### Security and compatibility
- Accept installers only from this repository's GitHub Releases and verify the downloaded Windows executable.
- Show an in-app message when no stable release or installer asset is available.

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
