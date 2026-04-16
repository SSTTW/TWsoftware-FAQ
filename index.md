---
layout: default
title: MOTW 技術支援中心
---

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<style>
  /* 基本設定 */
  body { color: #333; background-color: #ffffff; line-height: 1.8; font-family: "Helvetica Neue", Helvetica, Arial, sans-serif; overflow-x: hidden; }
  .site-footer, footer { display: none !important; }
  a { text-decoration: none; transition: 0.3s ease; }

  /* Hero 區塊 */
  .hero-section { text-align: center; padding: 60px 20px; background: linear-gradient(135deg, #ffffff 0%, #fdf2f3 100%); border-radius: 20px; margin-bottom: 40px; border: 1px solid #fee2e5; }
  .hero-section h1 { color: #D21F3C !important; font-size: clamp(1.8em, 5vw, 2.8em); font-weight: 800; border-bottom: none !important; margin-bottom: 15px; }
  
  /* 智能選型器 */
  .smart-selector-container { background: #fff; max-width: 800px; margin: 30px auto; padding: 25px; border-radius: 15px; box-shadow: 0 10px 30px rgba(0,0,0,0.08); border: 1px solid #eee; text-align: left; }
  .selector-controls { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 15px; margin-bottom: 20px; }
  .control-group label { display: block; font-weight: bold; font-size: 0.9em; margin-bottom: 5px; color: #666; }
  .control-group select { width: 100%; padding: 10px; border-radius: 8px; border: 1px solid #ddd; background: #f9f9f9; }
  .result-display { display: none; padding: 20px; background: #fdf2f3; border-radius: 10px; border-left: 5px solid #D21F3C; margin-top: 20px; animation: slideDown 0.3s ease-out; }
  @keyframes slideDown { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }
  .profis-link-btn { display: inline-block; background: #D21F3C; color: white !important; padding: 12px 25px; border-radius: 50px; font-weight: bold; margin-top: 15px; }

  /* 快速選型卡片 (Icon式) */
  .selector-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 15px; margin: 30px 0; }
  .selector-card { background: #fff; border: 2px solid #eee; border-radius: 12px; padding: 20px; text-align: center; transition: 0.3s; }
  .selector-card:hover { border-color: #D21F3C; transform: translateY(-5px); box-shadow: 0 10px 20px rgba(210,31,60,0.1); }

  /* 圖表與數據區塊 */
  .charts-flex-container { display: flex; flex-wrap: wrap; gap: 20px; margin: 40px 0; width: 100%; box-sizing: border-box; }
  .chart-box { flex: 1; min-width: 320px; background: #fafafa; border: 1px solid #eee; border-radius: 15px; padding: 20px; box-sizing: border-box; }
  .risk-label { font-size: 1.1em; font-weight: bold; color: #D21F3C; text-align: center; margin: 10px 0; }
  table { width: 100%; border-collapse: collapse; font-size: 0.85em; margin-top: 10px; background: #fff; }
  th { background-color: #D21F3C; color: white; padding: 8px; border: 1px solid #ddd; }
  td { padding: 8px; border: 1px solid #ddd; text-align: center; }
  .radar-canvas-wrapper { height: 300px; position: relative; width: 100%; }

  /* FAQ 與資源導航 */
  .faq-highlight-container { display: flex; flex-wrap: wrap; align-items: center; gap: 30px; padding: 40px; background: #fdf2f3; border-radius: 20px; margin: 60px 0; }
  .faq-image { flex: 1; min-width: 280px; border-radius: 12px; overflow: hidden; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
  .faq-image img { width: 100%; display: block; }
  .info-grid { display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin-top: 20px; }
  .info-card { flex: 1; min-width: 250px; padding: 25px; border: 1px solid #eee; border-radius: 12px; background: #fff; display: block; box-shadow: 0 2px 8px rgba(0,0,0,0.05); transition: 0.3s; }
  .info-card:hover { border-color: #D21F3C; transform: translateY(-3px); }

  @media (max-width: 768px) { .chart-box { min-width: 100%; } .faq-highlight-container { padding: 25px !important; } }
</style>

<div class="hero-section" markdown="0">
  <h1>PROFIS Engineering</h1>
  <p>掌握最新錨固設計文獻，優化工程安全與效率。</p>
  
  <div class="smart-selector-container">
    <h3 style="margin-top:0; color:#D21F3C;">🎯 錨栓 / 植筋 快速選型工具</h3>
    <div class="selector-controls">
      <div class="control-group">
        <label>地震風險</label>
        <select id="sel-seismic"><option value="low">低地震 (Static)</option><option value="high">高地震 (C2 抗震)</option></select>
      </div>
      <div class="control-group">
        <label>混凝土狀態</label>
        <select id="sel-concrete"><option value="non-cracked">無開裂 (建議)</option><option value="cracked">已開裂 (極限)</option></select>
      </div>
      <div class="control-group">
        <label>環境條件</label>
        <select id="sel-env"><option value="indoor">室內 (乾燥)</option><option value="outdoor">室外 (腐蝕/潮濕)</option></select>
      </div>
      <div class="control-group">
        <label>優先偏好</label>
        <select id="sel-type"><option value="mechanical">機械錨栓 (快速)</option><option value="chemical">化學植筋 (高強)</option></select>
      </div>
    </div>
    <button onclick="runSelection()" style="width:100%; padding:12px; background:#333; color:white; border:none; border-radius:8px; font-weight:bold; cursor:pointer;">🔍 獲取初步推薦結果</button>
    <div id="selection-result" class="result-display">
      <div style="font-weight:bold; font-size:1.1em; color:#D21F3C;" id="res-product">推薦產品：載入中...</div>
      <p id="res-note" style="font-size:0.9em; margin:10px 0; color:#555;"></p>
      <a href="https://profisengineering.hilti.com/" target="_blank" class="profis-link-btn">前往 PROFIS 進行完整力學驗算 ➔</a>
    </div>
  </div>

  <div class="hero-buttons">
    <a href="/TWsoftware-FAQ/faq.html" style="display: inline-block; padding: 12px 30px; background: #ffffff; color: #D21F3C; border: 2px solid #D21F3C; border-radius: 50px; font-weight: bold;">📚 進入 FAQ 知識庫</a>
    <a href="https://forms.office.com/e/PngwicwAn8" target="_blank" style="display: inline-block; padding: 12px 30px; background: #eee; color: #333; border-radius: 50px; font-weight: bold;">💬 私密技術諮詢</a>
  </div>
</div>

<h2 style="text-align: center; color: #333; margin-top: 40px;">📂 快速分類指南</h2>
<div class="selector-grid" markdown="0">
  <a href="/TWsoftware-FAQ/faq.html#混凝土固定" class="selector-card"><span>🏢</span><h4>混凝土固定</h4><p style="font-size:0.8em; color:#888;">RC結構與梁柱連接</p></a>
  <a href="/TWsoftware-FAQ/faq.html#磚牆固定" class="selector-card"><span>🧱</span><h4>磚牆固定</h4><p style="font-size:0.8em; color:#888;">空心磚與輕質隔間</p></a>
  <a href="/TWsoftware-FAQ/faq.html#預埋系統" class="selector-card"><span>📐</span><h4>預埋槽系統</h4><p style="font-size:0.8em; color:#888;">Anchor Channel 預埋</p></a>
  <a href="/TWsoftware-FAQ/faq.html#機械化學比較" class="selector-card"><span>⚡</span><h4>錨栓原理比較</h4><p style="font-size:0.8em; color:#888;">機械 vs 化學選型</p></a>
</div>

<h2 style="text-align: center; color: #333; margin-top: 60px;">📊 核心技術數據：三大規範動態對照</h2>
<div class="charts-flex-container" markdown="0">
  <div class="chart-box">
    <h3 style="color:#D21F3C; margin-top:0; text-align:center;">🎛️ 地震風險對照</h3>
    <div style="text-align:center;">
      <input type="range" id="riskSlider" min="1" max="3" value="1" step="1" style="width:80%; accent-color:#D21F3C;">
      <div class="risk-label" id="riskText">🟢 低地震風險區</div>
    </div>
    <table>
      <thead><tr><th style="width:28%;">項目</th><th>🇹🇼 台灣</th><th>🇺🇸 美國</th><th>🇪🇺 歐洲</th></tr></thead>
      <tbody id="tableBody"></tbody>
    </table>
  </div>
  <div class="chart-box">
    <h3 style="color:#D21F3C; margin-top:0; text-align:center;">📈 規範特點評估</h3>
    <div class="radar-canvas-wrapper"><canvas id="radarChart"></canvas></div>
  </div>
</div>

<div class="faq-highlight-container" markdown="0">
  <div class="faq-image"><img src="/TWsoftware-FAQ/images/faq_preview.png" alt="FAQ Preview"></div>
  <div class="faq-text">
    <h2 style="color:#D21F3C; margin-top:0;">❓ 技術問題快速排除</h2>
    <p style="color:#555;">針對軟體報錯、參數設定異常或法規解釋疑義，我們彙整了完整的 FAQ 資料庫。</p>
    <a href="/TWsoftware-FAQ/faq.html" style="display:inline-block; padding:12px 30px; background:#D21F3C; color:white; border-radius:8px; font-weight:bold;">查看完整 FAQ</a>
  </div>
</div>

<div style="margin-bottom: 60px;" markdown="0">
  <h2 style="text-align:center; color:#333; margin-bottom:30px;">🔗 專業資源導航</h2>
  <div class="info-grid">
    <a href="https://www.nlma.gov.tw/ch" target="_blank" class="info-card"><h3>🏛️ 國土管理署</h3><p style="font-size:0.9em; color:#777;">最新建築規範與法律條文。</p></a>
    <a href="https://www.hilti.com.tw/engineering/" target="_blank" class="info-card"><h3>🔴 Hilti 工程中心</h3><p style="font-size:0.9em; color:#777;">技術報告與 BIM/CAD 模型庫。</p></a>
  </div>
</div>

<p align="center" style="color:#808080; font-size:0.85em;">© 2026 Hilti Engineering Support Team</p>

<script>
  // 選型邏輯
  function runSelection() {
    const seismic = document.getElementById('sel-seismic').value;
    const concrete = document.getElementById('sel-concrete').value;
    const env = document.getElementById('sel-env').value;
    const type = document.getElementById('sel-type').value;
    let product = "", note = "";

    if (seismic === "high") {
      if (type === "chemical") { product = "HIT-RE 500 V3"; note = "高地震區首選化學植筋，具備 C2 抗震認證。"; }
      else { product = "HST4 / HSL4"; note = "最新機械錨栓，針對開裂混凝土與抗震設計。"; }
    } else {
      if (env === "outdoor") { product = "HIT-RE 500 V3 (A4)"; note = "室外環境建議使用化學植筋搭配不鏽鋼。"; }
      else if (type === "mechanical") { product = "HUS4 / HST4"; note = "室內乾燥環境機械錨栓效率最高。"; }
      else { product = "HIT-HY 200-R V3"; note = "室內化學植筋首選，固化速度快。"; }
    }
    document.getElementById('res-product').innerText = "推薦產品：" + product;
    document.getElementById('res-note').innerText = note;
    document.getElementById('selection-result').style.display = "block";
  }

  // 圖表邏輯
  const riskSlider = document.getElementById('riskSlider');
  const tableData = {
    1: { text: "🟢 低地震風險區 (Static)", color: "#28a745", tw: ["無要求", "不開裂", "0.75"], us: ["SDC A/B", "不開裂", "0.75"], eu: ["Static", "不開裂", "1.5"] },
    2: { text: "🟡 中地震風險區 (商辦)", color: "#ffc107", tw: ["建議 C1", "0.5mm", "0.75"], us: ["SDC C", "強制開裂", "0.75"], eu: ["C1 認證", "強制開裂", "1.5"] },
    3: { text: "🔴 高地震風險區 (維生)", color: "#D21F3C", tw: ["強制 C2", "0.8mm", "0.56"], us: ["SDC D/E/F", "極嚴格", "0.56"], eu: ["C2 認證", "循環載重", "地震折減"] }
  };
  function updateTable(val) {
    document.getElementById('riskText').innerText = tableData[val].text;
    document.getElementById('riskText').style.color = tableData[val].color;
    let html = "";
    const rows = ["抗震等級", "開裂設定", "剪力折減"];
    for(let i=0; i<3; i++) {
      html += `<tr><td style="font-weight:bold; background:#f9f9f9;">${rows[i]}</td><td>${tableData[val].tw[i]}</td><td>${tableData[val].us[i]}</td><td>${tableData[val].eu[i]}</td></tr>`;
    }
    document.getElementById('tableBody').innerHTML = html;
  }
  riskSlider.addEventListener('input', e => updateTable(e.target.value));
  updateTable(1);

  new Chart(document.getElementById('radarChart'), {
    type: 'radar',
    data: {
      labels: ['抗震嚴格度', '計算複雜度', '認證門檻', '更新頻率'],
      datasets: [
        { label: '🇹🇼 TW', data: [90, 75, 85, 70], backgroundColor: 'rgba(210,31,60,0.2)', borderColor: '#D21F3C' },
        { label: '🇺🇸 US', data: [85, 80, 80, 90], backgroundColor: 'rgba(54,162,235,0.2)', borderColor: '#36A2EB' },
        { label: '🇪🇺 EU', data: [80, 95, 95, 85], backgroundColor: 'rgba(255,206,86,0.2)', borderColor: '#FFCE56' }
      ]
    },
    options: { maintainAspectRatio: false, scales: { r: { min: 40, max: 100, ticks: { display: false } } } }
  });
</script>
