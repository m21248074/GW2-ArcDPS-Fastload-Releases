# GW2 ArcDPS Fastload

Fastload 的公開發布倉庫，提供 DLL 下載、安裝說明與問題回報。程式原始碼不在此倉庫公開。

## 下載

前往 [Releases](https://github.com/m21248074/GW2-ArcDPS-Fastload-Releases/releases/latest)，下載 `Fastload_1.0.0.zip` 或 `arcdps_fastload.dll`。

GitHub 自動產生的 `Source code (zip)` 與 `Source code (tar.gz)` 僅包含本倉庫文件，不是插件安裝包。

## 功能

- 載入加速。
- 帳號角色清單與角色切換，職業名稱使用繁體中文。
- 過場動畫自動跳過、逾時設定與手動跳過浮窗。
- 對話自動跳過與手動跳過浮窗。
- 繁體中文設定介面、設定保存及診斷資訊。

本版不包含快捷鍵。

## 安裝與更新

需要 Windows x64 的 Guild Wars 2，以及支援 Dear ImGui 1.92.7 的 arcdps。

1. 完全關閉遊戲。更新前請備份目前使用的 Fastload DLL。
2. 將 `arcdps_fastload.dll` 放入 `<Guild Wars 2>\bin64\`。
3. 確認其他插件載入位置（例如 `legacy`）沒有另一份 Fastload，避免重複載入。
4. 啟動遊戲，在 arcdps 設定中開啟 Fastload 設定頁。

執行時只需單一 DLL，不需要 `fastload_core.bin`。ZIP 內的第三方授權文件請一併保留。

## 設定

| 選項 | 用途 |
| --- | --- |
| 啟用載入加速 | 開啟或關閉載入加速 |
| 顯示角色選擇 | 顯示角色清單，點選角色送出切換要求 |
| 跳過過場動畫 | 自動跳過可處理的過場動畫 |
| 過場動畫逾時（毫秒） | 自動跳過前的等待時間，預設 2500，範圍 50–60000 |
| 過場動畫跳過浮窗 | 顯示手動跳過動畫的按鈕 |
| 跳過對話 | 自動停止可處理的遊戲內對話 |
| 對話跳過浮窗 | 顯示手動跳過對話的按鈕 |

自動跳過與浮窗可分別設定，也不依賴載入加速開關。浮窗只在遊戲位於前景時顯示。

設定保存在 `<Guild Wars 2>\addons\arcdps\arcdps_fastload.ini`，更新 DLL 時會沿用現有設定。全新設定預設開啟載入加速，其他功能需自行開啟。

自動跳過對話會排除下列地圖 ID：956、1062、1149、1156、1177、1188、1205、1264、1290、1303、1323、1384、1500。手動跳過按鈕不受這份地圖清單限制。

## 問題回報

遊戲更新可能導致插件需要更新。若特定跳過功能無法初始化，對應設定會停用；若必要入口無法確認，插件會停止初始化。

請在 [Issues](https://github.com/m21248074/GW2-ArcDPS-Fastload-Releases/issues) 提供：

- Fastload、arcdps 與遊戲版本。
- 問題發生的地圖、操作步驟與啟用選項。
- Fastload「診斷」中的狀態，必要時附上 `addons\arcdps\arcdps.log` 或 `arcdps_lastcrash.log` 的相關片段。

貼出記錄前請遮蔽帳號、角色名稱及其他個人資料。若更新後出現問題，可退出遊戲換回備份 DLL。

## 第三方元件

使用 Dear ImGui 與 MinHook，其授權分別列於 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。這些元件的授權不代表本插件的其餘原始碼已公開。
