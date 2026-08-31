# 彈性班級座位表（含 GitHub 上傳）

## 功能

- 拖曳調整座位（電腦滑鼠 / 手機長按）
- 本地儲存座位配置
- **上傳至 GitHub**（repository: `2026113`, branch: `main`）
- 下載 Excel 座位表
- 列印 / 另存 PDF
- 重新設定教室排數與人數

## 使用方式

1. 用瀏覽器開啟 `index.html`（可直接雙擊檔案或透過 GitHub Pages）。
2. 按「重新設定教室」設定排數與人數。
3. 拖曳調整座位。
4. 按「上傳最新版本到 GitHub」：
   - 第一次會要求輸入 Personal Access Token（需 repo 權限）
   - 產生 token：https://github.com/settings/tokens
   - 勾選 **repo** 權限
5. 上傳成功後，座位資料會儲存在 repository 中的 `seating-113 班.json`。
6. 下次開啟網頁時，會自動從 GitHub 載入最新版本。

## 檔案

- `index.html`：座位表網頁
- `config.json`：班級與學生名單設定
- `README.md`：說明
