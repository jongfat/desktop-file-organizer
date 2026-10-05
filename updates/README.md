# OTA 發布流程

更新端點：`https://raw.githubusercontent.com/jongfat/desktop-file-organizer/main/updates/latest.json`

1. 在本機開發專案的 `version.json` 修改三段數字版本、發布日期與更新內容。版本只能遞增。
2. 執行 `./build-installer.ps1`。版本會同步至程式及安裝包，並產生 `bin/DesktopOrganizer-Setup-<版本>.exe` 與 `updates/latest.json`（含大小及 SHA-256）。
3. 執行 `./test.ps1`、`./test-updater.ps1`、`./test-folder.ps1`、`./test-watch-today.ps1`、`./test-installer.ps1`。
4. 先上傳新安裝檔至 GitHub `bin`；確認可下載，再更新 README、`CHANGELOG.md`，最後上傳 `updates/latest.json`。
5. 已安裝 1.0.1 以上的工具會讀取此端點，顯示新版內容，由使用者選擇下載安裝。不要移除 manifest 所指的安裝檔，也不要重新打包同一版本後忘記更新 hash。

1.0.0 沒有 OTA 功能，需要手動安裝目前版本（1.0.3）一次。只支援正式三段版本，忽略相同版本及舊版本。下載僅允許本儲存庫的 HTTPS raw 安裝檔，拒絕轉址，且驗證檔案大小與 SHA-256。這是傳輸與完整性檢查；SHA-256 並非獨立的程式碼簽章。GitHub 帳號與儲存庫存取權必須妥善保護。

更新會開啟安裝精靈，程式結束後才覆蓋檔案，安裝成功後重新啟動。若使用者取消精靈，請從桌面捷徑重新開啟舊版。下載存於 `%LOCALAPPDATA%\DesktopOrganizer\updates`，已下載完成的安裝檔保留供重試，可在不進行更新時手動清除。
