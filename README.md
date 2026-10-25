# GourmetLog · 美食秘菜單點餐紀錄系統

[![Cloudflare Pages](https://img.shields.io/badge/demo-mygourmet--bv6.pages.dev-F38020?style=flat-square&logo=cloudflare)](https://mygourmet-bv6.pages.dev/)
[![Netlify](https://img.shields.io/badge/mirror-mygourmet.netlify.app-00C7B7?style=flat-square&logo=netlify)](https://mygourmet.netlify.app/)
[![Built with](https://img.shields.io/badge/stack-HTML%20%7C%20Tailwind%20%7C%20Vanilla%20JS-38BDF8?style=flat-square)](#技術架構)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

個人數位美食紀錄＋模擬點餐介面。以繁體中文（香港）為主，另支援 English；資料只存在瀏覽器本機，無需登入、無需後端。

**建議線上體驗（Cloudflare Pages）：** [https://mygourmet-bv6.pages.dev/](https://mygourmet-bv6.pages.dev/)  
**鏡像（Netlify）：** [https://mygourmet.netlify.app/](https://mygourmet.netlify.app/)

> 兩個網址可並存；本機資料（IndexedDB／localStorage）按網域分開，唔會自動互通。換裝置或換網域前請先「匯出 JSON」。

---

## 專案簡介

GourmetLog 把「餐廳菜單瀏覽」同「個人食記」合喺同一個輕量網頁：用可以自訂店名嘅範例冰室（預設「荃港大冰室」）展示點餐流程，同時支援新增、篩選、統計同備份你自己嘅美食紀錄。

適合用作：

- 前端作品集（靜態站、手機走位、本機儲存）
- 教學示範（IndexedDB、單頁互動、Git → Pages／Netlify）
- 個人食記／模擬點餐小工具

---

## 版本（摘要）

| 版本 | 重點 |
|------|------|
| **1.8d1**（現行） | IndexedDB 存菜式與相片 Blob；空庫會寫入示範資料；英文 UI 補齊；統計計算修復 |
| 1.8c–1.8b | 手機走位：FAB／toast／頂欄溢出、歡迎層 scrollbar |
| 1.8 | 手機版 layout 迭代 |
| 1.7 | 繁中／English 切換（`gourmet_lang`） |

現行介面版本號見設定頁 badge（目前 **v1.8d1**）。

---

## 主要功能

| 功能 | 說明 |
|------|------|
| 菜單瀏覽 | 分類、搜尋、評分篩選、排序 |
| 模擬點餐 | 「今日點單」購物車、模擬送出 |
| 美食紀錄 | 新增／編輯／刪除（含確認）、詳情與統計；可上載並壓縮相片 |
| 本機儲存 | **IndexedDB**（`items`＋`photos`）；語言與店名仍用 `localStorage` |
| 資料備份 | 匯出／匯入 JSON（含相片 base64 交換欄）；換機請匯出後再匯入 |
| 餐牌輸出 | 列印／匯出餐牌（瀏覽器列印轉 PDF） |
| 語言切換 | 繁中／English；歡迎頁與標題列可切換 |
| 響應式 | 桌面＋手機（含窄屏走位適配） |

---

## 技術架構

- **前端：** 單一靜態頁 `index.html`
- **樣式：** [Tailwind CSS](https://tailwindcss.com/)（CDN）
- **圖示：** Font Awesome
- **字型：** Plus Jakarta Sans、Noto Sans TC
- **狀態：** IndexedDB（菜式／相片）＋ `localStorage`（語言、店名）
- **託管：** [Cloudflare Pages](https://pages.cloudflare.com/) 與／或 [Netlify](https://www.netlify.com/)（同一 GitHub repo 可兩邊自動部署）

---

## 快速開始

### 本機預覽

```bash
# 若已安裝 Python 3
python3 -m http.server 8080
```

瀏覽器打開 `http://localhost:8080`。亦可直接開啟 `index.html`（建議用 static server）。

### 部署到 Cloudflare Pages（建議）

1. Workers & Pages → **Create** → 揀 **Pages** 分頁（唔好揀 Workers／`wrangler deploy`）
2. Import Git repo：`eggrollrollroll/mygourmet`
3. Framework：**None**；Build command：留空或 `exit 0`；**Build output directory：** `/`
4. Production branch：`main`

### 部署到 Netlify（可並存）

1. Import from Git → 同一個 repo  
2. Build command：留空；Publish directory：`.`  
3. 每次 `push` 到預設分支會自動部署  

---

## 資料與私隱

- 菜式、評分、筆記、本機相片均只存放於使用者裝置（IndexedDB／localStorage）
- 本專案不收集帳號、不經伺服器上傳食記內容
- **升級或清除網站資料前，請先「匯出 JSON 備份」**；新版唔會自動遷移舊版 `localStorage` 大圖資料，請用匯入還原
- Cloudflare Pages 與 Netlify 係兩個 origin，資料互不相通

---

## 專案結構（簡要）

```text
.
├── index.html      # 主程式與介面
├── README.md       # 本說明
├── LICENSE         # 授權條款
└── .gitignore
```

---

## 開發備註

- 目標瀏覽器：現代桌面瀏覽器；流動版 Safari／Chrome 已針對匯出、篩選列、窄屏走位做適配
- iPhone 匯出 JSON：會優先開啟系統分享選單，請選擇「儲存到檔案」
- 歡迎以 Issue／Pull Request 提出改善建議

---

## 授權

本專案採用 [MIT License](LICENSE) 授權。你可以自由使用、修改與分享，惟需保留版權聲明。

---

## 作者

個人前端練習／作品集專案。

- Demo（Pages）：[mygourmet-bv6.pages.dev](https://mygourmet-bv6.pages.dev/)
- Demo（Netlify）：[mygourmet.netlify.app](https://mygourmet.netlify.app/)
