# Trading Dashboard

專業交易 Dashboard，支援即時報價、部位管理、選擇權、P&L 追蹤。

## 功能
- **即時報價**：美股 (ADBE, AVGO, CAT, DIS, NVDA, AMD, TSLA) + 台股 (2317, 2454, 2330)
- **自動更新**：每 15 秒透過 Yahoo Finance API 刷新報價
- **部位管理**：多空股票部位，顯示未實現 P&L、今日 P&L、Delta$
- **選擇權**：Call/Put，Long/Short，自動計算 Delta/Gamma/Theta/Vega
- **Book P&L**：整體帳冊損益、市值、淨 Delta
- **停損監控**：10 億美元停損計量器，超過 90% 自動警示

## 資料來源
- Yahoo Finance（via allorigins proxy，免費，無需 API key）
- 報價延遲：美股約 15 分鐘（免費方案），台股同步

## 部署到 Vercel

### 方法一：GitHub + Vercel (推薦)
```bash
git init
git add .
git commit -m "init trading dashboard"
git remote add origin https://github.com/YOUR_USERNAME/trading-dashboard.git
git push -u origin main
```
然後到 [vercel.com](https://vercel.com) → Import Repository → 選你的 repo → Deploy

### 方法二：Vercel CLI
```bash
npm i -g vercel
vercel --prod
```

## 即時報價升級（選用）
如需完全即時報價（無延遲），可申請免費 [Finnhub API key](https://finnhub.io)，
將 `index.html` 中的 `FINNHUB_KEY` 替換為你的 key。

## 本地開發
```bash
# 直接用瀏覽器開啟
open index.html

# 或用 live-server
npx live-server .
```

## 注意事項
- 部位資料儲存於 localStorage（清除瀏覽器快取會消失）
- 停損設定：虧損超過 $1,000,000,000 USD 顯示強制平倉警告
- 台股報價單位：TWD
