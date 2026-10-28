# 電子報整理工具（GAS Newsletters）

自動把 Gmail 電子報整理到 Google 雲端硬碟的 Google Apps Script（GAS）工具。

## 功能

- 🔍 自動搜尋寄給指定信箱的電子報
- 📁 按週自動分資料夾（格式：YYYY-Wxx）
- 📝 信件轉成 Markdown 格式
- 📅 從 2024 年 12 月開始處理信件
- 🔄 可以設定定時自動執行

## 檔案結構

```
gas_newsletters/
├── .clasp.json           # Clasp 設定檔
├── appsscript.json       # GAS 專案設定
├── README.md             # 說明文件
└── src/
    ├── Code.js           # 主程式
    ├── EmailToMarkdown.js # 信件轉 Markdown 工具
    └── DriveManager.js   # 雲端硬碟資料夾管理工具
```

## 安裝步驟

### 1. 安裝 Clasp

```bash
npm install -g @google/clasp
```

### 2. 登入 Google 帳號

```bash
clasp login
```

### 3. 建立新的 GAS 專案

在 `gas_newsletters` 資料夾裡執行：

```bash
cd gas/gas_newsletters
clasp create --title "Newsletter Organizer" --type standalone
```

這會產生一組 Script ID，並自動更新 `.clasp.json`。

### 4. 推送程式碼

```bash
clasp push
```

### 5. 開啟 Gmail 和 Drive API

在 Google Apps Script 編輯器裡：
1. 點左側「服務」（Services）旁邊的 ➕
2. 加入「Gmail API」
3. 加入「Drive API」

## 使用方式

### 設定（重要！）

**第一步：寫入設定**

為了安全，信箱地址這類敏感資訊存在 Script Properties 裡，不會出現在程式碼中。

1. 打開 Google Apps Script 編輯器：
```bash
clasp open
```

2. **第一次使用前一定要先執行 `setupConfig` 函式**：
   - 在編輯器裡打開 `Code.gs`
   - 找到 `setupConfig` 函式
   - 依需要修改函式裡的信箱地址：
     ```javascript
     scriptProperties.setProperties({
       'EMAIL_RECIPIENT': 'your-email@gmail.com',  // 改成你的信箱
       'DRIVE_FOLDER_NAME': 'newsletters',
       'START_DATE': '2024-12-01'
     });
     ```
   - 在函式下拉選單選 `setupConfig`
   - 按執行按鈕 ▶️
   - 看執行記錄，確認設定已儲存

3. 設定存在 Script Properties 裡，程式碼檔案不含敏感資訊，可以放心分享或推上 Git

### 手動執行

1. 打開 Google Apps Script 編輯器（如果還沒開）：
```bash
clasp open
```

2. 在編輯器裡選 `runOnce` 函式，按執行

3. 第一次執行要授權存取 Gmail 和雲端硬碟

### 設定定時執行（選用）

在編輯器裡執行 `createDailyTrigger()` 函式，會建立一個每天凌晨 2 點執行的觸發條件。

也可以手動設定：
1. 點編輯器左側的「觸發條件」（Triggers）
2. 點「新增觸發條件」
3. 設定：
   - 函式：`processNewsletters`
   - 部署作業：Head
   - 活動來源：時間驅動
   - 時間型觸發條件類型：日計時器
   - 時段：選一個適合的時間

## 輸出結構

程式會在 Google 雲端硬碟建立這樣的結構：

```
newsletters/
├── 2024-W49/
│   ├── 2024-12-01 信件標題1.md
│   └── 2024-12-03 信件標題2.md
├── 2024-W50/
│   ├── 2024-12-08 信件標題3.md
│   └── 2024-12-10 信件標題4.md
└── 2024-W51/
    └── 2024-12-15 信件標題5.md
```

## Markdown 檔案格式

每封信會轉成這樣的 Markdown 檔：

```markdown
# 信件標題

## 信件資訊

- **寄件人**: sender@example.com
- **收件人**: ez2france.com@gmail.com
- **日期**: 2024-12-09 10:30:00

---

## 內容

信件內文……

---

## 附件

- 檔名.pdf (1.2 MB)
```

## 常用指令

```bash
# 把程式碼推送到 GAS
clasp push

# 從 GAS 拉回程式碼
clasp pull

# 打開線上編輯器
clasp open

# 查看執行記錄
clasp logs

# 查看版本
clasp versions

# 部署
clasp deploy
```

## 注意事項

1. **Gmail 配額限制**：Gmail API 有使用配額，信件很多時可能要分批處理
2. **執行時間限制**：GAS 單次最多執行 6 分鐘，信件太多可能要分批處理
3. **檔名長度**：標題太長會被截到 100 個字元
4. **特殊字元**：檔名裡的特殊字元會被換成 `-`

## 疑難排解

### 問題：找不到信件
- 檢查 `CONFIG.EMAIL_RECIPIENT` 有沒有填對
- 檢查 `CONFIG.START_DATE` 的日期範圍
- 在 Gmail 裡手動試一下搜尋條件

### 問題：無法建立檔案
- 檢查 Drive API 有沒有開啟
- 檢查雲端硬碟空間夠不夠
- 檢查檔名有沒有不能用的字元

### 問題：HTML 轉 Markdown 效果不好
- 程式用的是簡單的 HTML 轉換
- 可以考慮改用第三方函式庫提升轉換品質

## 進階用法

### 自訂信件搜尋條件

修改 `searchNewsletterEmails()` 函式裡的搜尋條件：

```javascript
const query = `to:${CONFIG.EMAIL_RECIPIENT} after:${startDateStr} subject:電子報`;
```

### 幫信件加標籤

處理完信件後自動加上標籤：

```javascript
thread.addLabel(GmailApp.getUserLabelByName('已處理'));
```

## 授權

MIT License

## 作者

為了更有效率地管理電子報而做。
