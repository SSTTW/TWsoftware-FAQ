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
  .hero-buttons { display: flex; justify-content: center; flex-wrap: wrap; gap: 15px; margin-top: 25px; }

  /* 響應式圖表區塊修正 */
  .charts-flex-container { display: flex; flex-wrap: wrap; gap: 20px; margin: 40px 0; width: 100%; box-sizing: border-box; }
  
  .chart-box { 
    flex: 1; 
    min-width: 320px; 
    background: #fafafa; 
    border: 1px solid #eee; 
    border-radius: 15px; 
    padding: 20px; 
    box-shadow: 0 4px 12px rgba(0,0,0,0.03);
    box-sizing: border-box;
  }

  /* 手機版強制全寬，避免靠右跑版 */
  @media (max-width: 768px) {
    .chart-box { min-width: 100%; }
    .hero-section { padding: 40px 15px; }
    .faq-highlight-container { padding: 25px !important; }
  }
  
  .risk-label { font-size: 1.1em; font-weight: bold; color: #D21F3C; margin: 10px 0; min-height: 1.5em; text-align: center;}
  table { width: 100%; border-collapse: collapse; font-size: 0.85em; background: #fff; margin-top: 10px; }
  th { background-color: #D21F3C; color: white; padding: 8px; border: 1px solid #ddd; }
  td { padding: 8px; border: 1px solid #ddd; text-align: center; }
  .radar-canvas-wrapper { height: 300px; position: relative; width: 100%; }

  /* 互動式快速選型工具 */
  .selector-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 15px; margin: 30px 0; }
  .selector-card { 
    background: #fff; border: 2px solid #eee; border-radius: 12px; padding: 20px; text-align: center;
    transition: 0.3s; cursor: pointer;
  }
  .selector-card:hover, .selector-card.active { border-color: #D21F3C; transform: translateY(-5px); box-shadow: 0 10px 20px rgba(210,31,60,0.1); background: #fdf2f3; }
  .selector-card h4 { margin: 10px 0; color: #333; }
  .selector-card i { font-size: 2em; display: block; margin-bottom: 10px; }

  /* 選型結果動態顯示區塊 */
  .recommendation-box { display: none; background: #fff; border-left: 5px solid #D21F3C; padding: 25px; margin-top: 20px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); animation: fadeIn 0.4s ease; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }
  .profis-btn { display: inline-block; margin-top: 15px; padding: 12px 30px; background: #D21F3C; color: white !important; border-radius: 5px; font-weight: bold; transition: 0.3s; }
  .profis-btn:hover { background: #b01730; transform: scale(1.02); }

  /* 其他現有樣式保持不變 */
  .standards-box { background-color: #fafafa; border-left: 5px solid #D21F3C; padding: 20px; margin: 40px 0; border-radius: 8px; }
  .standards-box a { color: #D21F3C; text-decoration: underline; font-weight: bold; }
  .faq-highlight-container { display: flex; flex-wrap: wrap; align-items: center; gap: 30px; padding: 40px; background: #fdf2f3; border-radius: 20px; margin: 60px 0; }
  .faq-image { flex: 1; min-width: 280px; border-radius: 12px; overflow: hidden; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
  .faq-image img { width: 100%; display: block; }
  .faq-text { flex: 1.2; min-width: 280px; }
  .info-grid { display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin-top: 20px; }
  .info-card { flex: 1; min-width: 250px; padding: 25px; border: 1px solid #eee; border-radius: 12px; background: #fff; display: block; box-shadow: 0 2px 8px rgba(0,0,0,0.05); transition: 0.3s; }
  .info-card:hover { transform: translateY(-3px); box-shadow: 0 8px 20px rgba(210,31,60,0.15); border-color: #D21F3C; }
</style>

<div class="hero-section" markdown="0">
  <h1>PROFIS Engineering</h1>
  <p>掌握最新錨固設計文獻，優化工程安全與效率。我們提供專業的應用指南與技術諮詢服務。</p>
  <div class="hero-buttons">
    <a href="/TWsoftware-FAQ/faq.html" style="display: inline-block; padding: 15px 35px; background: #D21F3C; color: white; border-radius: 50px; font-weight: bold; box-shadow: 0 4px 15px rgba(210,31,60,0.3);">📚 進入 FAQ 知識庫</a>
    <a href="https://forms.office.com/e/PngwicwAn8" target="_blank" style="display: inline-block; padding: 15px 35px; background: #ffffff; color: #D21F3C; border: 2px solid #D21F3C; border-radius: 50px; font-weight: bold; box-shadow: 0 4px 10px rgba(0,0,0,0.05);">💬 私密技術諮詢</a>
  </div>
</div>

<div class="standards-box" markdown="0">
  <h3 style="margin-top: 0; color: #333;">⚖️ 適用法規與設計標準</h3>
  <ul style="font-size: 0.9em; color: #666; line-height: 1.8;">
    <li><a href="/TWsoftware-FAQ/土木401%20112.pdf" target="_blank">🇹🇼 台灣土木 401-112 規範</a></li>
    <li><a href="/TWsoftware-FAQ/ACI318%2019.pdf" target="_blank">🇺🇸 美國 ACI 318-19 規範</a></li>
    <li><a href="/TWsoftware-FAQ/ETAG-001-annex-c.pdf" target="_blank">🇪🇺 歐洲 ETAG 001 認證標準</a></li>
  </ul>
</div>

<h2 style="text-align: center; color: #333; margin-top: 60px;">🎯 快速選型指南：找到正確的設計路徑</h2>
<div class="selector-grid" markdown="0">
  <div class="selector-card" onclick="showRecommendation('concrete', this)">
    <span>🏢</span>
    <h4>混凝土固定</h4>
    <p style="font-size: 0.8em; color: #888;">適用於 RC 結構與梁柱連接</p>
  </div>
  <div class="selector-card" onclick="showRecommendation('masonry', this)">
    <span>🧱</span>
    <h4>磚牆固定</h4>
    <p style="font-size: 0.8em; color: #888;">適用於空心磚與輕質隔間牆</p>
  </div>
  <div class="selector-card" onclick="showRecommendation('channel', this)">
    <span>📐</span>
    <h4>預埋槽系統</h4>
    <p style="font-size: 0.8em; color: #888;">Anchor Channel 預先埋設設計</p>
  </div>
  <div class="selector-card" onclick="showRecommendation('compare', this)">
    <span>⚡</span>
    <h4 style="color: #D21F3C; margin: 10px 0;">機械 / 化學錨栓</h4>
    <p style="font-size: 0.8em; color: #D21F3C;">原理差異、選型與 Nb 值判定</p>
  </div>
</div>

<div id="recommendation-result" class="recommendation-box" markdown="0">
  <h3 id="rec-title" style="color: #D21F3C; margin-top: 0;"></h3>
  <p id="rec-desc" style="color: #555; font-size: 1.05em;"></p>
  <ul id="rec-features" style="color: #555; font-size: 0.95em; line-height: 1.8;"></ul>
  <a href="https://profisengineering.hilti.com/" target="_blank" class="profis-btn">前往 PROFIS Engineering 開始設計 ➔</a>
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
      <thead>
        <tr>
          <th style="width: 28%;">項目</th>
          <th>🇹🇼 台灣</th>
          <th>🇺🇸 美國</th>
          <th>🇪🇺 歐洲</th>
        </tr>
      </thead>
      <tbody id="tableBody"></tbody>
    </table>
  </div>
  <div class="chart-box">
    <h3 style="color:#D21F3C; margin-top:0; text-align:center;">📈 規範特點綜合評估</h3>
    <div class="radar-canvas-wrapper">
      <canvas id="radarChart"></canvas>
    </div>
  </div>
</div>

<div class="faq-highlight-container" markdown="0">
  <div class="faq-image">
    <img src="/TWsoftware-FAQ/images/faq_preview.png" alt="技術支援示意圖">
  </div>
  <div class="faq-text">
    <h2 style="color: #D21F3C; margin-top: 0;">❓ 技術問題快速排除</h2>
    <p style="color: #555;">針對軟體報錯、參數設定異常或法規解釋疑義，我們彙整了完整的 FAQ 資料庫。</p>
    <div style="display: flex; flex-wrap: wrap; gap: 15px; margin-top: 20px;">
      <a href="/TWsoftware-FAQ/faq.html" style="padding: 12px 30px; background: #D21F3C; color: white; border-radius: 8px; font-weight: bold;">查看完整 FAQ</a>
    </div>
  </div>
</div>

<div style="margin-bottom: 60px;" markdown="0">
  <h2 style="text-align: center; color: #333; margin-bottom: 30px;">🔗 業界專業資源導航</h2>
  <div class="info-grid">
    <a href="https://www.nlma.gov.tw/ch" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0; border:none !important;">🏛️ 國土管理署</h3>
      <p style="font-size:0.9em; color:#777; margin:0;">最新建築規範與營建法律條文。</p>
    </a>
    <a href="https://www.hilti.com.tw/engineering/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0; border:none !important;">🔴 Hilti 工程中心</h3>
      <p style="font-size:0.9em; color:#777; margin:0;">官方技術報告與 BIM/CAD 模型庫。</p>
    </a>
  </div>
</div>

<p align="center" style="color:#808080; font-size:0.85em; margin-top:60px;">
  © 2026 Hilti Engineering Support Team | 僅供技術交流參考
</p>

<script>
  // ================= 互動選型工具邏輯 =================
  const recData = {
    'concrete': {
      title: '推薦方案：HST3-R 機械錨栓 / HIT-RE 500 V3 化學植筋',
      desc: '符合台灣 401-112 新規範要求，適用於開裂混凝土與抗震設計。',
      features: ['✅ 具備 C1 / C2 抗震認證，安全有保障', '✅ 支援極小邊距與間距設計', '✅ 可承受動態與地震循環載重']
    },
    'masonry': {
      title: '推薦方案：HIT-HY 270 輕質磚牆專用植筋劑',
      desc: '針對多孔隙與中空基材設計，確保錨固力不流失。',
      features: ['✅ 搭配專用網套管使用，完美適用於空心磚', '✅ 不會對基材產生膨脹應力，避免牆面破裂', '✅ 適用於老舊建築翻修與外牆拉皮工程']
    },
    'channel': {
      title: '推薦方案：HAC-V 預埋槽系統 (Anchor Channel)',
      desc: '免鑽孔的先進錨固技術，提升現場施工效率與精準度。',
      features: ['✅ 適用於玻璃帷幕、電梯導軌安裝', '✅ 支援 3D 全方位受力調整，容錯率高', '✅ 大幅降低現場粉塵與噪音污染']
    },
    'compare': {
      title: '設計指南：機械錨栓 vs 化學錨栓 (Nb 值判定)',
      desc: '根據基材破壞模式 (Nb值) 與現場施工條件進行最佳化選擇。',
      features: ['⚙️ <b>機械錨栓：</b> 施工快速，立即受力，但對邊距與間距要求較嚴格。', '🧪 <b>化學錨栓：</b> 無膨脹應力，適合小邊距，但需注意固化時間與清孔品質。', '💡 建議使用 PROFIS 軟體直接模擬兩種方案在極限狀態下的受力表現。']
    }
  };

  function showRecommendation(type, element) {
    // 移除所有卡片的 active 狀態
    const cards = document.querySelectorAll('.selector-card');
    cards.forEach(card => card.classList.remove('active'));
    // 加上當前卡片的 active 狀態
    element.classList.add('active');

    // 填入對應資料
    document.getElementById('rec-title').innerHTML = recData[type].title;
    document.getElementById('rec-desc').innerHTML = recData[type].desc;
    
    const ul = document.getElementById('rec-features');
    ul.innerHTML = '';
    recData[type].features.forEach(feat => {
      const li = document.createElement('li');
      li.innerHTML = feat;
      li.style.marginBottom = '8px';
      ul.appendChild(li);
    });

    // 顯示結果區塊
    document.getElementById('recommendation-result').style.display = 'block';
  }

  // ================= 表格與雷達圖邏輯 =================
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
