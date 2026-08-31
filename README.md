# 彈性班級座位表系統

## 功能特色

- **彈性排數**：支援 5 排、6 排、7 排等不同教室配置
- **彈性列數**：根據人數自動調整
- **多班級支援**：每個班級獨立設定
- **男生淺藍色、女生淺粉紅色**
- 本地儲存 + GitHub 雲端同步
- 下載 Excel 座位表
- 列印 / 另存 PDF

## config.json 設定說明

```json
{
  "class": {
    "name": "班級名稱",
    "rows": 6,
    "cols": 6,
    "total": 36,
    "students": [
      {"no":1,"name":"姓名","gender":"男","style":"風格"},
      ...
    ]
  },
  "github": {
    "owner": "GitHub 使用者名稱",
    "repo": "Repository 名稱",
    "branch": "main"
  }
}
```

### 欄位說明

- `name`：班級名稱（例如：101 班、102 班、113 班）
- `rows`：教室排數（5、6、7 皆可）
- `cols`：每排的列數（根據人數調整）
- `total`：學生總人數
- `students`：學生名單（包含座號、姓名、性別、風格）

## 使用方式

1. 修改 `config.json` 中的班級資訊。
2. 上傳 `index.html` 和 `config.json` 到 GitHub。
3. 啟用 GitHub Pages。
4. 開啟網頁，按「設定」輸入 token。
5. 拖曳座位調整。
6. 按「下載 Excel 座位表」或「列印 / 存 PDF」匯出檔案。

## 多班級管理

每個班級使用獨立的 `config.json` 和 repository：

- 101 班：`config-101.json` + `2026101` repository
- 102 班：`config-102.json` + `2026102` repository
- 113 班：`config.json` + `2026113` repository

或者將所有班級的 `config.json` 放在不同資料夾中。
