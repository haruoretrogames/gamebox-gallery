# 哈魯歐遊戲盒典藏室｜分類清單更新包

這是針對已建立的 https://haruoretrogames.github.io/gamebox-gallery/ 的**增量更新**，不是整站重建。

## 上傳哪些檔案？

在 GitHub Repo `haruoretrogames/gamebox-gallery` 根目錄，上傳並覆蓋：

- `index.html`：移除首頁右上角「盒裝製作工坊」與管理入口，增加分類列。
- `site.js`：分類、搜尋、收合、清單獨立捲動。
- `style.css`：新清單樣式與手機適配。
- `admin.html`、`admin.js`：管理表單新增「遊戲分類」欄位（不需要你寫語法）。
- `admin.css`：原有管理介面樣式，方便第一次完整安裝後台。

**請勿刪除或覆蓋你原有的 `catalog.js`、`boxes/`、`covers/`**，以免已加入的遊戲遺失。

## 讓盒裝製作工具不再公開

右上角按鈕已移除，但 GitHub Pages 是公開的靜態網站；若 Repo 仍存在 `builder.html`，任何知道網址的人都能開啟。

要移除公開工具：
1. 先將 `builder.html` 備份下載到自己電腦，之後在電腦上離線製作盒裝。
2. 到 GitHub Repository 點開 `builder.html`，選擇刪除檔案 (Delete file)，Commit changes。
3. 確認 GitHub Pages 部署成功後，`/builder.html` 才會不再由該網站提供。注意公開儲存庫歷史紀錄可能仍保留舊檔；若需要真正限制存取，必須放在私人位置，不要發布到公開 Repo。

## 分類邏輯

`admin.html` 的「遊戲分類」可以選既有類別或自由輸入。例如「角色扮演」、「策略戰棋」、「益智／模擬」、「動作冒險」。只要按發布，這個分類會儲存在 `catalog.js` 對應遊戲的 `category` 欄位。

既有遊戲若沒有 `category`，展示館會對少數常見遊戲標題做初步分類；其他暫列「未分類」，仍可正常顯示。登入 `admin.html` 修改分類即可。分類按鈕會自動根據收藏資料產生，不需要再動程式。

**管理頁位置**：`https://haruoretrogames.github.io/gamebox-gallery/admin.html`。為避免一般訪客看到管理入口，首頁沒有提供連結。但它仍是公開可訪問的頁面，真正的修改權限取決於你的 GitHub Token。請務必使用限定 Repo、期限短、Contents Read/Write 的 token，切勿將 token 上傳到網站。

## 注意

這份 ZIP 不含 `builder.html`、`catalog.js` 或任何遊戲盒圖檔，因此不會把原有收藏覆蓋成示範資料。重新部署通常需幾分鐘，若看起來沒變，強制重新整理瀏覽器。
