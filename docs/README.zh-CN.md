# ⚡ Desktop Organizer｜桌面整理工具

[繁體中文](../README.md) · [简体中文](README.zh-CN.md) · [English](README.en.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Italiano](README.it.md)

> **桌面留给灵感，杂乱交给我。**

报表、截图、安装文件、压缩包……你的桌面，值得比“文件停车场”更好的待遇。

Desktop Organizer 在 Windows 系统托盘待命，将散落的文件送入对应分类，让原本装好的文件夹整体归位。常用快捷方式留在原处，你的工作节奏继续向前。

**登录启动 · 每 30 秒整理 · 保留快捷方式 · 同名不覆盖 · 单文件安装**

## 🚀 一个安装文件，重新开场

安装文件位于项目根目录下的 `bin/DesktopOrganizer-Setup-1.0.0.exe`。

**[⬇️ 下载 Windows 安装程序](../bin/DesktopOrganizer-Setup-1.0.0.exe?raw=true)**

1. 双击 EXE，按繁体中文安装向导操作。
2. 选择桌面快捷方式和登录自动启动。
3. 在最后一页选择立即启动，或稍后从快捷方式打开。

程序、警示图标、使用说明及卸载功能均包含在一个 EXE 中。复制到另一台电脑即可安装。

支持 **Windows 10／11**，需要 **.NET Framework 4.8**；缺少时安装向导会提示。仅为当前用户安装，默认路径为 `%LOCALAPPDATA%\Programs\DesktopOrganizer`，无需管理员权限。

**六种语言仅用于 README；程序界面、安装向导和实际文件夹名称目前仍使用繁体中文。下表保留实际路径名称。**

## 🗂️ 每种文件，都有自己的位置

所有分类位于桌面的 `桌面資料整理` 文件夹中。

| 格式 | 目标位置 |
| --- | --- |
| DOC、DOCX | 文件 → Word |
| XLS、XLSX、CSV | 文件 → Excel |
| PPT、PPTX | 文件 → PowerPoint |
| PDF / TXT | 文件 → PDF / TXT |
| TIF、TIFF、PNG、JPG、JPEG、GIF、WEBP 等图片 | 圖檔 |
| MP4、AVI、MOV、MKV、WEBM 等视频 | 影片 |
| APK、EXE、MSI、MSIX、BAT、CMD、PS1 等程序和脚本 | 程式 |
| ZIP、RAR、7Z、TAR、GZ 等压缩文件 | 壓縮檔 |
| 已装好内容的文件夹 | 資料夾 → 原文件夹名称 |
| LEA 等其他格式 | 其他類別 → 大写扩展名 |
| 无扩展名 | 其他類別 → 無副檔名 |

按扩展名分类，不读取正文进行语义判断。大小写视为同一格式；多重扩展名取最后一段，`backup.tar.gz` 也归入压缩文件。仅在需要时创建分类，避免堆积空文件夹。

## 🎛️ 后台待命，随时接手

双击桌面快捷方式会启动工具并打开整理文件夹；已驻留时直接打开文件夹。登录自动启动在后台运行。

右键系统托盘图标，可立即整理、暂停自动整理、打开整理文件夹、查看记录或退出。双击托盘图标也可立即整理。暂停仅适用于本次运行；退出不会取消登录启动设置。

## 🛡️ 整齐，也要保留你的数据

- `.lnk`、`.url`、`.appref-ms` 快捷方式保留在桌面。
- 同名文件或文件夹追加 `(1)`、`(2)` 等编号，不覆盖已有内容。
- 原文件夹整体移动，保留内部结构。
- 最近 10 秒有更新的项目延后处理；移动失败会记录并在后续轮次重试。
- 跳过隐藏、系统、链接项目、常见下载临时文件和 Office 临时文件；不移动公共桌面内容。
- 记录位于 `%LOCALAPPDATA%\DesktopOrganizer\history.csv`：`MOVE` 表示尝试，`DONE` 表示完成，`ERROR` 表示错误。

使用 Windows 设置的当前用户桌面路径，支持已重定向到 OneDrive 的桌面。自动启动发生在登录 Windows 时。

> ⚠️ **`桌面資料整理` 保存原始数据，请勿删除。** 警示图标不会禁止删除。整理不是备份，请另行备份重要文件。

## 🔄 更新、停用与卸载

更新前先从系统托盘退出，再运行新版安装程序。旧分类按当前规则调整；清空后移除旧分类，失败项目保留并重试。

关闭登录启动：按 `Win + R` 输入 `shell:startup`，删除“桌面整理工具”快捷方式，再退出当前驻留程序。

卸载前先退出工具，再通过 Windows 已安装应用或开始菜单卸载。程序和安装创建的快捷方式移除，**整理数据与记录保留**。手动移回桌面前，请先暂停或退出工具。

## 🧰 开发与打包

GitHub 发布仓库提供安装文件和说明文档；以下命令适用于完整的本地开发项目。

采用 C#、Windows Forms、.NET Framework 和 Inno Setup 6。在项目根目录执行：

```powershell
./build.ps1           # 编译程序和生成图标
./test.ps1            # 分类、移动及升级测试
./build-installer.ps1 # 生成单个安装 EXE 到 bin
./test-installer.ps1  # 安装、更新、卸载及数据保留测试
```

默认编译器为 `.tools/InnoSetup/ISCC.exe`，可用 `-CompilerPath` 指定其他位置。

开发安装可用 `./install.ps1`，更新可用 `./install.ps1 -Update`，默认安装到 `%LOCALAPPDATA%\DesktopOrganizer`；更新沿用现有快捷方式位置。此方式与完整安装向导不同。

安装包仅包含程序、配置、图标和说明。`bin` 目前由 Git 忽略；可将生成的 EXE 上传至 GitHub Releases 供下载。
