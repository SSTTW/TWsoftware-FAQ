---
layout: default
title: MOTW 技術支援中心
---

<meta charset="UTF-8">
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
    padding: 8vw 20px;
    margin-top: 20px;
    background: linear-gradient(to bottom, #ffffff, #fdf2f3);
    border-radius: 12px;
    border: 1px solid #fee2e5;
  }

  .hero-section h1 {
    color: #D21F3C !important;
    font-size: clamp(1.8em, 4vw, 2.5em);
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
    margin: 10px 5px;
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
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin-top: 40px;
  }

  .info-card {
    flex: 1;
    min-width: 250px;
    padding: 25px;
    border: 1px solid #eee;
    border-radius: 8px;
    text-align: left;
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
  <p style="font-size: 0.95em; color: #555;">本平台之設計邏輯與 PE 軟體計算基準，皆符合以下最新國內外規範要求（點擊可檢視原廠規範文件）：</p>
  <ul style="font-size: 0.9em; color: #666; line-height: 1.8;">
    <li><a href="./土木401%20112.pdf" target="_blank" style="color: #D21F3C; text-decoration: underline;"><b>🇹🇼 台灣土木 401-112</b></a>：建築物混凝土結構設計規範 (第十七章 混凝土結構用錨栓)。</li>
    <li><a href="./ACI318%2019.pdf" target="_blank" style="color: #D21F3C; text-decoration: underline;"><b>🇺🇸 美國 ACI 318-19 / 318-25</b></a>：包含開裂混凝土要求與地震載重抵抗 (AC308 / ACI 355.2)。</li>
    <li><a href="./ETAG-001-annex-c.pdf" target="_blank" style="color: #D21F3C; text-decoration: underline;"><b>🇪🇺 歐洲 ETAG 001 / EAD</b></a>：符合 DIBT / CSTB 實驗室測試之 ETA 認證標準。</li>
  </ul>
</div>

<div class="info-grid">
  <div class="info-card">
    <h3>⚙️ 軟體更新與維護</h3>
    <p style="font-size: 0.9em; color:#777;">SaaS 軟體每三到四週進行維修，並隨時因應政府法規調整，即時更新相對應之計算功能條件。</p>
  </div>
  <div class="info-card">
    <h3>🛡️ 專案保密承諾</h3>
    <p style="font-size: 0.9em; color:#777;">所有透過表單提交之諮詢（含 DWG、參數、截圖）皆採私密處理，僅限內部工程團隊檢閱。</p>
  </div>
</div>

<h2 style="text-align: center; color: #D21F3C; margin-top: 60px;">🔗 外部專業資源</h2>
<p style="text-align: center; color: #666;">獲取最新官方規範文件與技術支援</p>

<div class="info-grid">
  <a href="https://www.cpami.gov.tw/" target="_blank" class="info-card" style="display: block; text-decoration: none;">
    <h3>🏛️ 內政部國土管理署</h3>
    <p style="font-size: 0.9em; color:#777;">查詢最新建築物混凝土結構設計規範與法律條文。</p>
  </a>

  <a href="https://www.hilti.com.tw/engineering/" target="_blank" class="info-card" style="display: block; text-decoration: none;">
    <h3>🔴 Hilti 工程資訊中心</h3>
    <p style="font-size: 0.9em; color:#777;">喜立德官方技術論文、認證報告與 BIM/CAD 庫。</p>
  </a>

  <a href="https://ask.hilti.com.tw/" target="_blank" class="info-card" style="display: block; text-decoration: none;">
    <h3>💬 Ask Hilti 論壇</h3>
    <p style="font-size: 0.9em; color:#777;">全球工程師的技術社群，解決各種特殊的錨固難題。</p>
  </a>
</div>

<hr style="border-top: 1px solid #eee; margin: 60px 0 20px 0;">
<p align="center" style="color:#808080; font-size:0.85em;">
  © 2026 Hilti Engineering Support Team | 僅供技術交流參考<br>
  本網頁由 <b>MOTW 技術組</b> 維護
</p>
