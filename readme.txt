# YouTube 企劃模擬器

這是一個雲端協作工具，旨在讓內容創作者模擬 YouTube 介面，測試不同影片企劃的受歡迎程度。

## 核心架構

本專案採用「前端渲染」搭配「Google Apps Script 作為無伺服器後台 (Serverless Backend)」的架構。

-   **前端 (`index.html`, `stats.html`)**: 使用者介面，負責渲染與互動。
-   **後台 (Google Apps Script)**: 作為唯一的「單一事實來源」，綁定至 Google Sheet。

---

## 後台部署指南 (Google Apps Script)

這是讓整個專案能成功運作的關鍵。請將以下程式碼部署為一個網路應用程式。


### 步驟：

1.  在 Google Sheet 中，點擊 `擴充功能 > Apps Script`。
2.  將下方完整的程式碼貼入編輯器。
3.  點擊 `部署 > 新增部署`。
4.  設定類型為 `網路應用程式`。
5.  **執行身份** 選擇 `我`。
6.  **誰可以存取** 選擇 `任何人`。
7.  點擊「部署」，並複製產生的網址。
8.  將此網址更新至 `index.html` 和 `stats.html` 的 `SCRIPT_URL` 常數中。


### Apps Script 程式碼
```javascript
const SHEET_ID = '【請貼上您的 Google Sheet ID】';
const DB_SHEET_NAME = 'VideoDatabase';


**請注意：**
請務必將上方 `【請貼上您的 Google Sheet ID】` 替換成您自己的 Sheet ID，並將完整的 Apps Script 程式碼填入。這樣，未來的您或任何協作者，都能快速地重新部署這個專案。