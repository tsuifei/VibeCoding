# VibeCoding

我的個人網頁小工具合集

## 🔗 工具總覽

| 工具 | 用途 | 使用連結 |
|------|------|----------|
| 腦力反應訓練遊戲（Brain Training Game） | Stroop 測驗小遊戲 | [開啟](https://tsuifei.github.io/VibeCoding/brain-training/) |
| 檔案格式轉換工具箱（File Format Conversion Toolbox） | 在瀏覽器裡轉檔，檔案不用上傳 | [開啟](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/) |
| └ WAV 轉 MP3 | 音訊轉檔 | [開啟](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/wav-to-mp3/) |
| └ PNG／JPG 轉 WebP | 圖片轉 WebP | [開啟](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/image-to-webp/) |
| └ 圖片壓縮 | 縮小圖片檔案大小 | [開啟](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/image-compressor/) |
| Le Cartomètre | 精裝書書殼尺寸計算器 | [開啟](https://tsuifei.github.io/VibeCoding/le-cartometre/) |
| 精油訂購系統（Essential Oils Order System） | Google Apps Script 訂購系統 | 要部署到自己的 Google Apps Script，見下方說明 |
| 電子報整理工具（GAS Newsletters） | 把 Gmail 電子報整理到 Google Drive | 要部署到自己的 Google Apps Script，見下方說明 |

## 📂 工具介紹

### 1. 腦力反應訓練遊戲（Brain Training Game）
用 Stroop 測驗訓練大腦反應速度

**功能：**
- 支援 5 種語言（繁中、簡中、英文、日文、法文）
- 12 種容易辨認的顏色
- 速度從 3 秒逐漸加快到 1.5 秒
- 可以暫停／繼續

**📁 位置：** `brain-training/`

**🔗 線上使用：** [https://tsuifei.github.io/VibeCoding/brain-training/](https://tsuifei.github.io/VibeCoding/brain-training/)

---

### 2. 檔案格式轉換工具箱（File Format Conversion Toolbox）
在瀏覽器裡就能轉檔的工具合集

**功能：**
- 全部在瀏覽器裡處理，檔案不會上傳到伺服器
- 檔案不離開你的電腦，隱私有保障
- 支援多種格式轉換
- 介面簡潔好用

**目前有的工具：**
- **WAV 轉 MP3**：音訊轉檔（可批次轉換，音質 128–320 kbps 可調）
- **PNG／JPG 轉 WebP**：圖片轉檔（可批次轉換，輸出寬度 800–1920px、畫質可調）
- **圖片壓縮**：縮小圖片檔案大小

**之後想加的：**
- PDF 文件轉換
- 影片格式轉換
- 更多格式轉換工具

**📁 位置：** `File-Format-Conversion-Toolbox/`

**🔗 線上使用：** [https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/](https://tsuifei.github.io/VibeCoding/File-Format-Conversion-Toolbox/)

---

### 3. 精油訂購系統（Essential Oils Order System）
用 Google Apps Script 做的精油訂購管理系統

**功能：**
- 🔐 用 Google 帳號登入
- 🌿 精油資訊有繁體中文、拉丁學名、法文三種名稱
- 📦 可選不同容量，價格即時計算
- 🛒 購物車
- 📊 訂單自動存進 Google 試算表
- 📝 商品清單可以從 Google 試算表讀取
- 📂 檔案自動整理到指定的 Google 雲端硬碟資料夾

**使用技術：**
- 前端：HTML5、CSS3、JavaScript
- 後端：Google Apps Script
- 資料庫：Google 試算表
- 部署工具：Clasp（Google Apps Script 的命令列工具）

**管理設定：**
- 管理帳號：`hello2paris@gmail.com`
- 資料夾：「精油訂購APP」
- 所有訂單自動整理到指定資料夾，並共用給管理帳號

**📁 位置：** `essential-oils-order/`

**📚 說明文件：**
- [README.md](essential-oils-order/README.md)：系統說明
- [DEPLOYMENT.md](essential-oils-order/DEPLOYMENT.md)：部署教學
- [ADMIN_ACCOUNT_SETUP.md](essential-oils-order/ADMIN_ACCOUNT_SETUP.md)：管理帳號設定

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
精裝書（reliure cartonnée）書殼尺寸計算器，算出書殼紙板要裁多大

**功能：**
- 輸入書本體的高（H）、寬（l）、厚（é），自動算出書背板、封面板、牛皮紙的裁切尺寸
- 紙板、布料厚度有預設值（2 mm／0.5 mm），可以自己改
- 每個結果都能展開「公式」，看帶入實際數字的計算過程
- 書殼俯視圖會依尺寸自動縮放
- 法文／英文／中文切換（預設法文），手機、平板、電腦都能用

**📁 位置：** `le-cartometre/`

**🔗 線上使用：** [https://tsuifei.github.io/VibeCoding/le-cartometre/](https://tsuifei.github.io/VibeCoding/le-cartometre/)

---

### 5. 電子報整理工具（GAS Newsletters）
自動把 Gmail 收到的電子報整理到 Google 雲端硬碟

**功能：**
- 🔍 自動搜尋寄給指定信箱的電子報
- 📁 按週分資料夾（YYYY-Wxx）
- 📝 信件轉成 Markdown
- 🔄 可以設定每天自動執行

**📁 位置：** `gas/gas_newsletters/`

**📚 說明文件：** [README.md](gas/gas_newsletters/README.md)

---

## 🚀 使用方式

### 在自己電腦上使用
1. 下載這個專案
   ```bash
   git clone https://github.com/tsuifei/VibeCoding.git
   ```

2. 進入專案資料夾
   ```bash
   cd VibeCoding
   ```

3. 打開任一個工具資料夾裡的 `index.html` 就能使用

### 線上使用
直接點上方「工具總覽」表格裡的連結

---

## 📝 授權
MIT License

---

**TsuiFei 用 ❤️ 做的**
