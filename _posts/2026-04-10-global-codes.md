---
layout: default
title: "全球錨固設計規範對照：台灣、美國與歐洲的抗震差異"
date: 2026-04-17
excerpt: "透過互動式圖表，直觀解析台灣土木401-112、美國 ACI 318 與歐洲 EN 1992-4 在抗震要求與安全係數上的關鍵差異。"
---

<meta charset="UTF-8">

<style>
  body { color: #333; background-color: #ffffff; line-height: 1.8; font-family: "Helvetica Neue", Helvetica, Arial, sans-serif; }
  h1, h2, h3 { color: #D21F3C !important; border-bottom: 2px solid #D21F3C !important; padding-bottom: 10px; margin-top: 40px; }
  .site-footer, footer { display: none !important; }
  .back-btn { display: inline-block; padding: 8px 15px; background: #f0f0f0; color: #333 !important; border-radius: 5px; font-weight: bold; margin-bottom: 20px; font-size: 0.9em; text-decoration: none; }
  
  /* 互動區塊樣式 */
  .interactive-box { background-color: #fafafa; border: 1px solid #ddd; border-radius: 8px; padding: 25px; margin-top: 30px; box-shadow: 0 4px 12px rgba(0,0,0,0.05); }
  .slider-container { margin: 20px 0; text-align: center; }
  input[type=range] { width: 80%; max-width: 400px; accent-color: #D21F3C; }
  .risk-label { font-size: 1.2em; font-weight: bold; color: #D21F3C; margin-top: 10px; }
  
  table { width: 100%; border-collapse: collapse; margin-top: 20px; background: #fff; text-align: center; font-size: 0.95em; }
  th { background-color: #D21F3C; color: white; padding: 12px; border: 1px solid #ddd; }
  td { padding: 12px; border: 1px solid #ddd; }
  
  .chart-container { position: relative; height: 350px; width: 100%; max-width: 500px; margin: 40px auto; }
</style>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<a href="/TWsoftware-FAQ/blog.html" class="back-btn">← 回到技術專欄</a>

# 🌍 全球錨固設計規範對照與抗震解析

台灣於 113 年生效的「建築物混凝土結構設計規範」大量參考了國際標準。為了讓工程師更直觀地理解台灣規範 (TW 401-112)、美國規範 (ACI 318) 與歐洲規範 (EN 1992-4) 的差異，我們準備了下方的互動工具。

---

## 🎛️ 互動工具 1：地震風險對照表
拖曳下方滑桿，觀察在不同地震風險下，三大規範對於「抗震等級」與「強度折減」的要求變化。

<div class="interactive-box">
  <div class="slider-container">
    <label for="riskSlider"><b>模擬案場地震風險等級：</b></label><br>
    <input type="range" id="riskSlider" min="1" max="3" value="1" step="1">
    <div class="risk-label" id="riskText">🟢 低地震風險區 (靜態載重為主)</div>
  </div>

  <table id="specTable">
    <thead>
      <tr>
        <th>比較項目</th>
        <th>🇹🇼 台灣 (土木401-112)</th>
        <th>🇺🇸 美國 (ACI 318-19)</th>
        <th>🇪🇺 歐洲 (EN 1992-4)</th>
      </tr>
    </thead>
    <tbody id="tableBody">
      </tbody>
  </table>
</div>

---

## 📊 互動工具 2：三大規範綜合雷達圖
從「抗震要求嚴格度」、「計算複雜度」與「產品認證門檻」三個維度，解析各規範的特性。台灣規範雖然以 ACI 為藍本，但在實務應用上融合了歐洲 ETA 的認證精神。

<div class="chart-container">
  <canvas id="radarChart"></canvas>
</div>

<script>
  // --- 互動工具 1：滑桿與表格邏輯 ---
  const riskSlider = document.getElementById('riskSlider');
  const riskText = document.getElementById('riskText');
  const tableBody = document.getElementById('tableBody');

  const data = {
    1: {
      text: "🟢 低地震風險區 (非結構物/靜態載重為主)",
      color: "#28a745",
      tw: ["無強制要求", "可不考慮開裂", "一般錨栓即可", "ϕ = 0.75 (一般)"],
      us: ["Category 1", "可不考慮開裂", "一般錨栓", "ϕ = 0.75"],
      eu: ["無要求 (Static)", "可不考慮開裂", "一般錨栓", "γ = 1.5"]
    },
    2: {
      text: "🟡 中地震風險區 (一般附掛物/商辦)",
      color: "#ffc107",
      tw: ["建議 C1 等級", "強制考慮開裂 (0.3mm)", "需有抗震認證", "ϕ = 0.75 (折減一次)"],
      us: ["Category 2", "強制考慮開裂", "AC308 認證", "ϕ = 0.75"],
      eu: ["C1 等級", "強制考慮開裂", "ETA C1 認證", "γ = 1.5 (輕微折減)"]
    },
    3: {
      text: "🔴 高地震風險區 (維生管線/廠房設備)",
      color: "#D21F3C",
      tw: ["強制 C2 等級", "嚴格開裂模擬 (0.5mm)", "極嚴格認證", "ϕ = 0.75 x 0.75 (雙重折減)"],
      us: ["Category 3", "嚴格開裂模擬", "AC308 嚴格測試", "ϕ = 0.75 x 0.75"],
      eu: ["C2 等級", "循環載重開裂", "ETA C2 認證", "γ = 1.5 x 地震折減係數"]
    }
  };

  const rows = ["抗震等級需求", "混凝土開裂設定", "錨栓產品要求", "強度折減係數 (剪力)"];

  function updateTable(val) {
    riskText.innerHTML = data[val].text;
    riskText.style.color = data[val].color;
    
    let html = "";
    for(let i=0; i<rows.length; i++){
      html += `<tr>
        <td style="font-weight:bold; background:#f9f9f9;">${rows[i]}</td>
        <td>${data[val].tw[i]}</td>
        <td>${data[val].us[i]}</td>
        <td>${data[val].eu[i]}</td>
      </tr>`;
    }
    tableBody.innerHTML = html;
  }

  riskSlider.addEventListener('input', function() { updateTable(this.value); });
  updateTable(1); // 初始化

  // --- 互動工具 2：雷達圖邏輯 ---
  const ctx = document.getElementById('radarChart').getContext('2d');
  new Chart(ctx, {
    type: 'radar',
    data: {
      labels: ['抗震要求嚴格度', '計算複雜度', '產品認證門檻'],
      datasets: [
        {
          label: '🇹🇼 TW 401-112',
          data: [90, 75, 85],
          backgroundColor: 'rgba(210, 31, 60, 0.2)',
          borderColor: 'rgba(210, 31, 60, 1)',
          borderWidth: 2
        },
        {
          label: '🇺🇸 ACI 318-19',
          data: [85, 80, 80],
          backgroundColor: 'rgba(54, 162, 235, 0.2)',
          borderColor: 'rgba(54, 162, 235, 1)',
          borderWidth: 2
        },
        {
          label: '🇪🇺 EN 1992-4',
          data: [80, 95, 95],
          backgroundColor: 'rgba(255, 206, 86, 0.2)',
          borderColor: 'rgba(255, 206, 86, 1)',
          borderWidth: 2
        }
      ]
    },
    options: {
      responsive: true,
      scales: {
        r: { min: 40, max: 100, ticks: { display: false } }
      }
    }
  });
</script>
