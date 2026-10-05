# 版本與更新內容 / Version history

## 1.0.5 — 2026-10-05

- 修正規則樹無法拖曳：副檔名可拖到分類更改關聯，拖到其他類別可恢復自動歸類。
- 分類可拖曳合併關聯或移為子分類，連同子分類與所有副檔名更新；可拖到根節點移回頂層。
- 新增目標反白、展開及邊緣捲動；固定節點、繼承規則、自身／子孫及無效目標不允許拖曳。
- 拖曳只改草稿，儲存並確認後才重新歸類；同名分類需明確合併，避免誤覆寫。

Fixed the missing Rules-tree drag-and-drop support. Extension reassignment and category merge/nesting update the draft and preserve all child associations. Highlighting, expansion and edge scrolling help target selection. Invalid destinations are rejected; confirmed saving remains required before file moves.

## 1.0.4 — 2026-10-05

- 系統匣右鍵新增「規則」：樹狀顯示分類及副檔名，可新增、修改、刪除關聯與分類，包含自動歸類的 ISO 等格式。
- 預設共用規則，桌面及各監視資料夾可建立獨立專屬規則或恢復繼承；設定重啟、升級及解除安裝後保留。
- 儲存前確認受影響來源，立即重新歸類整理紀錄中的既有歸檔檔案；Today 仍優先，原子資料夾保持完整，未記錄內容不搬移。
- 刪除規則不刪檔，相關格式回到其他類別；移空的舊分類只清除空資料夾。同名不覆蓋，鎖定／離線要求保留並重試。
- 單次整理與背景巡查都套用對應來源規則。設定損壞時停止搬移並提示修復；分類路徑限制於整理根目錄，拒絕連結目的地。

Added a tray Rules editor with a category/extension tree, shared defaults and independent folder rules. Confirmed saves reclassify recorded archived files immediately, with persistent retries for locked or offline sources. Today priority, intact original folders and collision protection remain. Rule deletion never deletes files; invalid configuration stops moves until repaired.

## 1.0.3 — 2026-10-05

- 系統匣右鍵新增「資料夾監視」：列出固定監視的桌面與額外資料夾，可新增、修改、移除；清單自動儲存，重啟後沿用。
- 每 30 秒一併巡查桌面與所有監視資料夾，整理結果各自放在來源內的「桌面資料整理」。單一位置離線或失敗不阻止其他位置，恢復後再試。
- 新增「當日檔案(Today)」：依本機最後修改日期，當天待整理的檔案先集中放置，不分格式；跨日後下一輪巡查才按原分類歸檔。
- 仍保留捷徑、同名檔案及原子資料夾內容；受監視資料夾及其上層資料夾不會被桌面巡查搬走。
- 「暫停自動整理」套用全部監視來源；「立即整理」巡查全部來源。單次「整理所選資料夾」同樣套用 Today 規則，跨日後需再次整理或加入監視。

Added persistent multi-folder monitoring, source-local outputs, per-folder failure isolation and a Today holding folder based on local last-modified dates. The next scan after midnight archives older files by type, with shortcuts, collisions and original subfolders preserved.

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
