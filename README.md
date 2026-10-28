# VibeCoding

個人 Web 專案集合 - Personal Web Projects Collection

## 🔗 工具總覽 | Quick Links

| 工具 | 用途 | 使用連結 |
|------|------|----------|
| Brain Training Game | Stroop 腦部反應訓練遊戲 | [開啟](https://tsuifei.github.io/VibeCoding/brain-training/) |
| File Format Conversion Toolbox | 瀏覽器端檔案格式轉換工具箱 | [開啟](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/) |
| └ WAV to MP3 | 音訊轉檔 | [開啟](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/wav-to-mp3/) |
| └ PNG/JPG to WebP | 圖片轉 WebP | [開啟](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/image-to-webp/) |
| └ Image Compressor | 圖片壓縮 | [開啟](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/image-compressor/) |
| Le Cartomètre | 書殼尺寸計算器（裝幀） | [開啟](https://tsuifei.github.io/VibeCoding/le-cartometre/) |
| Essential Oils Order System | 精油訂購系統（Google Apps Script） | 需部署到自己的 GAS，見下方說明 |
| GAS Newsletters | Gmail 電子報整理到 Drive（Google Apps Script） | 需部署到自己的 GAS，見下方說明 |

## 📂 專案列表 | Projects

### 1. Brain Training Game
腦部反應訓練遊戲 - Stroop 測試

**功能特色：**
- 支援 5 種語言（繁中、簡中、英文、日文、法文）
- 12 種容易識別的顏色
- 速度會從 3 秒逐漸加快到 1.5 秒
- 可暫停/繼續

**📁 位置：** `brain-training/`

**🔗 線上體驗：** [https://tsuifei.github.io/VibeCoding/brain-training/](https://tsuifei.github.io/VibeCoding/brain-training/)

---

### 2. File Format Conversion Toolbox
檔案格式轉換工具箱 - 專業線上格式轉換工具集

**功能特色：**
- 純瀏覽器端處理，無需上傳到伺服器
- 100% 隱私安全保護
- 支援多種格式轉換
- 現代化的使用者介面

**已包含工具：**
- **WAV to MP3** - 音訊格式轉換（支援批量轉換、音質設定 128-320 kbps）
- **PNG/JPG to WebP** - 圖片格式轉換（支援批量轉換、自訂輸出寬度 800-1920px、品質調整）
- **Image Compressor** - 圖片壓縮

**即將推出：**
- PDF 文件轉換工具
- 影片格式轉換
- 更多格式轉換工具...

**📁 位置：** `File-Format-Conversion-Toolbox/`

**🔗 線上體驗：** [https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/)

---

### 3. Essential Oils Order System
精油訂購系統 - 使用 Google Apps Script 的專業訂購管理系統

**功能特色：**
- 🔐 Google 帳號登入驗證
- 🌿 多語言精油資訊（繁體中文、拉丁文、法文）
- 📦 多尺寸選擇和即時價格計算
- 🛒 完整的購物車功能
- 📊 自動儲存到 Google Sheets
- 📝 產品列表可從 Google Sheet 讀取
- 📂 自動整理到指定 Drive 資料夾

**技術架構：**
- 前端：HTML5, CSS3, JavaScript
- 後端：Google Apps Script
- 資料庫：Google Sheets
- 部署工具：Clasp (Command Line Apps Script Projects)

**管理設定：**
- 管理帳號：`hello2paris@gmail.com`
- 資料夾：「精油訂購APP」
- 所有訂單自動整理到指定資料夾並共享給管理帳號

**📁 位置：** `essential-oils-order/`

**📚 文件：**
- [README.md](essential-oils-order/README.md) - 專案說明
- [DEPLOYMENT.md](essential-oils-order/DEPLOYMENT.md) - 部署指南
- [ADMIN_ACCOUNT_SETUP.md](essential-oils-order/ADMIN_ACCOUNT_SETUP.md) - 管理帳號設定

**🚀 快速開始：**
```bash
cd essential-oils-order
clasp login
clasp create --title "精油訂購系統" --type webapp
clasp push
clasp deploy
```

---

### 4. Le Cartomètre
書殼尺寸計算器 - 精裝書（reliure cartonnée）書殼紙板裁切尺寸計算

**功能特色：**
- 輸入書本體的高（H）、寬（l）、厚（é），自動算出書背板、封面板、牛皮紙的裁切尺寸
- 紙板、布料厚度有預設值（2 mm／0.5 mm），可自行修改
- 每個結果都能展開「公式」，看帶入實際數字的計算過程
- 依尺寸自動縮放的書殼俯視圖
- 法文／英文／中文切換（預設法文），手機、平板、桌機都能用

**📁 位置：** `le-cartometre/`

**🔗 線上體驗：** [https://tsuifei.github.io/VibeCoding/le-cartometre/](https://tsuifei.github.io/VibeCoding/le-cartometre/)

---

### 5. GAS Newsletters
電子報整理工具 - 自動將 Gmail 電子報整理到 Google Drive

**功能特色：**
- 🔍 自動搜尋指定收件人的電子報
- 📁 按週分類（YYYY-Wxx）
- 📝 郵件轉成 Markdown
- 🔄 支援定時自動執行

**📁 位置：** `gas/gas_newsletters/`

**📚 文件：** [README.md](gas/gas_newsletters/README.md)

---

## 🚀 使用方式 | How to Use

### 本地運行 | Local Development
1. Clone 此專案
   ```bash
   git clone https://github.com/tsuifei/VibeCoding.git
   ```

2. 進入專案目錄
   ```bash
   cd VibeCoding
   ```

3. 開啟任一專案的 `index.html` 即可使用

### 線上體驗 | Online Demo
直接點擊上方各專案的「線上體驗」連結

---

## 📝 授權 | License
MIT License

---

**Created with ❤️ by TsuiFei**
