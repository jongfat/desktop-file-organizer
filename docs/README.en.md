# ⚡ Desktop Organizer

[繁體中文](../README.md) · [简体中文](README.zh-CN.md) · [English](README.en.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Italiano](README.it.md)

## What's new in 1.0.1 · 2026-10-05

Explorer now offers “整理此資料夾” (Organize this folder) when you right-click a folder or its empty background. Enable the context menu during installation; on Windows 11, look under “Show more options.” This sorts the selected folder once using the same categories. Results stay inside its “桌面資料整理” folder. Shortcuts remain in place, original subfolders move intact into “資料夾,” and failed moves can be retried by running the command again.

OTA updates: the tray's version/update window shows installed and latest versions, release date and notes. Checks run after startup and every 24 hours. Choose download/update to verify installer size and SHA-256, open the installer at the existing location and restart after installation. Offline checks do not interrupt sorting. If you cancel installation, reopen the shortcut. **Users of 1.0.0 must manually install 1.0.1 once.** [Version history](../CHANGELOG.md)

> **Make room for ideas. Give clutter a place to go.**

Reports, screenshots, installers, archives. Your desktop deserves better than becoming a parking lot for files.

Desktop Organizer waits in the Windows system tray, sorts loose files into their categories, and moves existing folders as complete units. Your shortcuts stay where you expect them, so you can keep working.

**Start at sign-in · Organize every 30 seconds · Keep shortcuts · Preserve name collisions · One installer**

## 🚀 One file. A fresh start.

Installer location, relative to the project root: `bin/DesktopOrganizer-Setup-1.0.1.exe`.

**[⬇️ Download the Windows installer](https://github.com/jongfat/desktop-file-organizer/raw/refs/heads/main/bin/DesktopOrganizer-Setup-1.0.1.exe)**

1. Double-click the EXE and follow the Traditional Chinese installation wizard.
2. Choose whether to create a desktop shortcut and start automatically at sign-in.
3. Launch from the final page, or open the shortcut later.

The application, warning icon, guide, and uninstaller are bundled into one EXE. Copy that file to another computer to install it there.

Requires **Windows 10/11** and **.NET Framework 4.8**. The installer checks for the framework and prompts if it is missing. Installation is per user, defaults to `%LOCALAPPDATA%\Programs\DesktopOrganizer`, and requires no administrator privileges.

**The six languages apply to the README. The application, installer, and actual folder names currently remain in Traditional Chinese. The table below uses the real folder names.**

## 🗂️ A place for every file

All categories live inside `桌面資料整理` on your desktop.

| Format | Destination |
| --- | --- |
| DOC, DOCX | 文件 → Word |
| XLS, XLSX, CSV | 文件 → Excel |
| PPT, PPTX | 文件 → PowerPoint |
| PDF / TXT | 文件 → PDF / TXT |
| Images such as TIF, TIFF, PNG, JPG, JPEG, GIF, WEBP | 圖檔 — images |
| Videos such as MP4, AVI, MOV, MKV, WEBM | 影片 — videos |
| Programs and scripts such as APK, EXE, MSI, MSIX, BAT, CMD, PS1 | 程式 — programs |
| Archives such as ZIP, RAR, 7Z, TAR, GZ | 壓縮檔 — archives |
| Existing folders with their contents | 資料夾 → original folder name |
| Other formats, such as LEA | 其他類別 → uppercase extension |
| No extension | 其他類別 → 無副檔名 |

Classification uses extensions, not document text. Extension matching ignores case; the final suffix determines the category, so `backup.tar.gz` goes into archives. Categories are created only when needed.

## 🎛️ Quiet in the background. Ready when you are.

Double-click the desktop shortcut to start the tool and browse the organized folder. If it is already running, the folder opens directly. Automatic sign-in startup stays in the background.

Right-click the tray icon to organize now, pause automatic organization, open the folder, view the log, or exit. Double-clicking the tray icon also organizes immediately. Pause lasts for the current session; exiting does not disable startup at sign-in.

## 🛡️ Keep the files. Lose the clutter.

- `.lnk`, `.url`, and `.appref-ms` shortcuts remain on the desktop.
- Name collisions receive `(1)`, `(2)`, and so on, without overwriting existing files or folders.
- Existing folders move intact, preserving their internal structure.
- Items modified within the last 10 seconds are deferred. Failed moves are logged and retried on later passes.
- Hidden, system, and linked items, common partial downloads, and Office temporary files are skipped. Public desktop items are untouched.
- The log is at `%LOCALAPPDATA%\DesktopOrganizer\history.csv`: `MOVE` means an attempt, `DONE` means completion, and `ERROR` means an error.

The tool uses your Windows user desktop location, including desktops redirected to OneDrive. Automatic startup occurs when you sign in to Windows.

> ⚠️ **`桌面資料整理` contains your original files. Do not delete it.** The warning icon is a reminder, not a deletion lock. Organization is not a backup; back up important files separately.

## 🔄 Update, disable, or uninstall

Exit from the tray before running a newer installer. Old categories are migrated to the current layout; emptied old categories are removed, while failed items remain for retry.

To disable sign-in startup, press `Win + R`, enter `shell:startup`, and delete the `桌面整理工具` shortcut. Exit the currently running tool as well.

To uninstall, exit first, then use Windows installed apps or the Start menu uninstaller. Installed application files and shortcuts are removed; **organized data and logs remain**. Pause or exit before moving files back to the desktop manually.

## 🧰 Build and package

This GitHub distribution repository contains the installer and documentation. The commands below apply to the complete local development project.

Built with C#, Windows Forms, .NET Framework, and Inno Setup 6. Run from the project root:

```powershell
./build.ps1           # Compile the application and create its icon
./test.ps1            # Test classification, moves, and migration
./build-installer.ps1 # Create one installer EXE in bin
./test-installer.ps1  # Test install, upgrade, uninstall, and data retention
```

The default compiler is `.tools/InnoSetup/ISCC.exe`; specify another location with `-CompilerPath`.

For development, use `./install.ps1` or `./install.ps1 -Update`. This defaults to `%LOCALAPPDATA%\DesktopOrganizer` and reuses the existing shortcut location when updating. It is a separate installation path from the wizard.

Only application files, configuration, the icon, and the guide enter the installer. Git currently ignores `bin`; upload the generated EXE to GitHub Releases to distribute it.
