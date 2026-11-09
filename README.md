# Team Harbor Downloads

Team Harbor 多帳號 Claude Team 管理工具的公開桌面安裝檔與更新資訊。原始碼另行維護，此 repo 用於下載與更新，不需要 GitHub Token。

請至本 repo 的 **Releases → Latest** 下載最新版本。目前版本為 **1.3.1**，修正登入保存與同步，並新增「匯入外部登入」按鈕。

| 平台 | 選擇檔案 |
| --- | --- |
| Windows x64 | `TeamHarbor-1.3.1-win-x64.exe` |
| macOS Apple Silicon | `TeamHarbor-1.3.1-mac-arm64.dmg` |
| macOS Intel | `TeamHarbor-1.3.1-mac-x64.dmg` |
| Ubuntu／Linux x64 | `TeamHarbor-1.3.1-linux-x86_64.AppImage` |

## 1.3.1 更新內容

- 修正重開工作區時空 Cookie 覆寫登入，以及重新載入頁面時舊 LocalStorage 覆寫新登入的問題。
- 關閉主視窗或退出程式前，先保存內嵌視窗的最新登入資料。
- WebDAV 與外部瀏覽器同步期間完成的新登入會優先保留；Google／SSO 等網站的 LocalStorage 與 Claude 分開處理。
- 內嵌視窗工具列新增「匯入外部登入」。在工作區專用 Chrome／Edge 完成登入後，先關閉外部瀏覽器，再按此按鈕匯入。
- 保留 1.3.0 的「人員管理」面板與仿官網浮動席位選單。

若舊版已遺失登入資料，更新後需重新登入一次。本次修正不會延長 Claude 服務端的登入期限；Claude Code 仍需完成獨立授權並具備對應 Team 使用權。

## macOS 更新

1.2.1 起，未簽署的 macOS 版本可在 App 內「檢查更新 → 下載更新」。下載依目前 App 架構選擇 DMG，完成大小與 SHA-512 校驗後，可按「開啟檔案位置」。

請退出 Team Harbor，開啟 DMG，依更新視窗顯示的位置替換 App，再啟動新版。若 macOS 阻擋啟動，可使用更新視窗的「複製解除隔離指令」，確認路徑後在終端機自行執行。例如：

```bash
xattr -dr com.apple.quarantine "/Applications/Team Harbor.app"
```

程式不會自動執行指令或替換 App。1.2.0 的 macOS 版本需先手動安裝本次新版，之後即可使用新的下載流程。此版尚未提供 Apple 程式碼簽章或公證。

## Windows 與 Linux 更新

Windows NSIS 與 Linux AppImage 可在程式內檢查、下載，再按「重新啟動並安裝」。Linux 的程式內更新僅適用於從 AppImage 啟動。

Releases 中的 ZIP、YAML、blockmap 供更新功能使用，請保留原始檔名。
