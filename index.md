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
  <a href="/TWsoftware-FAQ/2026/04/15/profis-master-manual.html" style="display: inline-block; padding: 15px 40px; background: #D21F3C; color: white; border-radius: 50px; font-weight: bold; box-shadow: 0 4px 15px rgba(210,31,60,0.3);">📖 立即下載技術手冊</a>
</div>

<div class="standards-box">
  <h3 style="margin-top: 0; color: #333;">⚖️ 適用法規與設計標準</h3>
  <p style="font-size: 0.95em; color: #555;">點擊下方連結下載原廠與官方規範文件：</p>
  <ul style="font-size: 0.9em; color: #666; line-height: 1.8;">
    <li><a href="/TWsoftware-FAQ/土木401%20112.pdf" target="_blank">🇹🇼 台灣土木 401-112 規範</a></li>
    <li><a href="/TWsoftware-FAQ/ACI318%2019.pdf" target="_blank">🇺🇸 美國 ACI 318-19 規範</a></li>
    <li><a href="/TWsoftware-FAQ/ETAG-001-annex-c.pdf" target="_blank">🇪🇺 歐洲 ETAG 001 認證標準</a></li>
  </ul>
</div>

<h2 style="text-align: center; color: #333;">📊 核心技術數據：三大規範動態對照</h2>

<div class="charts-flex-container">
  
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
          <th>🇹🇼 台灣 (401-112)</th>
          <th>🇺🇸 美國 (ACI 318)</th>
          <th>🇪🇺 歐洲 (EN 1992-4)</th>
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

<div class="faq-highlight-container">
  <div class="faq-image">
    <img src="/TWsoftware-FAQ/images/faq_preview.png" alt="技術支援示意圖">
  </div>
  <div class="faq-text">
    <h2 style="color: #D21F3C; margin-top: 0;">❓ 技術問題快速排除</h2>
    <p style="color: #555; font-size: 1.1em;">
      針對 PROFIS Engineering 軟體操作報錯、參數設定異常或法規解釋疑義，我們彙整了完整的 FAQ 資料庫與下載專區。
    </p>
    
    <div style="display: flex; flex-wrap: wrap; align-items: center; gap: 15px; margin-top: 20px;">
      <a href="/TWsoftware-FAQ/2026/04/15/profis-master-manual.html" style="padding: 12px 30px; background: #D21F3C; color: white; border-radius: 8px; font-weight: bold; text-decoration: none;">進入資源中心</a>
      <div style="display: flex; align-items: center; gap: 5px;">
        <span style="font-size: 1.1em; font-weight: 500;">🙋‍♂️ 找不到答案？</span>
        <a href="https://forms.office.com/e/PngwicwAn8" target="_blank" style="text-decoration: none;">
          <img src="https://img.shields.io/badge/點我-問更多問題-red?style=for-the-badge&logo=microsoftforms" alt="問更多問題" style="height: 32px; border-radius: 5px;">
        </a>
      </div>
    </div>
  </div>
</div>

<div style="margin-bottom: 60px;">
  <h2 style="text-align: center; color: #333; margin-bottom: 30px;">🔗 業界專業資源導航</h2>
  <div class="info-grid">
    <a href="https://www.nlma.gov.tw/ch" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0;">🏛️ 內政部國土管理署</h3>
      <p style="font-size:0.9em; color:#777;">最新建築規範與營建法律條文。</p>
    </a>
    <a href="https://www.hilti.com.tw/engineering/" target="_blank" class="info-card">
      <h3 style="color:#D21F3C !important; margin-top:0;">🔴 Hilti 工程中心</h3>
      <p style="font-size:0.9em; color:#777;">官方技術報告與 BIM/CAD 模型庫。</p>
    </a>
  </div>
</div>

<p align="center" style="color:#808080; font-size:0.85em; margin-top:60px;">
  © 2026 Hilti Engineering Support Team | 僅供技術交流參考
</p>

<script>
  // --- 表格邏輯 (依據 HST Seismic PPT 更新技術參數) ---
  const riskSlider = document.getElementById('riskSlider');
  const riskText = document.getElementById('riskText');
  const tableBody = document.getElementById('tableBody');
  const tableData = {
    1: { 
      text: "🟢 低地震風險區 (Static Only)", 
      color: "#28a745", 
      tw: ["無要求", "不考慮開裂", "ϕ = 0.75"], 
      us: ["SDC A/B", "不考慮開裂", "ϕ = 0.75"], 
      eu: ["Static Design", "不考慮開裂", "γ = 1.5"] 
    },
    2: { 
      text: "🟡 中地震風險區 (一般商辦)", 
      color: "#ffc107", 
      tw: ["建議 C1 等級", "0.5 mm (C1認證)", "ϕ = 0.75"], 
      us: ["SDC C", "強制開裂", "ϕ = 0.75"], 
      eu: ["C1 認證產品", "強制開裂", "γ = 1.5"] 
    },
    3: { 
      text: "🔴 高地震風險區 (醫療/維生建物)", 
      color: "#D21F3C", 
      tw: ["強制 C2 等級", "0.8 mm (C2認證)", "0.75 × 0.75"], 
      us: ["SDC D/E/F", "極嚴格開裂", "0.75 × 0.75"], 
      eu: ["C2 認證產品", "循環載重開裂", "γ = 地震折減"] 
    }
  };
  const rows = ["抗震等級需求", "混凝土開裂設定", "強度折減 (剪力)"];
  function updateTable(val) {
    riskText.innerHTML = tableData[val].text;
    riskText.style.color = tableData[val].color;
    let html = "";
    for(let i=0; i<rows.length; i++){
      html += `<tr><td style="font-weight:bold; background:#f9f9f9;">${rows[i]}</td><td>${tableData[val].tw[i]}</td><td>${tableData[val].us[i]}</td><td>${tableData[val].eu[i]}</td></tr>`;
    }
    tableBody.innerHTML = html;
  }
  riskSlider.addEventListener('input', function() { updateTable(this.value); });
  updateTable(1);

  // --- 雷達圖邏輯 ---
  new Chart(document.getElementById('radarChart'), {
    type: 'radar',
    data: {
      labels: ['抗震嚴格度', '計算複雜度', '產品認證門檻', '更新頻率'],
      datasets: [
        { label: '🇹🇼 TW', data: [90, 75, 85, 70], backgroundColor: 'rgba(210,31,60,0.2)', borderColor: '#D21F3C', borderWidth: 2 },
        { label: '🇺🇸 US', data: [85, 80, 80, 90], backgroundColor: 'rgba(54,162,235,0.2)', borderColor: '#36A2EB', borderWidth: 2 },
        { label: '🇪🇺 EU', data: [80, 95, 95, 85], backgroundColor: 'rgba(255,206,86,0.2)', borderColor: '#FFCE56', borderWidth: 2 }
      ]
    },
    options: {
      maintainAspectRatio: false,
      scales: { r: { min: 40, max: 100, ticks: { display: false } } }
    }
  });
</script>
