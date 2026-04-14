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
  a { text-decoration: none; transition: 0.3s; }

  /* Hero 區塊：品牌視覺 */
  .hero-section {
    text-align: center;
    padding: 60px 20px;
    background: linear-gradient(135deg, #ffffff 0%, #fdf2f3 100%);
    border-radius: 20px;
    margin-bottom: 40px;
    border: 1px solid #fee2e5;
  }
  .hero-section h1 { color: #D21F3C !important; font-size: clamp(2em, 5vw, 3em); font-weight: 800; border-bottom: none !important; }

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
  .article-preview-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 25px; margin: 40px 0; }
  .article-card { background: #fff; border: 1px solid #eee; padding: 25px; border-radius: 12px; transition: 0.3s; display: flex; flex-direction: column; }
  .article-card:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(0,0,0,0.08); }
</style>

<div class="hero-section">
  <h1>PROFIS Engineering</h1>
  <p>掌握最新錨固設計文獻，優化工程安全與效率。<br>我們提供專業的應用指南與技術諮詢服務。</p>
  <a href="/TWsoftware-FAQ/blog.html" style="display: inline-block; padding: 15px 40px; background: #D21F3C; color: white; border-radius: 50px; font-weight: bold; box-shadow: 0 4px 15px rgba(210,31,60,0.3);">📖 瀏覽全部應用文獻</a>
</div>

<h2 style="text-align: center; color: #333;">📰 精選應用文獻與技術要點</h2>
<p style="text-align: center; color: #888;">快速抓取業界核心技術資訊</p>

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
    <p style="font-size:0.9em; color:#777; flex-grow:1;">深入探討台灣土木 401-112 與國際規範在地震載重下的計算差異...</p>
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
    <p style="font-size:0.9em; color:#777; flex-grow:1;">完整拆解 PROFIS Engineering 官方手冊，掌握自動化建模與報告生成的技巧。</p>
    <a href="/TWsoftware-FAQ/blog.html" style="font-weight:bold; color:#D21F3C;">閱讀全文 →</a>
  </div>
</div>

<div style="background: #f9f9f9; padding: 40px 20px; border-radius: 15px; margin: 60px 0;">
  <h2 style="text-align: center; color: #333; margin-bottom: 30px;">🔗 業界資源導航</h2>
  <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px;">
    <a href="https://www.cpami.gov.tw/" target="_blank" style="background:#fff; padding:20px; border-radius:10px; border:1px solid #eee; flex:1; min-width:250px;">
      <h4 style="margin:0; color:#D21F3C;">🏛️ 內政部國土署</h4>
      <p style="font-size:0.85em; color:#777; margin:5px 0 0;">最新建築規範與法律條文查詢。</p>
    </a>
    <a href="https://www.hilti.com.tw/engineering/" target="_blank" style="background:#fff; padding:20px; border-radius:10px; border:1px solid #eee; flex:1; min-width:250px;">
      <h4 style="margin:0; color:#D21F3C;">🔴 Hilti 工程中心</h4>
      <p style="font-size:0.85em; color:#777;">技術報告、認證文件與 BIM 模型庫。</p>
    </a>
  </div>
</div>

<div style="text-align: center; padding: 40px 0; border: 2px dashed #eee; border-radius: 15px;">
  <h3 style="color: #333;">❓ 需要解決具體技術問題？</h3>
  <p style="color: #666;">針對軟體報錯或具體參數設定，請查閱我們的問答集。</p>
  <a href="/TWsoftware-FAQ/faq.html" style="color: #D21F3C; font-weight: bold; text-decoration: underline;">進入 FAQ 常見問答集</a>
</div>

<p align="center" style="color:#808080; font-size:0.85em; margin-top:60px;">
  © 2026 Hilti Engineering Support Team | MOTW 技術組維護
</p>
