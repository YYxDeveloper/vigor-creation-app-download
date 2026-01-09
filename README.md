# 躍健健康 App 下載頁面

這是一個靜態網站專案，用於提供躍健健康應用程式的下載連結。使用者可以透過掃描 QR Code 或直接點擊下載按鈕來下載應用程式。

## 功能特色

- 📱 **智能裝置檢測**：自動偵測使用者裝置類型（Android/iOS）
- 🔄 **自動跳轉**：根據裝置類型自動跳轉至對應的應用程式商店
- 🎨 **現代化 UI**：響應式設計，支援各種裝置尺寸
- 📲 **QR Code 生成**：動態生成 QR Code，方便使用者掃描
- 🔗 **備用下載連結**：提供手動下載按鈕，確保所有使用者都能下載

## 檔案結構

```
.
├── index.html          # 主頁面（顯示 QR Code）
├── redirect.html       # 跳轉頁面（裝置檢測與跳轉邏輯）
├── styles.css          # 樣式檔案
└── README.md          # 說明文件
```

## 技術架構

- **HTML5**：語義化標籤，提升 SEO 與可訪問性
- **CSS3**：現代化樣式，包含漸層背景與動畫效果
- **JavaScript**：裝置檢測與自動跳轉邏輯
- **QRCode.js**：透過 CDN 載入的 QR Code 生成庫

## 部署到 GitHub Pages

### 方法一：透過 GitHub 網頁介面

1. 在 GitHub 上建立新的 Repository
2. 將所有檔案上傳到 Repository
3. 進入 Repository 的 **Settings** → **Pages**
4. 在 **Source** 選擇 `main` branch（或您使用的分支）
5. 點擊 **Save**
6. 等待幾分鐘後，您的網站將在 `https://[username].github.io/[repository-name]` 上線

### 方法二：透過 Git 命令列

```bash
# 初始化 Git Repository
git init

# 新增所有檔案
git add .

# 提交變更
git commit -m "feat: 初始專案 - 躍健健康 App 下載頁面"

# 新增遠端 Repository（請替換為您的 Repository URL）
git remote add origin https://github.com/[username]/[repository-name].git

# 推送到 GitHub
git push -u origin main

# 之後在 GitHub 設定 Pages（參考方法一）
```

## 應用程式商店連結

- **Android**: [Google Play Store](https://play.google.com/store/apps/details?id=com.yyxdev.vigor_android&hl=zh_TW&pli=1)
- **iOS**: [App Store](https://apps.apple.com/us/app/%E8%BA%8D%E9%BD%A1%E5%81%A5%E5%BA%B7/id6443744551)

## 裝置檢測邏輯

系統會透過以下方式檢測使用者裝置：

1. **Android 檢測**：
   - 檢查 User-Agent 是否包含 `android`、`Android` 或 `Linux Mobile`

2. **iOS 檢測**：
   - 檢查 User-Agent 是否包含 `iPad`、`iPhone` 或 `iPod`
   - 針對 iOS 13+ 的 iPad，檢查 `navigator.platform === 'MacIntel'` 且 `navigator.maxTouchPoints > 1`

3. **桌面裝置**：
   - 如果無法檢測到行動裝置，會顯示選擇頁面讓使用者手動選擇

## 自訂設定

### 修改應用程式商店連結

編輯 `redirect.html` 檔案中的以下變數：

```javascript
const androidUrl = '您的 Android 連結';
const iosUrl = '您的 iOS 連結';
```

### 修改 QR Code 大小

編輯 `index.html` 檔案中的 QRCode 設定：

```javascript
new QRCode(document.getElementById("qrcode"), {
    width: 300,  // 修改寬度
    height: 300, // 修改高度
    // ...
});
```

### 修改樣式

編輯 `styles.css` 檔案來自訂顏色、字體、間距等樣式。

## 瀏覽器支援

- Chrome (最新版本)
- Firefox (最新版本)
- Safari (最新版本)
- Edge (最新版本)
- 行動瀏覽器（iOS Safari、Chrome Mobile）

## 授權

© 2024 躍健健康. All rights reserved.

## 聯絡資訊

如有任何問題或建議，請聯絡開發團隊。
