# 📈 存股追蹤

以 GitHub Gist 為資料庫的輕量存股追蹤網站，無需後端、免費部署，跨裝置同步持倉資料。

<!-- **Demo：** `https://你的帳號.github.io/stock-tracker/` -->

---

## 功能

- 新增／刪除持股（代碼、名稱、股數、平均成本）
- 一鍵更新現價（Yahoo Finance）
- 自動計算未實現損益與報酬率
- 資料存於私人 GitHub Gist，跨裝置同步
- 支援台股（自動加 `.TW`）與美股
- 深色模式自動切換

---

## 部署方式

### 1. Fork 或上傳檔案

將 `index.html` 放到 GitHub repo 的根目錄。

### 2. 開啟 GitHub Pages

進入 repo → **Settings** → **Pages** → Source 選 `main` branch → **Save**

幾分鐘後網站會在以下網址上線：

```
https://<你的帳號>.github.io/<repo名稱>/
```

---

## 使用方式

### 第一次設定

1. 前往 [GitHub Token 設定頁](https://github.com/settings/tokens)
2. 點擊 **Generate new token (classic)**
3. 勾選 `gist` 權限，生成 Token（格式：`ghp_xxx...`）
4. 打開網站，貼上 Token，**Gist ID 留空**
5. 點擊「連接 Gist」→ 系統自動建立私人 Gist 並顯示 Gist ID
6. **記下 Gist ID**，之後在其他裝置登入時使用

### 日常使用

| 動作 | 說明 |
|------|------|
| 新增持股 | 輸入代碼、名稱、股數、平均成本 |
| 更新股價 | 點擊「更新股價」從 Yahoo Finance 抓取現價 |
| 刪除持股 | 點擊該列右側 ✕ 按鈕 |
| 換裝置 | 輸入同一組 Token + Gist ID 即可讀取資料 |

### 股票代碼格式

- **台股**：輸入數字代碼即可，如 `2330`（系統自動轉為 `2330.TW`）
- **美股**：直接輸入代碼，如 `AAPL`、`NVDA`

---

## 資料安全

- Token 與 Gist ID 僅儲存於**本機瀏覽器 localStorage**，不會傳送到任何第三方伺服器
- Gist 建立時設為 **private**，只有 Token 擁有者可讀寫
- 本專案為純靜態網頁，無後端、無資料庫、無第三方追蹤

---

## 技術說明

| 項目 | 說明 |
|------|------|
| 資料儲存 | GitHub Gist API（`stocks.json`） |
| 股價來源 | Yahoo Finance 非官方 API |
| 部署平台 | GitHub Pages（純靜態） |
| 相依套件 | 無，單一 HTML 檔案 |

---

## 限制

- 股價為**非即時**資料，有數分鐘至數十分鐘延遲
- Yahoo Finance API 為非官方，偶有不穩定情況
- GitHub API 有速率限制（每小時 60 次未認證 / 5000 次已認證），一般使用不受影響

---

## License

MIT