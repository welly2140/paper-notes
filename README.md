# 論文整理

這是我用來整理論文閱讀筆記的網站，不限定領域，讀到什麼論文就整理什麼。以前讀完一篇論文，筆記常常散落在 PDF 的註解或手機備忘錄裡，過一陣子就找不到，所以想做一個格式固定、可以一直往下加的地方。

整理的工作大部分交給 AI。我在 AGENTS.md 裡寫好規則，包括每頁要有哪些區塊、檔案怎麼命名、標籤怎麼用，以及哪些事情 AI 不能做。這樣不管我用哪個 AI 工具、隔多久再回來加新論文，做出來的頁面格式都會一樣。

URL: https://welly2140.github.io/paper-notes/

## 新增一篇論文的流程

1. 把 PDF 放進 papers/inbox 資料夾。這個資料夾有寫在 .gitignore 裡，PDF 不會被傳上 GitHub。
2. 跟 AI 說：

   ```
   請依照 AGENTS.md 整理 papers/inbox/論文檔名.pdf
   ```

3. AI 會從範本複製一份新頁面，照規則填好內容，再順便更新首頁的論文列表和標籤頁。如果網站上已經有相關的論文，也會互相加上連結。
4. 我自己對照原文檢查一次，寫好我的心得，再跟 AI 說這篇已經校對完，頁面狀態就會從 AI 初稿改成已校對。
5. push 到 GitHub 之後，GitHub Pages 會自己更新。

我特別在規則裡要求 AI 每個重點都要標原文頁碼，論文沒寫的東西不能自己補。因為 AI 整理論文最怕的就是講得很順但內容是錯的，有頁碼的話，我回去核對會快很多。

## 專案結構

```
├── AGENTS.md            專案規則，給 AI 看
├── CLAUDE.md            只用來引入 AGENTS.md
├── index.html           首頁，論文總表
├── tags.html            標籤索引
├── assets/style.css     全站共用的樣式
└── papers/
    ├── _template.html   論文頁範本
    ├── inbox/           放 PDF，不會上傳
    └── *.html           每篇論文一頁
```

整個網站只有 HTML 和 CSS，沒有用框架，也不需要 build，直接用瀏覽器打開 index.html 就能看。

## 部署到 GitHub Pages

1. 把專案 push 到一個 public repo。
2. 進到 repo 的 Settings，點左邊的 Pages。
3. Source 選 Deploy from a branch，Branch 選 main，資料夾選 root，按 Save。
4. 等一兩分鐘，網站就會出現在上面那個網址。

## 關於版權

這裡只放我自己整理的筆記，不放論文 PDF，也不用論文裡的原圖。
