# 版本與更新內容 / Version history

## 1.0.2 — 2026-10-05

- 修正資料夾整理入口：在 Windows 系統匣圖示右鍵選單新增「整理所選資料夾」。
- 開啟資料夾選擇視窗，選定後顯示來源、整理結果位置及分類說明；確認後才搬移檔案。
- 取消選擇或取消確認時不建立整理資料夾，也不搬移檔案。
- 使用相同分類規則；結果保存在所選資料夾內的「桌面資料整理」，保留捷徑及子資料夾內容。
- 移除 1.0.1 的檔案總管右鍵整合，升級時清除其選單；保留 OTA 功能。

Corrected the entry point to the Windows tray icon's menu: “整理所選資料夾” (Organize selected folder). Choose a folder, review the source and destination, then confirm to sort. Cancelling either step leaves the folder unchanged. Removed the Explorer context menu introduced in 1.0.1; OTA updates remain available.

## 1.0.1 — 2026-10-05

- 新增檔案總管資料夾右鍵與空白處選單「整理此資料夾」（Windows 11 可於「顯示其他選項」找到）。
- 只整理所選資料夾一次，分類結果建立於其內的「桌面資料整理」，套用與桌面相同的分類。
- 保留捷徑，原子資料夾整包搬移；同名不覆蓋，顯示成功與失敗數量，可再次右鍵重試。
- 新增 OTA 線上版本檢查：啟動後及每 24 小時檢查官方 GitHub 更新資訊。
- 系統匣新增「版本 · 檢查更新」，顯示目前／最新版本、發布日期及更新內容。
- 使用者選擇更新後，下載安裝檔並核對大小與 SHA-256；失敗時不執行安裝。
- 沿用安裝路徑，開啟安裝精靈，更新完成後重新常駐；分類資料與紀錄保留。
- 斷線與檢查失敗不影響整理；提供本機版本紀錄供離線閱讀。

Added Explorer's “Organize this folder” context menu, with the same categories as desktop sorting. Results remain inside the selected folder; shortcuts and original subfolder contents are preserved. Also added online update checks, version and release notes, verified downloads and restart after installation.

## 1.0.0 — 2026-10-05

- Windows 系統匣常駐、登入啟動、手動整理與資料夾捷徑。
- 依副檔名分類，Office／PDF／TXT 集中於「文件」；原資料夾完整搬移。
- 桌面捷徑保留、撞名不覆蓋、搬移紀錄及警示資料夾圖示。
- 單一 Windows 安裝檔、六語系 README。

Initial release: desktop sorting, preserved shortcuts, collision protection, move history, a warning folder icon, a single Windows installer and six README languages.
