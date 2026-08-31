# 113 班座位表（含 GitHub 雲端同步）

將 `index.html` 上傳至 GitHub repository，即可用 GitHub Pages 部署。

## GitHub Pages 部署

1. 建立 repository（例如：`class113-seating`）。
2. 上傳 `index.html` 到 repository 根目錄。
3. 進入 **Settings → Pages**。
4. 在 **Build and deployment** 中選擇：
   - Source：`Deploy from a branch`
   - Branch：`main`
   - Folder：`/ (root)`
5. 按下 **Save**，稍後即可透過 GitHub Pages 網址開啟座位表。

## 第一次使用：設定 GitHub 上傳

1. 在 GitHub 產生 Personal Access Token（classic）：
   - 網址：https://github.com/settings/tokens
   - 勾選 **repo** 權限。
   - 複製產生的 token。
2. 開啟座位表網頁，按下「上傳最新版本到 GitHub」。
3. 依提示輸入：
   - GitHub 使用者名稱（owner）
   - Repository 名稱（不含 owner）
   - Branch 名稱（預設 `main`）
   - Personal Access Token
4. 設定完成後，網頁會將目前的座位表上傳到 repository 中的 `seating.json`。

## 之後使用

- 每次調整座位後，按下「上傳最新版本到 GitHub」即可同步到雲端。
- 下次開啟網頁時，會自動從 GitHub 載入 `seating.json` 的最新版本。
- 若未設定 GitHub 或載入失敗，則使用本地瀏覽器儲存的版本。

## 注意

- 座位資料會同時存在：
  - 本地：瀏覽器的 `localStorage`
  - 雲端：GitHub repository 中的 `seating.json`
- 請妥善保管 Personal Access Token，不要分享給他人。
