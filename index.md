---
layout: default
title: MOTW 技術支援中心
---

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

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

  /* --- 互動圖表並列容器 --- */
  .charts-flex-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    margin: 40px 0;
  }
  .chart-box {
    flex: 1;
    min-width: 350px;
    background: #fafafa;
    border: 1px solid #eee;
    border-radius: 15px;
    padding: 20px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.03);
  }
  
  .risk-label { font-size: 1.1em; font-weight: bold; color: #D21F3C; margin: 10px 0; min-height: 1.5em; text-align: center;}
  table { width: 100%; border-collapse: collapse; font-size: 0.85em; background: #fff; }
  th { background-color: #D21F3C; color: white; padding: 8px; border: 1px solid #ddd; }
  td { padding: 8px; border: 1px solid #ddd; text-align: center; }
  .radar-canvas-wrapper { height: 300px; position: relative; }

  /* 適用法規區塊 */
  .standards-box {
    background-color: #fafafa;
    border-left: 5px solid #D21F3C;
    padding: 20px;
    margin: 40px 0;
    border-radius: 8px;
  }
  .standards-box a { color: #D21F3C; text-decoration: underline; font-weight: bold; }

  /* FAQ 互動區塊 */
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

  /* 資源導航 */
  .info-grid { display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin-top: 20px; }
  .info-card { flex: 1; min-width: 250px; padding: 25px; border: 1px solid #eee; border-radius: 12px; background: #fff; text-decoration: none; }
</style>

<div class="hero-section">
  <h1>PROFIS Engineering</h1>
  <p>掌握最新錨固設計文獻，優化工程安全與效率。我們提供專業的應用指南與技術諮詢服務。</p>
  <a href="/TWsoftware-FAQ/blog.
