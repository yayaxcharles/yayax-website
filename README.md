# Charles Y. C. Yeh 葉彥呈 — 個人網站（GitHub Pages 版）

高質感 3D 動態風格個人學術網站。單檔 HTML/CSS/JS 架構、無建置流程、無追蹤器，repo 總大小約 290 KB（3D 引擎 Three.js 由 CDN 載入，不佔 repo 空間）。

## 內容物

```
yayax-website-v2/
├── index.html          # 網站本體（含所有樣式與程式）
├── assets/
│   ├── portrait.jpg    # 大頭照（已壓縮 104KB）
│   └── math-island.webp# 數學島截圖（已壓縮 68KB）
├── .nojekyll           # 告訴 GitHub 不要用 Jekyll 處理
└── README.md           # 本說明
```

## 功能

- **3D 動態視覺**：Three.js 打造的 3D 神經星雲（數百顆發光粒子＋星座連線，隨滑鼠視差旋轉）；若無網路或 WebGL 被擋，自動退回純 CSS 極光背景，頁面照常運作
- **高質感介面**：玻璃擬態（glassmorphism）卡片、極光漸層背景、噪點質感、卡片 3D 傾斜特效、發光按鈕、漸層文字、捲動進度條
- **深／淺色模式**：導覽列一鍵切換（記住選擇），3D 星雲配色同步調整
- **活的專案展示**：AI 聊書卡片是循環播放的真實對話演示（含行為／情意／認知訊號亮燈）；LLM 知識追蹤卡片是即時模擬動畫（答題序列逐題亮起、精熟度曲線即時延伸）；專案卡 hover 有旋轉漸層光邊＋滑鼠聚光燈
- 中／英雙語切換（自動偵測瀏覽器語言，記住選擇）
- 著作清單：三分類頁籤＋即時搜尋（標題／作者／年份）
- 「AI 導覽助理」：純前端內建知識庫，**不需任何後端或 API key**，離線可用
- RWD 響應式、`prefers-reduced-motion` 無障礙支援、SEO / Open Graph / JSON-LD
- 三層防禦：功能彼此隔離、內容顯示不依賴 JS、1.5 秒 failsafe——任何腳本失敗都不會讓頁面開天窗

## 部署到 GitHub Pages（三步驟）

1. 在 GitHub 建新 repo：
   - 想當個人首頁 → repo 名稱取 `你的帳號.github.io`（網址就是 `https://你的帳號.github.io/`）
   - 一般 repo（例如 `homepage`）→ 網址會是 `https://你的帳號.github.io/homepage/`
2. 把本資料夾**內容物**（不是外層資料夾）全部上傳到 repo 根目錄：
   ```bash
   cd yayax-website-v2
   git init && git add . && git commit -m "personal website"
   git branch -M main
   git remote add origin https://github.com/你的帳號/你的repo.git
   git push -u origin main
   ```
   （不想用指令的話，GitHub 網頁上「Add file → Upload files」拖進去也可以）
3. Repo → Settings → Pages → Source 選 `Deploy from a branch`、Branch 選 `main` / `(root)` → Save。約 1–2 分鐘後網站上線。

## 部署後建議修改

- `index.html` 內 `<meta property="og:image">` 目前是相對路徑，上線後可改成完整網址
  （例如 `https://你的帳號.github.io/assets/portrait.jpg`），社群分享預覽圖才會正確顯示。

## 更新內容

- **著作**：改 `index.html` 內 `<script id="pub-data">` 的 JSON（journal / conf1 / conf2 三組）
- **英文翻譯**：改 `<script id="i18n-en">` 的 JSON
- **中文內容**：直接改 HTML 內文（中文是預設語言）
- **問答小助理知識庫**：改主程式內的 `KB` 陣列

## 注意

⚠️ 只上傳這個資料夾。舊版 `yayax website/` 資料夾內的 `uploads/` 含薪資表、保險、計畫申請書等私人文件，**切勿**整包推上 GitHub。
