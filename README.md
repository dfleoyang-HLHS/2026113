# 113 班座位表（含 GitHub 雲端同步）

將以下三個檔案上傳至同一個 GitHub repository，即可用 GitHub Pages 部署。

## 檔案說明

- `index.html`：座位表網頁主程式。
- `config.json`：GitHub 設定檔（owner、repo、branch）。
- `seating.json`：座位表資料（由網頁自動建立與更新）。

## 第一次使用：設定 GitHub 上傳

1. 在 GitHub 產生 Personal Access Token（classic）：
   - 網址：https://github.com/settings/tokens
   - 勾選 **repo** 權限。
   - 複製產生的 token。
2. 在 GitHub repository 中編輯 `config.json`，修改以下欄位：
   ```json
   {
     "owner": "your-github-username",
     "repo": "class113-seating",
     "branch": "main"
   }
   ```
   - `owner`：您的 GitHub 使用者名稱。
   - `repo`：這個 repository 的名稱（不含 owner）。
   - `branch`：分支名稱（預設 `main`）。
3. 開啟座位表網頁，按下「設定」按鈕。
4. 輸入 Personal Access Token，按下確定。
5. 調整座位後，按下「上傳最新版本到 GitHub」，即可將座位表上傳到 repository 中的 `seating.json`。

## GitHub Pages 部署

1. 建立 repository（例如：`class113-seating`）。
2. 上傳 `index.html`、`config.json` 到 repository 根目錄。
3. 進入 **Settings → Pages**。
4. 在 **Build and deployment** 中選擇：
   - Source：`Deploy from a branch`
   - Branch：`main`
   - Folder：`/ (root)`
5. 按下 **Save**，稍後即可透過 GitHub Pages 網址開啟座位表。

## 之後使用

- 每次調整座位後，按下「上傳最新版本到 GitHub」即可同步到雲端。
- 下次開啟網頁時，會自動從 GitHub 載入 `seating.json` 的最新版本。
- 若未設定 GitHub 或載入失敗，則使用本地瀏覽器儲存的版本。

## 注意

- 座位資料會同時存在：
  - 本地：瀏覽器的 `localStorage`
  - 雲端：GitHub repository 中的 `seating.json`
- 請妥善保管 Personal Access Token，不要分享給他人。
- `config.json` 可公開，但 token 請只在網頁中輸入，不要寫進任何公開檔案。
