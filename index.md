---
layout: default
title: MOTW 技術支援中心
---

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  /* 全域與響應式風格強化 */
  body {
    color: #333;
    background-color: #ffffff;
    line-height: 1.8;
    font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif;
  }

  .site-footer, footer { display: none !important; }
  a { text-decoration: none; transition: 0.3s ease; }

  /* 品牌 Hero 區塊：重點放在推廣 PE 與 專業形象 */
  .hero-section {
    text-align: center;
    padding: 60px 20px;
    background: linear-gradient(135deg, #ffffff 0%, #fdf2f3 100%);
    border-radius: 20px;
    margin-bottom: 40px;
    border: 1px solid #fee2e5;
  }

  .hero-section h1 {
    color: #D21F3C !important;
    font-size: clamp(1.8em, 5vw, 2.8em);
    font-weight: 800;
    margin-bottom: 15px;
    border-bottom: none !important;
  }

  .hero-section p {
    font-size: 1.15em;
    color: #555;
    max-width: 800px;
    margin: 0 auto 35px;
  }

  /* 核心按鈕：首要目標是「應用文獻」 */
  .btn-main {
    display: inline-block;
    padding: 18px 50px;
    font-size: 1.15em;
    font-weight: bold;
    color: #ffffff !important;
    background-color: #D21F3C;
    border-radius: 50px;
    box-shadow: 0 8px 20px rgba(210, 31, 60, 0.3);
  }

  .btn-main:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 25px rgba(210, 31, 60, 0.4);
  }

  /* 應用文獻預覽網格 */
  .article-preview-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 25px;
    margin: 40px 0;
  }

  .article-card {
    background: #fff;
    border: 1px solid #eee;
    padding: 30px;
    border-radius: 12px;
    border-top: 5px solid #D21F3C;
    transition: 0.3s;
  }

  .article-card:hover {
    box-shadow: 0 8px 25px rgba(0,0,0,0.06);
  }

  .article-card span {
    color: #D21F3C;
    font-weight: bold;
    font-size: 0.8em;
    letter-spacing: 1px;
  }

  .info-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin-top: 30px;
  }

  .info-card {
    flex: 1;
    min-width: 250px;
    padding: 25px;
    border: 1px solid #eee;
    border-radius: 12px;
    background: #fff;
  }
</style>

<div class="hero-section">
  <h1>PROFIS Engineering</h1>
  <p>掌握最新錨固設計法規與 PROFIS Engineering 應用指南。我們致力於分享業界實務文獻，協助工程師建立安全且高效的計算模型。</p>
  <a href="/TWsoftware-FAQ/blog.html" class="btn-main">📖 探索應用文獻資訊</a>
</div>

<h2 style="text-align: center; color: #333; margin-top: 60px;">📰 最新應用文獻精選</h2>
<p style="text-align: center; color: #666; margin-bottom: 40px;">獲取業界專家針對最新法規與軟體應用的深度分析</p>

<div class="article-preview-grid">
  <div class="article-card">
    <span>Technical Guide</span>
    <h3 style="margin: 15px 0; border:none !important; color:#333 !important;">軟體操作大師指南</h3>
    <p style="color: #777; font-size: 0.95em;">拆解官方手冊，涵蓋雲端管理、3D 建模與自動化報告生成的核心技巧。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="color: #D21F3C; font-weight: bold;">閱讀文章 →</a>
  </div>
  <div class="article-card">
    <span>Regulation</span>
    <h3 style="margin: 15px 0; border:none !important; color:#333 !important;">全球錨固設計規範對照</h3>
    <p style="color: #777; font-size: 0.95em;">直觀解析台灣土木 401-112 與國際 ACI/EN 規範在抗震要求上的關鍵差異。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="color: #D21F3C; font-weight: bold;">閱讀文章 →</a>
  </div>
  <div class="article-card">
    <span>Resources</span>
    <h3 style="margin: 15px 0; border:none !important; color:#333 !important;">官方技術手冊下載中心</h3>
    <p style="color: #777; font-size: 0.95em;">彙整 Steel-to-Concrete 與各類連接手冊，供工程師隨時查閱下載。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="color: #D21F3C; font-weight: bold;">閱讀文章 →</a>
  </div>
</div>

<div style="background-color: #f9f9f9; padding: 50px 20px; border-radius: 20px; margin: 60px 0;">
  <h2 style="text-align: center; color: #333; margin-bottom: 10px;">🔗 業界專業資源導航</h2>
  <p style="text-align: center; color: #666; margin-bottom: 40px;">獲取最新官方規範文件與 Hilti 權威技術支援</p>
  <div class="info-grid">
    <a href="https://www.hilti.com.tw/engineering/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important;">🔴 Hilti 工程中心</h3>
      <p style="font-size: 0.9em; color:#777;">官方技術論文、認證報告與最新的 BIM/CAD 模型庫。</p>
    </a>
    <a href="https://www.cpami.gov.tw/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important;">🏛️ 內政部國土署</h3>
      <p style="font-size: 0.9em; color:#777;">查詢最新建築物混凝土結構設計規範與營建法律條文。</p>
    </a>
    <a href="https://ask.hilti.com.tw/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important;">💬 Ask Hilti 論壇</h3>
      <p style="font-size: 0.9em; color:#777;">與全球工程師交流，解決最棘手的現場錨固設計難題。</p>
    </a>
  </div>
</div>

<div style="text-align: center; padding: 50px 20px; border: 2px dashed #eee; border-radius: 20px;">
  <h2 style="color: #333; margin-bottom: 15px;">❓ 需要具體的技術支援？</h2>
  <p style="color: #666; margin-bottom: 30px;">針對軟體操作報錯、具體參數設定等問題，我們為您準備了詳細的問答集與諮詢通道。</p>
  <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px;">
    <a href="/TWsoftware-FAQ/faq.html" style="color: #D21F3C; font-weight: bold; font-size: 1.1em; text-decoration: underline;">📚 進入 FAQ 常見問答</a>
    <a href="https://forms.office.com/e/PngwicwAn8" target="_blank" style="color: #666; font-size: 1.1em; text-decoration: underline;">📩 提交私密技術諮詢</a>
  </div>
</div>

<hr style="border-top: 1px solid #eee; margin: 80px 0 20px 0;">
<p align="center" style="color:#808080; font-size:0.85em;">
  © 2026 Hilti Engineering Support Team | 僅供技術交流參考<br>
  本網頁由 <b>MOTW 技術組</b> 維護
</p>
