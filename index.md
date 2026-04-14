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

  /* 品牌 Hero 區塊 */
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

  /* Key Takeaways 小卡風格 */
  .takeaway-box {
    background: #fffafb;
    border-left: 5px solid #D21F3C;
    padding: 15px;
    margin: 15px 0;
    font-size: 0.9em;
    text-align: left;
    border-radius: 0 8px 8px 0;
  }
  .takeaway-box ul { margin: 5px 0 0 18px; padding: 0; color: #666; }

  /* 文章網格 */
  .article-preview-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 25px;
    margin: 40px 0;
  }

  .article-card {
    background: #fff;
    border: 1px solid #eee;
    padding: 25px;
    border-radius: 12px;
    transition: 0.3s;
    display: flex;
    flex-direction: column;
  }

  .article-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(0,0,0,0.08);
  }

  /* 資源導航區 */
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
    text-decoration: none;
  }
</style>

<div class="hero-section">
  <h1>PROFIS Engineering</h1>
  <p>掌握最新錨固設計文獻，優化工程安全與效率。我們提供專業的應用指南與技術諮詢服務。</p>
  <a href="/TWsoftware-FAQ/blog.html" style="display: inline-block; padding: 15px 40px; background: #D21F3C; color: white; border-radius: 50px; font-weight: bold; box-shadow: 0 4px 15px rgba(210,31,60,0.3);">📖 瀏覽全部應用文獻</a>
</div>

<h2 style="text-align: center; color: #333; margin-top: 60px;">📰 精選應用文獻與技術要點</h2>
<p style="text-align: center; color: #888; margin-bottom: 30px;">快速抓取業界核心技術資訊</p>

<div class="article-preview-grid">
  <div class="article-card">
    <h3 style="color:#D21F3C; margin-top:0;">全球錨固設計規範對照</h3>
    <div class="takeaway-box">
      <strong>💡 技術要點：</strong>
      <ul>
        <li>113 年新規範強制檢核開裂混凝土。</li>
        <li>C2 抗震等級產品具備雙重折減機制。</li>
      </ul>
    </div>
    <p style="font-size:0.9em; color:#777; flex-grow:1;">解析台灣土木 401-112 與國際規範在地震載重下的計算差異...</p>
    <a href="/TWsoftware-FAQ/blog.html" style="font-weight:bold; color:#D21F3C;">閱讀全文 →</a>
  </div>

  <div class="article-card">
    <h3 style="color:#D21F3C; margin-top:0;">操作大師指南</h3>
    <div class="takeaway-box">
      <strong>💡 操作要點：</strong>
      <ul>
        <li>善用模板功能可節省 80% 重複設定。</li>
        <li>3D 視圖實時偵測底板與鋼筋衝突。</li>
      </ul>
    </div>
    <p style="font-size:0.9em; color:#777; flex-grow:1;">掌握 PROFIS Engineering 自動化建模與報告生成的技巧。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="font-weight:bold; color:#D21F3C;">閱讀全文 →</a>
  </div>
</div>

<div class="resource-section">
  <h2 style="text-align: center; color: #333; margin-bottom: 10px;">🔗 業界專業資源導航</h2>
  <div class="info-grid">
    <a href="https://www.nlma.gov.tw/ch" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0;">🏛️ 內政部國土管理署</h3>
      <p style="font-size:0.9em; color:#777;">查詢最新建築物混凝土結構設計規範與營建法律條文。</p>
    </a>
    <a href="https://www.hilti.com.tw/engineering/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0;">🔴 Hilti 工程中心</h3>
      <p style="font-size:0.9em; color:#777;">官方技術報告、認證文件與 BIM/CAD 模型庫。</p>
    </a>
    <a href="https://ask.hilti.com.tw/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0;">💬 Ask Hilti 論壇</h3>
      <p style="font-size:0.9em; color:#777;">與全球工程師交流，解決最棘手的現場設計難題。</p>
