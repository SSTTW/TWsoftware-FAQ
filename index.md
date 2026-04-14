---
layout: default
title: MOTW 技術支援中心
---

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  /* 全域風格 */
  body {
    color: #333;
    background-color: #ffffff;
    line-height: 1.8;
    font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif;
  }

  /* 隱藏官方頁尾 */
  .site-footer, footer { display: none !important; }
  a { text-decoration: none; }

  /* 首頁專屬 Hero 區塊 (大視覺區) */
  .hero-section {
    text-align: center;
    padding: 8vw 20px; /* 響應式內距 */
    margin-top: 20px;
    background: linear-gradient(to bottom, #ffffff, #fdf2f3); /* 淡淡的粉紅漸層 */
    border-radius: 12px;
    border: 1px solid #fee2e5;
  }

  .hero-section h1 {
    color: #D21F3C !important;
    font-size: clamp(1.8em, 4vw, 2.5em); /* 響應式字體大小 */
    font-weight: 800;
    margin-bottom: 10px;
    border-bottom: none !important;
  }

  .hero-section p {
    font-size: clamp(1em, 2vw, 1.2em);
    color: #666;
    margin-bottom: 40px;
  }

  /* 核心按鈕設計 */
  .btn-primary {
    display: inline-block;
    padding: 16px 36px;
    margin: 10px 5px; /* 增加外距避免手機版按鈕擠在一起 */
    font-size: 1.1em;
    font-weight: bold;
    color: #ffffff !important;
    background-color: #D21F3C;
    border-radius: 8px;
    transition: all 0.3s ease;
    box-shadow: 0 4px 15px rgba(210, 31, 60, 0.3);
  }

  .btn-primary:hover {
    background-color: #A3182E;
    transform: translateY(-3px);
  }

  /* 次要按鈕 (Blog按鈕專用) */
  .btn-secondary {
    background-color: #ffffff;
    color: #D21F3C !important;
    border: 2px solid #D21F3C;
    box-shadow: none;
  }

  .btn-secondary:hover {
    background-color: #fdf2f3;
    box-shadow: 0 4px 15px rgba(210, 31, 60, 0.1);
  }

  /* 規範資訊區塊 */
  .standards-box {
    background-color: #fafafa;
    border-left: 5px solid #D21F3C;
    padding: 20px;
    margin-top: 40px;
    border-radius: 4px;
  }

  /* 次要資訊區塊 (響應式 Grid) */
  .info-grid {
    display: flex;
    flex-wrap: wrap; /* 允許手機版自動換行 */
    justify-content: center;
    gap: 20px;
    margin-top: 40px;
  }

  .info-card {
    flex: 1;
    min-width: 250px; /* 手機版會自動變成單行 */
    padding: 25px;
    border: 1px solid #eee;
    border-radius: 8px;
    text-align: left; /* 改為靠左對齊較好閱讀 */
    background: #fff;
    box-shadow: 0 2px 10px rgba(0,0,0,0.05);
  }

  .info-card h3 {
    color: #D21F3C !important;
    border-bottom: 1px solid #eee !important;
    padding-bottom: 10px !important;
    margin-top: 0 !important;
    font-size: 1.2em;
  }
</style>

<div class="hero-section">
  <h1>MOTW PROFIS Engineering</h1>
  <p>專業錨固設計與技術支援中心</p>

  <div>
    <a href="./faq.html" class="btn-primary">📚 進入技術問答集 (FAQ)</a>
    <a href="./blog.html" class="btn-primary btn-secondary">📰 閱讀技術專欄 (Blog)</a>
  </div>

  <div style="margin-top: 20px;">
    <a href="https://forms.office.com/e/PngwicwAn8" target="_blank">
      <img src="https://img.shields.io/badge/找不到答案？-點我提交私密問題-gray?style=flat-square&logo=googleforms" alt="私密提問表單">
    </a>
  </div>
</div>

<div class="standards-box">
  <h3 style="margin-top: 0; color: #333 !important; border:none !important;">⚖️ 適用法規與設計標準</h3>
  <p style="font-size: 0.95em; color: #555;">本平台之設計邏輯與 PE 軟體計算基準，皆符合以下最新國內外規範要求：</p>
  <ul style="font-size: 0.9em; color: #666; line-height: 1.8;">
    <li><b>🇹🇼 台灣土木 401-112</b>：建築物混凝土結構設計規範 (第十七章 混凝土結構用錨栓)。</li>
    <li><b>🇺🇸 美國 ACI 318-19 / 318-25</b>：包含開裂混凝土要求與地震載重抵抗 (AC308 / ACI 355.2)。</li>
    <li><b>🇪🇺 歐洲 ETAG 001 / EAD</b>：符合 DIBT / CSTB 實驗室測試之 ETA 認證標準。</li>
  </ul>
</div>

<div class="info-grid">
  <div class="info-card">
    <h3>⚙️ 軟體更新與維護</h3>
    <p style="font-size: 0.9em; color:#777;">SaaS 軟體每三到四週進行維修，並隨時因應政府法規調整，即時更新相對應之計算功能條件。</p>
  </div>
  <div class="info-card">
    <h3>🛡️ 專案保密承諾</h3>
    <p style="font-size: 0.9em;
