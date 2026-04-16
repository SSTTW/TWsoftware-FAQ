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
  
  /* 智能選型器樣式 */
  .smart-selector-container {
    background: #fff;
    max-width: 800px;
    margin: 30px auto;
    padding: 25px;
    border-radius: 15px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.08);
    border: 1px solid #eee;
    text-align: left;
  }
  .selector-controls {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 15px;
    margin-bottom: 20px;
  }
  .control-group label { display: block; font-weight: bold; font-size: 0.9em; margin-bottom: 5px; color: #666; }
  .control-group select { 
    width: 100%; 
    padding: 10px; 
    border-radius: 8px; 
    border: 1px solid #ddd; 
    background: #f9f9f9;
    cursor: pointer;
  }

  .result-display {
    display: none;
    padding: 20px;
    background: #fdf2f3;
    border-radius: 10px;
    border-left: 5px solid #D21F3C;
    margin-top: 20px;
    animation: slideDown 0.3s ease-out;
  }
  @keyframes slideDown { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }

  .profis-link-btn {
    display: inline-block;
    background: #D21F3C;
    color: white !important;
    padding: 12px 25px;
    border-radius: 50px;
    font-weight: bold;
    margin-top: 15px;
    box-shadow: 0 4px 12px rgba(210,31,60,0.2);
  }

  /* 響應式圖表與卡片 (保留原本優化好的 CSS) */
  .charts-flex-container { display: flex; flex-wrap: wrap; gap: 20px; margin: 40px 0; width: 100%; box-sizing: border-box; }
  .chart-box { flex: 1; min-width: 320px; background: #fafafa; border: 1px solid #eee; border-radius: 15px; padding: 20px; box-sizing: border-box; }
  @media (max-width: 768px) { .chart-box { min-width: 100%; } }
  
  .risk-label { font-size: 1.1em; font-weight: bold; color: #D21F3C; text-align: center; margin: 10px 0; }
  table { width: 100%; border-collapse: collapse; font-size: 0.85em; margin-top: 10px; background: #fff; }
  th { background-color: #D21F3C; color: white; padding: 8px; border: 1px solid #ddd; }
  td { padding: 8px; border: 1px solid #ddd; text-align: center; }
  .radar-canvas-wrapper { height: 300px; position: relative; width: 100%; }
</style>

<div class="hero-section" markdown="0">
  <h1>PROFIS Engineering</h1>
  <p>掌握最新錨固設計文獻，優化工程安全與效率。</p>
  
  <div class="smart-selector-container">
    <h3 style="margin-top:0; color:#D21F3C;">🎯 錨栓 / 植筋 快速選型工具</h3>
    <div class="selector-controls">
      <div class="control-group">
        <label>地震風險</label>
        <select id="sel-seismic">
          <option value="low">低地震 (Static)</option>
          <option value="high">高地震 (C2 抗震)</option>
        </select>
      </div>
      <div class="control-group">
        <label>混凝土狀態</label>
        <select id="sel-concrete">
          <option value="non-cracked">無開裂 (建議)</option>
          <option value="cracked">已開裂 (極限)</option>
        </select>
      </div>
      <div class="control-group">
        <label>環境條件</label>
        <select id="sel-env">
          <option value="indoor">室內 (乾燥)</option>
          <option value="outdoor">室外 (腐蝕/潮濕)</option>
        </select>
      </div>
      <div class="control-group">
        <label>優先偏好</label>
        <select id="sel-type">
          <option value="mechanical">機械錨栓 (快速)</option>
          <option value="chemical">化學植筋 (高強)</option>
        </select>
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

<h2 style="text-align: center; color: #333; margin-top: 60px;">📊 核心技術數據：三大規範動態對照</h2>
<div class="charts-flex-container" markdown="0">
  <div class="chart-box">
    <h3 style="color:#D21F3C; margin-top:0; text-align:center;">🎛️ 地震風險動態對照</h3>
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
    <h3 style="color:#D21F3C; margin-top:0; text-align:center;">📈 規範特點綜合評估</h3>
    <div class="radar-canvas-wrapper"><canvas id="radarChart"></canvas></div>
  </div>
</div>

<p align="center" style="color:#808080; font-size:0.85em; margin-top:60px;">
  © 2026 Hilti Engineering Support Team | 僅供技術交流參考
</p>

<script>
  //智能選型邏輯
  function runSelection() {
    const seismic = document.getElementById('sel-seismic').value;
    const concrete = document.getElementById('sel-concrete').value;
    const env = document.getElementById('sel-env').value;
    const type = document.getElementById('sel-type').value;
    
    let product = "";
    let note = "";

    if (seismic === "high") {
      if (type === "chemical") {
        product = "HIT-RE 500 V3";
        note = "高地震區首選化學植筋，具備 C2 抗震認證與室外抗腐蝕能力。";
      } else {
        product = "HST4 / HSL4";
        note = "最新一代機械錨栓，針對開裂混凝土設計，抗震效能頂尖。";
      }
    } else {
      if (env === "outdoor") {
        product = "HIT-RE 500 V3 (不鏽鋼款式)";
        note = "室外環境建議使用化學植筋，並搭配 A4 不鏽鋼材質防止鏽蝕。";
      } else if (type === "mechanical") {
        product = "HUS4 / HST4";
        note = "室內乾燥環境建議使用機械錨栓，施工效率最高且安裝即受力。";
      } else {
        product = "HIT-HY 200-R V3";
        note = "室內化學植筋首選，固化速度快，搭配 SafeSet 技術免清孔。";
      }
    }
    
    // 特殊重型應用檢查
    if (concrete === "cracked" && seismic === "high" && type === "mechanical") {
      product = "HDA / HSL4 (重型擴底錨栓)";
      note = "極限地震工況下，建議選用擴底型錨栓以獲得最高安全性。";
    }

    document.getElementById('res-product').innerText = "推薦產品：" + product;
    document.getElementById('res-note').innerText = note;
    document.getElementById('selection-result').style.display = "block";
  }

  // 保留原本的 Chart.js 與 RiskSlider 邏輯...
  const riskSlider = document.getElementById('riskSlider');
  const riskText = document.getElementById('riskText');
  const tableBody = document.getElementById('tableBody');
  const tableData = {
    1: { text: "🟢 低地震風險區 (Static Only)", color: "#28a745", tw: ["無要求", "不開裂", "ϕ=0.75"], us: ["SDC A/B", "不開裂", "ϕ=0.75"], eu: ["Static", "不開裂", "γ=1.5"] },
    2: { text: "🟡 中地震風險區 (商辦)", color: "#ffc107", tw: ["建議 C1", "0.5mm (C1)", "ϕ=0.75"], us: ["SDC C", "強制開裂", "ϕ=0.75"], eu: ["C1 認證", "強制開裂", "γ=1.5"] },
    3: { text: "🔴 高地震風險區 (醫療/維生)", color: "#D21F3C", tw: ["強制 C2", "0.8mm (C2)", "0.56"], us: ["SDC D/E/F", "極嚴格開裂", "0.56"], eu: ["C2 認證", "循環載重", "地震折減"] }
  };
  const rows = ["抗震等級", "開裂設定", "剪力折減"];
  
  function updateTable(val) {
    if(!tableBody) return;
    riskText.innerHTML = tableData[val].text;
    riskText.style.color = tableData[val].color;
    let html = "";
    for(let i=0; i<rows.length; i++){
      html += `<tr><td style="font-weight:bold; background:#f9f9f9;">${rows[i]}</td><td>${tableData[val].tw[i]}</td><td>${tableData[val].us[i]}</td><td>${tableData[val].eu[i]}</td></tr>`;
    }
    tableBody.innerHTML = html;
  }
  
  if(riskSlider) {
    riskSlider.addEventListener('input', function() { updateTable(this.value); });
    updateTable(1);
  }

  const canvasEl = document.getElementById('radarChart');
  if(canvasEl) {
    new Chart(canvasEl, {
      type: 'radar',
      data: {
        labels: ['抗震嚴格度', '計算複雜度', '認證門檻', '更新頻率'],
        datasets: [
          { label: '🇹🇼 TW', data: [90, 75, 85, 70], backgroundColor: 'rgba(210,31,60,0.2)', borderColor: '#D21F3C', borderWidth: 2 },
          { label: '🇺🇸 US', data: [85, 80, 80, 90], backgroundColor: 'rgba(54,162,235,0.2)', borderColor: '#36A2EB', borderWidth: 2 },
          { label: '🇪🇺 EU', data: [80, 95, 95, 85], backgroundColor: 'rgba(255,206,86,0.2)', borderColor: '#FFCE56', borderWidth: 2 }
        ]
      },
      options: { maintainAspectRatio: false, scales: { r: { min: 40, max: 100, ticks: { display: false } } } }
    });
  }
</script>
