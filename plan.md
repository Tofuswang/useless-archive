# Navbar + 關於我 & Blog 頁面規劃

## 目前狀態
- 純靜態 HTML 網站，無框架
- 風格：Noto Serif TC 字體、奶白底色 (#faf9f6)、極簡排版
- 頁面：`index.html`（首頁）、`blog/first-post.html`（文章頁）

---

## 規劃內容

### 1. 新增 Navbar（所有頁面共用）

在每個頁面最上方（`<body>` 開頭）加入一個 `<nav>` 元素，風格與現有設計一致：

```
┌─────────────────────────────────────────────┐
│  無用資料庫          關於我    Blog          │
│  (← 點擊回首頁)      (連結)   (連結)        │
└─────────────────────────────────────────────┘
```

- **左側**：網站名稱「無用資料庫」，點擊回到首頁
- **右側**：「關於我」和「Blog」兩個連結
- 風格：同字體、小字號 (0.85rem)、不加底線、hover 變色
- 與 `header-rule`（粗橫線）整合，navbar 在橫線上方
- 響應式：手機上也維持一行排列（字夠小不會換行）

### 2. 新增「關於我」頁面 (`about.html`)

在根目錄建立 `about.html`，內容類似履歷/自我介紹：

- 頁面結構與 blog 文章頁一致（同樣的排版風格）
- 包含以下區塊：
  - **名字 + 簡介**：大標題 + 一段自我介紹
  - **經歷**：工作 / 學歷等（先放 placeholder 讓你填寫）
  - **聯絡方式**：email / social links 的預留位置
- 頁面也包含 navbar

### 3. 調整首頁 (`index.html`)

- 加入 navbar
- Blog 區塊保持不變（navbar 的 Blog 連結指向 `index.html#blog`，用錨點滾動到 blog 區段）
- 在 blog 列表的 `<h2>Blog</h2>` 加上 `id="blog"` 方便錨點定位

### 4. 更新 Blog 文章頁 (`blog/first-post.html`)

- 加入 navbar（路徑需調整為 `../index.html`、`../about.html`）
- 移除底部「← 回到無用資料庫」連結（因為 navbar 已有導航功能）

---

## 需要修改的檔案

| 檔案 | 改動 |
|------|------|
| `index.html` | 加 navbar、blog 區段加 id 錨點 |
| `about.html` | **新建**，關於我頁面 |
| `blog/first-post.html` | 加 navbar、移除底部返回連結 |

## 實作順序

1. 先改 `index.html`：加入 navbar CSS + HTML
2. 新建 `about.html`：套用相同風格 + navbar
3. 改 `blog/first-post.html`：加入 navbar
4. 測試所有頁面的連結是否正確
