---
layout: default
title: MOTW 技術支援中心
---

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  /* 全域風格 */
  body { color: #333; background-color: #ffffff; line-height: 1.8; font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif; }
  .site-footer, footer { display: none !important; }
  a { text-decoration: none; transition: 0.3s ease; }

  /* Hero 區塊 */
  .hero-section {
    text-align: center;
    padding: 60px 20px;
    background: linear-gradient(135deg, #ffffff 0%, #fdf2f3 100%);
    border-radius: 20px;
    margin-bottom: 40px;
    border: 1px solid #fee2e5;
  }
  .hero-section h1 { color: #D21F3C !important; font-size: clamp(1.8em, 5vw, 2.8em); font-weight: 800; border-bottom: none !important; }

  /* 應用文獻網格 */
  .article-preview-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 25px; margin: 40px 0; }
  .article-card { background: #fff; border: 1px solid #eee; padding: 25px; border-radius: 12px; transition: 0.3s; display: flex; flex-direction: column; border-top: 5px solid #D21F3C; }
  .article-card:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(0,0,0,0.08); }

  /* FAQ 互動區塊樣式 */
  .faq-highlight-container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 30px;
    padding: 40px;
    background: #fdf2f3;
    border-radius: 20px;
    margin: 60px 0;
  }
  .faq-image { flex: 1; min-width: 300px; border-radius: 12px; overflow: hidden; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
  .faq-image img { width: 100%; display: block; }
  .faq-text { flex: 1.2; min-width: 300px; }

  /* 資源導航區 */
  .info-grid { display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin-top: 20px; }
  .info-card { flex: 1; min-width: 250px; padding: 25px; border: 1px solid #eee; border-radius: 12px; background: #fff; text-decoration: none; }
</style>

<div class="hero-section">
  <h1>PROFIS Engineering</h1>
  <p>掌握最新錨固設計文獻，優化工程安全與效率。我們提供專業的應用指南與技術諮詢服務。</p>
  <a href="/TWsoftware-FAQ/blog.html" style="display: inline-block; padding: 15px 40px; background: #D21F3C; color: white; border-radius: 50px; font-weight: bold; box-shadow: 0 4px 15px rgba(210,31,60,0.3);">📖 瀏覽全部應用文獻</a>
</div>

<h2 style="text-align: center; color: #333;">📰 精選應用文獻與技術要點</h2>
<div class="article-preview-grid">
  <div class="article-card">
    <h3 style="color:#D21F3C; margin-top:0;">全球錨固設計規範對照</h3>
    <p style="font-size:0.9em; color:#777; flex-grow:1;">解析台灣土木 401-112 與國際規範在地震載重下的計算差異...</p>
    <a href="/TWsoftware-FAQ/blog.html" style="font-weight:bold; color:#D21F3C;">閱讀全文 →</a>
  </div>
  <div class="article-card">
    <h3 style="color:#D21F3C; margin-top:0;">操作大師指南</h3>
    <p style="font-size:0.9em; color:#777; flex-grow:1;">掌握 PROFIS Engineering 自動化建模與報告生成的技巧。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="font-weight:bold; color:#D21F3C;">閱讀全文 →</a>
  </div>
</div>

<div class="faq-highlight-container">
  <div class="faq-image">
    <img src="/TWsoftware-FAQ/images/faq_preview.png" alt="技術支援示意圖">
  </div>
  <div class="faq-text">
    <h2 style="color: #D21F3C; margin-top: 0;">❓ 技術問題快速排除</h2>
    <p style="color: #555; font-size: 1.1em;">
      針對 PROFIS Engineering 軟體操作報錯、參數設定異常或法規解釋疑義，我們彙整了完整的 FAQ 資料庫，協助您即時解決設計障礙。
    </p>
    <a href="/TWsoftware-FAQ/faq.html" style="display: inline-block; margin-top: 15px; padding: 12px 30px; background: #D21F3C; color: white; border-radius: 8px; font-weight: bold;">進入 FAQ 常見問答</a>
    <div style="margin-top: 20px;">
      <a href="https://forms.office.com/e/PngwicwAn8" target="_blank" style="color: #666; font-size: 0.9em; text-decoration: underline;">📩 找不到答案？點此提交私密諮詢</a>
    </div>
  </div>
</div>

<div style="margin-bottom: 60px;">
  <h2 style="text-align: center; color: #333; margin-bottom: 30px;">🔗 業界專業資源導航</h2>
  <div class="info-grid">
    <a href="https://www.nlma.gov.tw/ch" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0;">🏛️ 內政部國土管理署</h3>
      <p style="font-size:0.9em; color:#777;">最新建築物混凝土結構設計規範與營建法律條文。</p>
    </a>
    <a href="https://www.hilti.com.tw/engineering/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0;">🔴 Hilti 工程中心</h3>
      <p style="font-size:0.9em; color:#777;">官方技術報告、認證文件與 BIM/CAD 模型庫。</p>
    </a>
  </div>
</div>

<p align="center" style="color:#808080; font-size:0.85em; margin-top:60px;">
  © 2026 Hilti Engineering Support Team | 僅供技術交流參考
</p>
