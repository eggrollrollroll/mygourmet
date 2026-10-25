# GourmetLog · 美食秘菜單點餐紀錄系統

[![Live Demo](https://img.shields.io/badge/demo-mygourmet.netlify.app-00C7B7?style=flat-square&logo=netlify)](https://mygourmet.netlify.app/)
[![Built with](https://img.shields.io/badge/stack-HTML%20%7C%20Tailwind%20%7C%20Vanilla%20JS-38BDF8?style=flat-square)](#技術架構)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

個人數位美食紀錄＋模擬點餐介面。以繁體中文（香港）為主，資料只存在瀏覽器本機，無需登入、無需後端。

**線上體驗：** [https://mygourmet.netlify.app/](https://mygourmet.netlify.app/)

---

## 專案簡介

GourmetLog 把「餐廳菜單瀏覽」同「個人食記」合喺同一個輕量網頁：用可以自訂店名嘅範例冰室（預設「荃港大冰室」）展示點餐流程，同時支援新增、篩選、統計同備份你自己嘅美食紀錄。

適合用作：

- 前端作品集（靜態站、UI／UX、無障礙小修）
- 教學示範（`localStorage`、單頁互動、Netlify 部署）
- 個人食記／模擬點餐小工具

---

## 版本

- **1.7：** 介面支援繁體中文／English 切換（歡迎頁與標題列），語言偏好存於 `localStorage`（`gourmet_lang`）。

## 主要功能

| 功能 | 說明 |
|------|------|
| 菜單瀏覽 | 分類、搜尋、評分篩選、排序 |
| 模擬點餐 | 「今日點單」購物車、數量合併、模擬送出 |
| 美食紀錄 | 新增／編輯／刪除（含確認）、詳情與統計 |
| 資料備份 | 匯出／匯入 JSON；iPhone 優先用系統分享「儲存到檔案」 |
| 餐牌輸出 | 匯出／列印專屬餐廳餐牌 |
| 本機儲存 | 使用 `localStorage`，換裝置請自行匯出備份 |
| 語言切換 | 繁中／English；歡迎頁與標題列可切換 |

---

## 技術架構

- **前端：** 單一靜態頁（HTML）
- **樣式：** [Tailwind CSS](https://tailwindcss.com/)（CDN）
- **圖示：** Font Awesome
- **字型：** Plus Jakarta Sans、Noto Sans TC
- **狀態：** 瀏覽器 `localStorage`（無需伺服器資料庫）
- **託管：** [Netlify](https://www.netlify.com/)（可由 GitHub 自動部署）

---

## 快速開始

### 本機預覽

用任何靜態伺服器開啟專案根目錄即可，例如：

```bash
# 若已安裝 Python 3
python3 -m http.server 8080
```

瀏覽器打開 `http://localhost:8080`。

亦可以直接用瀏覽器開啟 `index.html`（部分瀏覽器對本機檔案權限較嚴，建議用簡單 static server）。

### 部署到 Netlify

1. 將本 repo 連接到 Netlify（Import from Git）
2. **Build command：** 留空（純靜態）
3. **Publish directory：** `.`（或放置 `index.html` 的資料夾）
4. 每次 `push` 到預設分支即會自動重新部署

---

## 資料與私隱

- 菜式、評分、筆記等均只存放於使用者裝置的瀏覽器儲存空間
- 本專案不收集帳號、不經伺服器上傳食記內容
- 清除網站資料或更換裝置前，請先使用「匯出 JSON 備份」

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

- 目標瀏覽器：現代桌面瀏覽器；流動版 Safari／Chrome 已針對匯出、篩選列做適配
- iPhone 匯出 JSON：會優先開啟系統分享選單，請選擇「儲存到檔案」
- 歡迎以 Issue／Pull Request 提出改善建議

---

## 授權

本專案採用 [MIT License](LICENSE) 授權。你可以自由使用、修改與分享，惟需保留版權聲明。

---

## 作者

個人前端練習／作品集專案。線上 Demo：[mygourmet.netlify.app](https://mygourmet.netlify.app/)
