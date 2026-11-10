# 遊戲盒典藏室 — GitHub Pages 收藏網站

這是「左側遊戲清單／右側 3D 遊戲盒」的美化版，純靜態網站，不需要資料庫或 Python。首頁是 `index.html`，樣式在 `style.css`，清單互動在 `site.js`，收藏資料在 `catalog.js`，製作工具是 `builder.html`。

## 放到 GitHub Pages

1. 在 GitHub 新增公開儲存庫，例如 `gamebox-gallery`。
2. 將 ZIP **解壓縮後，裡面的所有檔案與資料夾**（不是整個 ZIP）上傳到儲存庫根目錄。
3. 到 **Settings → Pages**，在 **Build and deployment** 選 **Deploy from a branch**，指定 `main`、`/(root)`，儲存。
4. 上線網址通常為 `https://你的帳號.github.io/gamebox-gallery/`。GitHub 完成部署後即可開啟。

## 新增遊戲

1. 使用首頁右上「盒裝製作工坊」（`builder.html`）上傳展開圖，裁切調整並匯出單一 HTML。
2. 將該 HTML 命名為英文檔名，例如 `sentimental-graffiti.html`，上傳到 `boxes/` 資料夾。
3. 編輯 `catalog.js`，在 `window.GAME_BOXES` 陣列中加入：

```js
{
  id: 'sentimental-graffiti',
  title: '青澀寶貝',
  year: '1998',
  platform: 'PC',
  maker: '遊戲公司名稱',
  description: '這裡寫你的個人收藏介紹。',
  file: 'boxes/sentimental-graffiti.html',
  cover: 'covers/sentimental-graffiti.jpg'
},
```

4. 封面縮圖為選填。若設定 `cover`，請建立 `covers/` 並上傳相對應圖片；不設定可寫 `cover: ''`，網站會顯示預設圖示。
5. 請移除原先 `catalog.js` 的 `demo` 示範資料，必要時也刪除 `boxes/demo.html`。將變更提交到 GitHub 後，網站會更新。

## 使用技巧

- 左側可搜尋遊戲名稱、年份、平台與製作公司；可依平台篩選、名稱或年份排序。
- 點選左側遊戲切換右側的 3D 盒裝；手機版清單改為橫向滑動。
- 點「複製連結」即可分享指定遊戲的網址，例如 `https://你的帳號.github.io/gamebox-gallery/#sentimental-graffiti`。
- 「獨立檢視」可在新分頁開啟該遊戲盒的展示頁面。
- 3D 旋轉、縮放、六面切換功能由每一個 `boxes/` 內的 HTML 實作，首頁不會覆蓋它的功能。
- 製作工坊的圖片不會自動上傳 GitHub：需要匯出 HTML 後，再手動上傳 `boxes/` 並編輯 `catalog.js`。
- 介面 Google Fonts 需網路才能載入；離線時會自動使用系統字型，不影響其他功能。
