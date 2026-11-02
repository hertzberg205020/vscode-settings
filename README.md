# vscode-settings

Visual Studio Code 個人設定與 Profile 設定範本。

## Profile 設定

目前提供的設定檔：

| Profile | 設定檔 | 說明 |
| --- | --- | --- |
| Default | [`profile.default.settings.jsonc`](./profile.default.settings.jsonc) | 通用編輯器、終端機、Git、GitHub Copilot 與擴充功能設定 |

設定檔採用 JSONC 格式，包含註解，便於了解各項設定用途。檔案中的大部分設定可套用於 User Settings；部分擴充功能設定則需要安裝相應擴充功能才能生效。

## Default Profile 設定內容

### GitHub Copilot 與 Chat

- 為多種檔案類型啟用 Copilot，純文字檔除外。
- 對 Chat 編輯要求的移除與重試顯示確認提示。
- 停用 VS Code 遙測，並啟用 Copilot 下一步編輯建議。

### 編輯器與格式

- 字型大小為 16、行高為 22，並設定 120 字元的垂直尺標。
- 一般縮排使用 2 個空格；C# 與 Java 使用 4 個空格。
- 啟用貼上及儲存時格式化、括號配對上色、平滑游標動畫、字詞自動換行與多游標。
- 儲存時明確觸發修正程式碼動作；依語言指定 JSON、JSONC、YAML 與 Markdown 格式化工具。
- 啟用 Inlay Hints 留白及本機符號優先建議。

### 檔案、搜尋與工作區

- 視窗切換時自動儲存，並在儲存時移除行尾空白與多餘結尾空行。
- 自動偵測檔案編碼、搜尋結果顯示行號，並啟用麵包屑導覽。
- 為 Dockerfile、`.csproj` 及 `.bazelrc` 指定檔案語言。
- 設定不受信任檔案的開啟行為為直接開啟；使用前請依自己的安全需求確認此設定。

### 外觀與終端機

- 使用 Atom One Dark 色彩主題及 vscode-icons 圖示主題，並自訂註解及搜尋比對文字顏色。
- 啟用 Minimap，但不顯示其字元；Markdown 編輯器則關閉 Minimap。
- 設定終端機字型與 14 號字體；Windows 預設終端機為 PowerShell。
- 啟用編輯器滑鼠滾輪縮放，並設定未命名檔案只顯示檔名。

### Git

- 啟用遠端自動擷取、智慧提交及同步時使用 rebase。
- 關閉同步確認提示與提交簽章，並顯示已暫存變更區塊。

### 語言與擴充功能

- 設定 YAML 格式化與單引號選項，並啟用 YAML 驗證。
- 包含 Live Server、Docker、Red Hat YAML、Highlight Line、Better Comments、Power Mode 及 GitLens 等擴充功能的設定。
- 停用 VS Code 自動推薦擴充功能；Markdown 預覽中的連結會在編輯器內開啟。
- 提供 OpenAPI 及 markdownlint 設定檔的 JSON Schema 對應。

> 字型、色彩主題、格式化工具與擴充功能 ID 需依本機安裝項目調整。終端機預設 Profile 僅指定 Windows；其他平台可在各自的 VS Code 設定中選擇終端機。

## 套用設定

1. 在 VS Code 切換到要設定的 Profile。
2. 開啟命令選擇區，執行 **Preferences: Open User Settings (JSON)**。
3. 將所需設定合併至該 Profile 的 `settings.json`，避免覆蓋已有且不相關的設定。
4. 安裝設定中使用的主題、字型及擴充功能，並檢查平台專屬選項。

## 新增 Profile 設定

新增其他設定範本時，請使用 `profile.<名稱>.settings.jsonc` 命名，並在上方的 Profile 清單加入用途說明。設定檔應保留必要註解，並避免把帳號、權杖或其他機敏資料放入版本控制。
