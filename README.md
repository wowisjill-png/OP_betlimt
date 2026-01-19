# Bet Limit Configuration (Baccarat)

一個專業的百家樂投注限制管理系統，使用 React 18 + Tailwind CSS 構建，提供完整的 CRUD 功能和智能比例計算。

## 功能特色

### 🎰 百家樂專業投注類型
- 莊家/閒家 (Banker/Player) - 主要投注
- 和局 (Tie) - 平局投注
- 對子 (Pair) - 對子投注
- 獎金 (Bonus) - 獎金投注
- 大小 (Big/Small) - 大小投注  
- 任意對 (Any Pair) - 任意對子
- 完美對 (Perfect Pair) - 完美對子
- 超級六 (Super Six) - 超級六投注
- 幸運六 (Lucky 6) - 幸運六投注
- 莊閒天牌 (B/P Nature) - 莊閒天牌
- 龍寶/虎寶 (Dragon/Tiger Bonus) - 大小龍虎相關投注
- 龍虎 (Dragon Tiger) - 龍虎玩法

### 💰 智能限制管理
- 基於比例的自動限額計算
- 最低/最高投注額配置
- 多幣別支援 (USD, CNY, HKD, JPY, TWD, SGD)
- 最小籌碼限制驗證
- 狀態切換 (Enable/Disable)

### 🔍 高級搜尋功能
- 按網站 (Website) 搜尋
- 按ID精確查找
- 按幣別過濾
- 即時編輯搜尋結果
- 複製配置功能

### 📱 響應式設計
- **桌面版**: 8欄網格佈局，最佳化大螢幕體驗
- **平板版**: 自適應欄位調整
- **手機版**: 垂直堆疊，保持功能完整性
- **彈性容器**: 適應各種螢幕尺寸

### 🚀 React進階功能
- ✅ **自動計算**: 基於比例的限額自動計算
- ✅ **智能驗證**: 最小籌碼/基準限額驗證
- ✅ **動態ID生成**: 5位數ID自動遞增
- ✅ **實時通知**: 成功/錯誤狀態反饋
- ✅ **複製配置**: 一鍵複製現有配置
- ✅ **狀態切換**: Enable/Disable 即時切換
- ✅ **貨幣映射**: 自動載入貨幣對應最小籌碼
- ✅ **表單重置**: 完整的表單狀態管理

## 檔案結構

```
op_BetlimitSetting/
├── index.html          # React單頁應用程式
├── README.md           # 專案說明文件
└── start_server.bat    # 本地伺服器啟動腳本
```

## 技術規格

### 前端技術棧
- **React 18** - 現代化前端框架
- **Tailwind CSS** - 實用程式優先的CSS框架  
- **Lucide Icons** - 現代化圖示庫
- **Babel Standalone** - 瀏覽器內JSX轉譯

### 支援的網站平台
- **Gamelobby** - 遊戲大廳
- **Sportsbook** - 體育投注平台
- **LiveCasino_A** - 真人賭場 A
- **LiveCasino_B** - 真人賭場 B

### 支援的貨幣
- **USD** (美元) - 最小籌碼: $5
- **CNY** (人民幣) - 最小籌碼: ¥20
- **HKD** (港幣) - 最小籌碼: HK$20
- **JPY** (日圓) - 最小籌碼: ¥500  
- **TWD** (台幣) - 最小籌碼: NT$100
- **SGD** (新幣) - 最小籌碼: S$10

### 瀏覽器支援
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## 快速開始

### 1. 開啟專案
```bash
# 方法1: 雙擊 start_server.bat 自動啟動
start_server.bat

# 方法2: 手動啟動Python伺服器
python -m http.server 8000
# 然後前往 http://localhost:8000

# 方法3: 直接開啟HTML檔案 (CDN依賴可能較慢)
# 直接在瀏覽器開啟 index.html
```

### 2. 基本操作

#### 創建新的投注限制
1. 切換到 "Create New Bet Limit" 分頁
2. 選擇網站平台 (必填)
3. 選擇貨幣 (必填，會自動載入最小籌碼)
4. 選填或生成 Bet Limit ID
5. 使用快速計算工具設定基準限額
6. 調整各投注類型的限額
7. 點擊 "Save New Limit"

#### 搜尋和編輯現有限制  
1. 在 "Search & Modify" 分頁設定搜尋條件
2. 選擇網站 (必填) 或輸入ID進行精確搜尋
3. 選擇性過濾貨幣
4. 點擊 "Search" 查看結果
5. 直接在搜尋結果中編輯限額
6. 切換 Enable/Disable 狀態
7. 點擊 "Save Changes" 儲存修改

#### 複製配置
1. 在搜尋結果中找到要複製的配置
2. 點擊 "Copy" 按鈕
3. 系統會自動切換到創建分頁並填入資料
4. 自動生成新的ID
5. 可進一步調整後儲存

