# Trading Desk Pro v2

## 🚀 部署到 Vercel（最簡單方式）

### 方法 A：拖曳上傳（最快，不需要 GitHub）
1. 到 [vercel.com/new](https://vercel.com/new)
2. 點「Browse」或直接把 **`public` 資料夾**拖進去
3. Vercel 自動偵測靜態網站 → Deploy
4. 完成！

### 方法 B：GitHub + Vercel
```bash
git init
git add .
git commit -m "trading desk v2"
git remote add origin https://github.com/YOUR/repo.git
git push -u origin main
```
然後 Vercel Import → 選 repo → **Framework: Other** → **Output Directory: public** → Deploy

> ⚠️ 重要：Vercel 設定頁記得把 Output Directory 設為 `public`

## 功能
- 即時報價（Yahoo Finance，20秒自動刷新）
- 行情看板：卡片式，含開盤/最高/最低/成交量/52週區間/市值/Sparkline
- 股票部位：多空管理，未實現P&L、Today P&L、Delta$
- 選擇權：Call/Put × Long/Short，Black-Scholes Greeks
- 風險監控：P&L 柱狀圖、累計曲線、Greeks 彙總、警示系統
- **歷史交易**：成交記錄、勝率、已實現P&L、平均盈虧統計
- 停損計量器（$10億）
