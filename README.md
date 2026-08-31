# 教室座位表產生器｜Classroom Seating Chart Generator

可拖放交換、匯出 Excel/PDF，並直接上傳座位資料到 GitHub 的網頁版教室座位表工具。支援自動從 GitHub 載入最新座位，並在本機儲存設定避免重複輸入 Token。

## 功能特色

- 🪑 **可調整座位配置**：支援每排 5、6、7、8 個座位
- 🖱️ **直覺拖放交換**：學生 ↔ 座位、座位 ↔ 座位、座位 → 名單（絕不移除學生）
- 📊 **自動填滿**：依人數自動排列，支援逐排、逐欄、依班級座號排序
- 📥 **匯出多種格式**：Excel (.xlsx)、PDF、JSON
- 📤 **GitHub 整合**：直接從網頁上傳座位資料到 GitHub 儲存庫
- 🔄 **自動載入**：重新整理網頁後自動從 GitHub 讀取最新座位
- 💾 **本機儲存設定**：Token 儲存在瀏覽器，避免重複輸入
- 🌐 **純前端運作**：無需伺服器，瀏覽器即可使用
- 📱 **響應式設計**：支援桌面與平板裝置

## 快速開始

### 方法一：GitHub Pages（推薦）

1. 開啟網站：https://dfleoyang-HLHS.github.io/2026113/
2. 第一次使用時，輸入 Personal Access Token
3. 上傳點名表或使用範例資料
4. 調整座位排列
5. 點選「上傳座位資料到 GitHub」
6. 下次開啟：**自動載入最新座位，Token 已自動填入**

### 方法二：本機使用

1. 下載 `index.html`
2. 使用 Chrome、Edge 或 Firefox 開啟
3. 開始使用

## 使用說明

### 第一次設定 Token

1. 取得 Personal Access Token：
   - 前往 https://github.com/settings/tokens?type=beta
   - 建立 Fine-grained token
   - 授權儲存庫 `2026113`
   - 設定 **Contents** 為 **Read and write**
   - 複製 Token

2. 在網頁中填寫：
   - GitHub 使用者名稱：`dfleoyang-HLHS`（已預設）
   - 儲存庫名稱：`2026113`（已預設）
   - Personal Access Token：貼上你的 Token
   - 分支：`main`（已預設）
   - 檔案路徑：`seating_data.json`（已預設）

3. 點選「上傳座位資料到 GitHub」

**完成後，Token 會儲存在本機瀏覽器，下次開啟自動填入。**

### 上傳點名表

1. 點選「上傳點名表」
2. 選擇 `.xlsx`、`.xls` 或 `.csv` 檔案
3. 系統自動辨識欄位：學號、班級、座號、姓名

### 調整座位

- **每排座位數**：選擇 5、6、7、8
- **排列方式**：
  - 由前到後、逐排填入
  - 由左到右、逐欄填入
  - 依班級與座號排序
- **自動填滿**：一鍵依設定排列
- **拖放調整**：
  - 從名單拖到空座位
  - 座位之間直接交換（兩人都会保留）
  - 拖回名單取消入座

### 匯出資料

- **下載 Excel**：包含座位、班級、座號、姓名、學號
- **下載 PDF**：座位表視覺化圖档
- **下載 JSON**：結構化座位資料
- **列印**：使用瀏覽器列印功能

### 從 GitHub 載入座位

- **自動載入**：頁面載入時自動從 GitHub 讀取
- **手動載入**：點選「從 GitHub 載入座位」按鈕

### 管理儲存的 Token

- **清除 Token**：點選「清除儲存的 Token」按鈕
- **重新輸入**：清除後，下次使用時需重新輸入 Token

## 檔案結構

```
2026113/
├── index.html              # 網頁版主程式
├── seating_data.json       # 座位資料（由網頁上傳）
└── README.md               # 說明文件
```

## JSON 資料格式

```json
{
  "title": "教室座位表 Classroom Seating Chart",
  "updatedAt": "2026-08-31T11:14:00.000Z",
  "totalStudents": 32,
  "layout": {
    "seatsPerRow": 6,
    "rows": 6,
    "arrangement": "row"
  },
  "seats": [
    {
      "seat": 1,
      "studentId": "310273",
      "className": "301",
      "number": "03",
      "name": "余賽亞"
    }
  ]
}
```

## 拖放規則

| 拖曳來源 | 拖曳目標 | 結果 |
|----------|----------|------|
| 座位 A（有學生） | 座位 B（空位） | 學生移到座位 B |
| 座位 A（有學生） | 座位 B（有學生） | **兩人交換座位** |
| 名單（未入座） | 座位 A（空位） | 學生入座 |
| 名單（未入座） | 座位 A（有學生） | 原學生回名單，新學生入座 |
| 座位 A（有學生） | 左側名單 | 學生取消入座 |

## 技術堆疊

- **HTML5** + **CSS3**（響應式設計）
- **Vanilla JavaScript**（無框架依賴）
- [SheetJS / xlsx](https://sheetjs.com/) - Excel 匯出
- [jsPDF](https://parall.ax/products/jspdf) - PDF 產生
- [html2canvas](https://html2canvas.hertzen.com/) - 畫面擷取
- **GitHub API** - 座位資料上傳與載入
- **LocalStorage** - 本機儲存設定

## 隱私與安全

- 所有資料處理均在瀏覽器本機完成
- 學生資料不儲存到伺服器
- Personal Access Token 儲存在瀏覽器 LocalStorage
- Token 僅用於與 GitHub API 的連線
- 不會傳送到其他伺服器
- 建議使用 Fine-grained token 並限制單一儲存庫權限
- 每台設備（電腦、手機）需分別設定一次

## 瀏覽器相容性

- ✅ Chrome 90+
- ✅ Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+

## 常見問題

### Q: 為什麼重新整理後座位消失了？
A: 請確認已先上傳座位資料到 GitHub。頁面載入時會自動從 GitHub 讀取最新資料。

### Q: Token 儲存在哪裡？
A: Token 儲存在瀏覽器的 LocalStorage，僅限本网頁使用。

### Q: 如何在多台設備使用？
A: 每台設備需分別輸入 Token 一次，之後會各自儲存。

### Q: 如何清除儲存的 Token？
A: 點選「清除儲存的 Token」按鈕，或清除瀏覽器資料。

## 授權

本專案供教育用途使用。

## 聯絡與回饋

如有問題或建議，歡迎透過 GitHub Issues 提出。