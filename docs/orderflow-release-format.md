# OrderFlow 正式版本資訊格式

此文件說明 OrderFlow 後續版本偵測的發布格式。此文件及 testing 目錄中的資料不是正式 Release，也不表示任何新版本已發布。

## 正式來源與識別

- 正式來源：`https://api.github.com/repos/zhai93926-create/FlowLab-Releases/releases`。
- OrderFlow 正式標籤格式：`orderflow/v主版本.次版本.修訂版`，例如 `orderflow/v2.1.10`。此例僅為格式示範，並非已發布版本。
- BatchRemarks 使用 `batchremarks/v...`；未來溫大醫可使用獨立 `wendayi/v...`。不同工具必須分別篩選、比較及保存快取。
- 只納入非 Draft、非 Pre-release、標籤為工具名稱加純數字版本的正式 Release。Beta、測試、其他工具與無法驗證的資料必須排除。
- 比較 `manifest.json` 的數字版本，逐段按數值比較，不按文字字典序比較。相同版本不提示；含 Beta 顯示名稱但數字相同時仍視為相同。
- 發現較新正式版時，提示使用者並提供 FlowLab 發布頁；正式安裝檔依既定流程放在 Google Drive。不得自動下載、安裝或覆蓋。
- 開啟工具時可檢查，建議同工具的介面共用 60 分鐘快取；網路或資料異常不影響其他功能。手動檢查如支援，應區分無版本與連線失敗。

## 測試資料

`testing/orderflow-fixtures.json` 僅供模擬測試；它是普通檔案，不屬於 GitHub Releases，不會使已安裝工具收到正式更新通知。測試程式必須明確指向該檔；正式程式不得讀取測試資料。正式資料應以 GitHub Releases 的實際 `draft`、`prerelease`、`tag_name`、`html_url` 等欄位判定，並驗證 Release 的來源及連結。

此階段未修改 OrderFlow 程式，亦未建立任何 OrderFlow 正式 Release。
