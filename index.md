---
layout: default
title: MOTW 技術支援中心
---

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  /* 全域風格強化 */
  body {
    color: #333;
    background-color: #ffffff;
    line-height: 1.8;
    font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif;
  }

  .site-footer, footer { display: none !important; }
  a { text-decoration: none; transition: 0.3s; }

  /* 調整後的 Hero 區塊：強調 PE 軟體與文獻 */
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
    font-size: clamp(2em, 5vw, 3em);
    font-weight: 800;
    margin-bottom: 15px;
    border-bottom: none !important;
  }

  .hero-section p {
    font-size: 1.2em;
    color: #555;
    max-width: 700px;
    margin: 0 auto 35px;
  }

  /* 核心按鈕：引導至應用文獻 */
  .btn-main {
    display: inline-block;
    padding: 18px 45px;
    font-size: 1.1em;
    font-weight: bold;
    color: #ffffff !important;
    background-color: #D21F3C;
    border-radius: 50px;
    box-shadow: 0 10px 20px rgba(210, 31, 60, 0.2);
  }

  .btn-main:hover {
    transform: translateY(-3px);
    box-shadow: 0 15px 25px rgba(210, 31, 60, 0.3);
  }

  /* 應用文獻預覽區塊 */
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
    border-top: 6px solid #D21F3C;
    transition: 0.3s;
  }

  .article-card:hover {
    box-shadow: 0 8px 25px rgba(0,0,0,0.08);
  }

  .article-card span {
    color: #D21F3C;
    font-weight: bold;
    font-size: 0.85em;
    text-transform: uppercase;
  }

  /* 外部資源區 */
  .resource-section {
    background-color: #f9f9f9;
    padding: 50px 20px;
    border-radius: 20px;
    margin: 60px 0;
  }

  .info-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
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
  <p>探索先進錨固設計文獻，優化工程安全與效率。我們提供專業的應用指南與技術諮詢服務。</p>
  <a href="/TWsoftware-FAQ/blog.html" class="btn-main">📖 進入應用文獻資訊</a>
  <div style="margin-top: 25px;">
    <a href="https://forms.office.com/e/PngwicwAn8" target="_blank" style="font-size: 0.9em; color: #666;">
      📩 找不到解答？提交私密技術諮詢
    </a>
  </div>
</div>

<h2 style="text-align: center; color: #333; margin-top: 60px;">📰 最新應用文獻精選</h2>
<p style="text-align: center; color: #666; margin-bottom: 30px;">掌握業界趨勢與 PROFIS Engineering 核心技術</p>

<div class="article-preview-grid">
  <div class="article-card">
    <span>Technical Guide</span>
    <h3 style="margin: 15px 0;">軟體操作大師指南</h3>
    <p style="color: #777; font-size: 0.95em;">拆解 PROFIS Engineering 官方手冊，涵蓋雲端管理與 3D 建模的核心技巧。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="color: #D21F3C; font-weight: bold;">閱讀文章 →</a>
  </div>
  <div class="article-card">
    <span>Regulation</span>
    <h3 style="margin: 15px 0;">全球錨固設計規範對照</h3>
    <p style="color: #777; font-size: 0.95em;">深入探討台灣土木 401-112 與國際 ACI/EN 規範在抗震設計上的差異。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="color: #D21F3C; font-weight: bold;">閱讀文章 →</a>
  </div>
  <div class="article-card">
    <span>Resource</span>
    <h3 style="margin: 15px 0;">官方技術手冊下載專區</h3>
    <p style="color: #777; font-size: 0.95em;">彙整 Steel-to-Concrete 與各類連接手冊，供工程師隨時查閱。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="color: #D21F3C; font-weight: bold;">閱讀文章 →</a>
  </div>
</div>

<div class="resource-section">
  <h2 style="text-align: center; color: #333; margin-bottom: 10px;">🔗 業界資源導航</h2>
  <p style="text-align: center; color: #666; margin-bottom: 40px;">連結官方與政府權威機構，獲取一手資訊</p>
  <div class="info-grid">
    <a href="https://www.hilti.com.tw/engineering/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C;">🔴 Hilti 工程資訊中心</h3>
      <p style="font-size: 0.9em; color:#777;">官方技術論文、認證報告與 BIM/CAD 庫。</p>
    </a>
    <a href="https://www.cpami.gov.tw/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C;">🏛️ 內政部國土管理署</h3>
      <p style="font-size: 0.9em; color:#777;">查詢最新建築物混凝土結構設計規範與法律條文。</p>
    </a>
    <a href="https://ask.hilti.com.tw/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C;">💬 Ask Hilti 論壇</h3>
      <p style="font-size: 0.9em; color:#777;">解決各種特殊的錨固難題，與全球技師交流。</p>
    </a>
  </div>
</div>

<div style="text-align: center; padding: 40px 20px; border: 1px dashed #ccc; border-radius: 15px;">
  <h2 style="color: #333; margin-bottom: 10px;">❓ 需要快速解決技術問題？</h2>
  <p style="color: #666; margin-bottom: 25px;">針對軟體報錯、參數設定等具體問題，請查閱我們的問答集。</p>
  <a href="/TWsoftware-FAQ/faq.html" style="color: #D21F3C; font-weight: bold; font-size: 1.1em; text-decoration: underline;">進入 FAQ 常見問答集</a>
</div>

<hr style="border-top: 1px solid #eee; margin: 80px 0 20px 0;">
<p align="center" style="color:#808080; font-size:0.85em;">
  © 2026 Hilti Engineering Support Team | 僅供技術交流參考<br>
  本網頁由 <b>MOTW 技術組</b> 維護
</p>
