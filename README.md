# 炫采外牆有限公司 SKYWORKS｜GitHub Pages 完整官網

> 此專案是 2026/11/19 既有品牌官網的 **GitHub 專用部署包**。所有網站視覺、圖片、版型、文字與互動程式沿用原版本，沒有重新設計。

## 📦 專案結構

```text
<repository-root>/
├── index.html                          # 原版完整網站（HTML + CSS + JS）
├── assets/                             # 原版圖片、品牌 Logo、網站圖示、社群封面
│   ├── brand-city.webp
│   ├── brand-rope.webp
│   ├── brand-symbol.png
│   ├── city-skyline.webp
│   ├── facade-workers.webp
│   ├── favicon.svg
│   ├── glass-building.webp
│   ├── hero-rope.webp
│   ├── inspection-drone.webp
│   ├── og-cover.webp
│   └── safety-equipment.webp
├── robots.txt
├── .nojekyll                            # 靜態網站 / Branch 部署相容
├── .github/
│   └── workflows/
│       └── deploy-pages.yml            # GitHub Actions 自動發布
└── README.md                           # 本檔案
```

## 🚀 第一次上線：推薦 GitHub Actions 自動發布

1. 登入 [github.com](https://github.com) → 右上角 `+` → **New repository**。
2. Repository 名稱可用 `skyworks-website`（只是範例，可改名）。建議選 **Public**（GitHub Free 可使用公開儲存庫發布 Pages）；不要勾選預先新增 README，以免不必要的衝突。
3. **解壓縮本下載 ZIP**；將解壓縮後資料夾裡的所有檔案、資料夾（包括隱藏的 `.github` 和 `.nojekyll`）上傳到 repository 的**根目錄**。**不能只把 ZIP 當作一個壓縮檔上傳**，也不要把所有網站檔案包在額外一層目錄。推薦使用 GitHub Desktop 進行提交與 Push，較不容易漏掉隱藏檔案。
4. 確認 GitHub 首頁檔案清單能直接看到 `index.html`、`assets`、`README.md`，並能找到 `.github/workflows/deploy-pages.yml`。
5. 到 Repository → **Settings → Pages → Build and deployment → Source → GitHub Actions**。
6. 選取 GitHub Actions 即可使用隨附的 `deploy-pages.yml`，**不需要再建立另一套工作流程**。如初次上傳的執行早於 Pages 啟用，可到 **Actions → Publish SKYWORKS website to GitHub Pages → Run workflow** 手動再執行一次。
7. 在 **Actions** 檢視部署結果；看到成功後，網站會顯示在 **Settings → Pages → Visit site**。

### 站址規則

- 一般專案儲存庫 `skyworks-website`：`https://<你的GitHub帳號>.github.io/skyworks-website/`
- 若儲存庫名稱正好為 `<你的GitHub帳號>.github.io`：`https://<你的GitHub帳號>.github.io/`

以上為**網址格式範例**，不是已註冊或部署的真實網址。GitHub Pages 本身支援 HTTPS。

## 💡 不用 GitHub Actions 的簡單替代方案

若只想用 GitHub 最基本的 **Deploy from a branch**：

1. 把本資料夾內容上傳至 `main` 根目錄。
2. 到 **Settings → Pages → Source** 改選 **Deploy from a branch**。
3. 選 `main` 與 `/ (root)` → **Save**。
4. 此模式只需要 `index.html`、`assets/`、`.nojekyll`；隨附的 GitHub Actions workflow 在這種模式不需要使用。若之後會自行維護，建議選一種發布來源即可，避免重複部署。

## 🧩 本次為什麼無須重寫原始碼？

此站原本就是純靜態單頁式網站。圖片使用相對路徑 `assets/...`；不依賴 Node.js、WordPress、PHP、資料庫、外部 API 或伺服器端渲染，因此無論部署在 `帳號.github.io` 根站或 `/repository-name/` 專案站，圖片都能從正確路徑載入。原版 HTML / CSS / JavaScript 及全部圖片檔 **位元組完全保留**。

## ✅ 上傳前可自行檢查

- 雙擊 `index.html`：在電腦端檢查視覺（本地檔案直接開啟）。
- 確認網頁頂端 Logo、首頁圖片、三欄服務圖、品牌圖、手機選單正常。
- 確認 `assets/` 是緊鄰 `index.html`，**不是** `assets/assets/`。
- 若畫面空白／404：確認 `index.html` 位於儲存庫**根目錄**、Pages 已設定，且 Actions 工作流程為綠色成功。
- 若圖片 404：檢查大小寫與 `assets` 資料夾相對路徑；GitHub 網站的檔案名稱會區分英文大小寫。

## ☎️ 原版聯絡資料（上線前請確認）

- 公司：炫采外牆有限公司
- 英文：SKYWORKS ROPE ACCESS
- 電話：0968-710-706
- LINE ID：`tkoejcsw1`
- 地址：台北市內湖區內湖路一段66號3樓

原版未設計後端寄信表單；點擊電話可以撥號，LINE ID 是「複製」功能而非未經確認的官方 LINE 直接加好友連結。原有品牌情境圖片不應誤稱為實際完工案例。

## 🌐 未來使用自有網域（選用）

當您正式取得 `xuancai.tw` 或其他網域後，可到 **Settings → Pages → Custom domain** 設定；同時依 GitHub 文件於 DNS 提供商建立正確紀錄，再啟用 Enforce HTTPS。**不要在未確認網域所有權與 DNS 前加入 CNAME 或虛構正式站址。** 站址確定後可補上 canonical 與絕對網址的 og:image，以利 SEO 與社群分享。

## 🔒 安全、授權與限制

- GitHub Pages 是靜態網站服務，不提供 PHP、Node.js 常駐後端或資料庫；如果日後要加入表單、CRM 或預約系統，應串接第三方後端服務並做好個資告知。
- GitHub Pages 網站通常為公開可讀；不要把密碼、API token、私人客戶資料放進此儲存庫。
- 品牌圖、內容使用由您提供的版本；若涉及第三方攝影素材，正式公開前應確認使用權。
- 本包**未替您建立 GitHub 儲存庫**，也未替您公開上線；完成步驟後才會產生實際網址。

## 官方文件

- [GitHub Pages 設定發布來源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub Actions 自動部署 Pages](https://docs.github.com/en/get-started/start-your-journey/deploying-your-website-automatically)