## 比例計算系統

### 最小限額比例 (相對於基準100%)
- Banker/Player: 100%
- Tie: 10%
- Pair: 10% 
- Bonus: 10%
- Big/Small: 100%
- Any Pair: 10%
- Perfect Pair: 10%
- Super Six: 10%

### 最大限額比例 (相對於基準100%)
- Banker/Player: 100%
- Tie: 10%
- Pair: 9%
- Bonus: 9% 
- Big/Small: 100%
- Any Pair: 20%
- Perfect Pair: 4%
- Super Six: 8%

## 智能驗證系統

### 自動驗證規則
- **最小籌碼驗證**: 所有最小限額必須 ≥ 該貨幣的最小籌碼
- **基準限額驗證**: 各投注類型的限額必須 ≥ 計算出的基準限額
- **邏輯驗證**: 最大限額必須 ≥ 最小限額
- **必填欄位**: Banker/Player 限額不可為空

### 即時反饋
- **紅色邊框**: 表示輸入值有錯誤
- **錯誤提示**: 具體說明錯誤原因
- **通知訊息**: 操作成功/失敗的即時反饋
- **狀態指示**: Enable/Disable 視覺化顯示

## 部署指南

### GitHub Pages 部署
1. 將專案推送至 GitHub 儲存庫
2. 在設定中啟用 GitHub Pages
3. 選擇主分支作為來源
4. 取得公開網址

### 其他平台
- **Netlify**: 拖曳資料夾直接部署
- **Vercel**: 連接 GitHub 自動部署
- **Firebase Hosting**: 使用 Firebase CLI

## 客製化指南

### 新增網站平台
修改 `WEBSITES` 常數：
```javascript
const WEBSITES = ['Gamelobby', 'Sportsbook', 'LiveCasino_A', 'LiveCasino_B', 'NewSite'];
```

### 新增貨幣支援
修改 `CURRENCIES` 和 `MIN_CHIP_DEFAULTS`：
```javascript
const CURRENCIES = ['USD', 'CNY', 'HKD', 'JPY', 'TWD', 'SGD', 'EUR'];
const MIN_CHIP_DEFAULTS = {
  USD: 5, CNY: 20, HKD: 20, JPY: 500, TWD: 100, SGD: 10, EUR: 5
};
```

### 調整比例計算
修改 `MIN_RATIOS` 和 `MAX_RATIOS`：
```javascript
const MIN_RATIOS = {
  bp: 100, tie: 15, // 調整 Tie 的比例從 10% 到 15%
  // ... 其他設定
};
```

### 自訂樣式
使用 Tailwind CSS 類別進行樣式調整，或添加自訂 CSS。

## 未來規劃

- [ ] **後端API整合**: 連接真實的限額管理後端
- [ ] **資料匯出功能**: JSON/CSV格式匯出
- [ ] **批次操作**: 批次啟用/停用/修改
- [ ] **歷史記錄**: 限額變更歷史追蹤  
- [ ] **權限管理**: 不同角色的操作權限
- [ ] **多語言**: 中文/英文介面切換
- [ ] **深色模式**: 暗色主題支援
- [ ] **資料驗證規則**: 可配置的驗證規則
- [ ] **統計報表**: 限額使用統計和分析

## 授權

MIT License - 可自由使用和修改

## 支援

如有問題或建議，請建立 Issue 或 Pull Request。

---

**開發日期**: 2025年12月16日  
**版本**: 1.0.0  
**作者**: Jill Chang

## 9. 欄位說明

| 欄位名稱         | 說明                                                         | 格式/限制                |
|------------------|--------------------------------------------------------------|--------------------------|
| Bet Limit ID     | 限額設定唯一識別碼，依幣別/網站區間自動產生/手動輸入         | 5位數字，唯一            |
| Game             | 遊戲名稱，批次模式下可同時設定多個遊戲                      | 下拉選單/多選            |
| Website          | 選擇適用的網站                                               | 下拉選單                 |
| Currency         | 幣別，決定 Min Chip 預設值                                   | 下拉選單                 |
| Min Chip         | 幣別對應的最小籌碼，僅顯示不可編輯                           | 數字，依幣別自動帶入      |
| Bet Area Limits  | 各下注區（如 bet, direct, pair...）之 Min/Max 設定           | 數字，依比例自動計算      |
| Min              | 該下注區最小下注額，需大於等於 Min Chip/基礎 Min             | 數字，動態驗證           |
| Max              | 該下注區最大下注額，需大於 Min，且依比例驗證                 | 數字，動態驗證           |
| Status           | 限額狀態（Enable/Disable），預設 Enable                      | 自動設定                 |

- 欄位驗證與互動行為請參考「主要互動行為」與「驗證與錯誤處理邏輯」章節。
- 欄位名稱與 UI 顯示一致，若需擴充請同步調整 GAMES 與 limits 結構。