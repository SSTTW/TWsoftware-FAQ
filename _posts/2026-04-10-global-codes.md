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
  .interactive-box { background-color: #fafafa; border: 1px solid #ddd; border-radius: 12px; padding: 25px; margin-top: 30px; box-shadow: 0 4px 12px rgba(0,0,0,0.05); }
  .slider-container { margin: 20px 0; text-align: center; }
  input[type=range] { width: 80%; max-width: 400px; accent-color: #D21F3C; }
  .risk-label { font-size: 1.2em; font-weight: bold; color: #D21F3C; margin-top: 10px; min-height: 1.5em; }
  
  table { width: 100%; border-collapse: collapse; margin-top: 20px; background: #fff; text-align: center; font-size: 0.95em; border-radius: 8px; overflow: hidden; }
  th { background-color: #D21F3C; color: white; padding: 12px; border: 1px solid #ddd; }
  td { padding: 12px; border: 1px solid #ddd; }
  
  .chart-container { position: relative; height: 350px; width: 100%; max-width: 600px; margin: 40px auto; background: #fff; padding: 20px; border-radius: 15px; border: 1px solid #eee; }
</style>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<a href="/TWsoftware-FAQ/blog.html" class="back-btn">← 回到技術專欄</a>

# 🌍 全球錨固設計規範對照與抗震解析

台灣於 113 年生效的「建築物混凝土結構設計規範」大量參考了國際標準。為了讓工程師更直觀地理解台灣規範 (TW 401-112)、美國規範 (ACI 318) 與歐洲規範 (EN 1992-4) 的差異，我們準備了下方的互動工具。

---

## 🎛️ 互動工具 1：地震風險動態對照表
工程師可根據案場需求，拖曳下方滑桿切換**地震風險等級**。表格將即時更新三大規範對於產品、設計開裂與強度折減的具體要求。

<div class="interactive-box">
  <div class="slider-container">
    <label for="riskSlider"><b>模擬案場地震風險等級：</b></label><br>
    <input type="range" id="riskSlider" min="1" max="3" value="1" step="1">
    <div class="risk-label" id="riskText">🟢 低地震風險區 (靜態載重為主)</div>
  </div>

  <table id="specTable">
    <thead>
      <tr>
        <th style="width: 25%;">比較項目</th>
        <th>🇹🇼 台灣 (401-112)</th>
        <th>🇺🇸 美國 (ACI 318)</th>
        <th>🇪🇺 歐洲 (EN 1992-4)</th>
      </tr>
    </thead>
    <tbody id="tableBody">
      </tbody>
  </table>
</div>

---

## 📊 互動工具 2：三大規範特點雷達圖
下圖展示了各規範在**嚴謹度**與**認證門檻**上的分佈。台灣規範雖然師承美國 ACI，但在產品測試要求上，與歐洲 ETA 的認證精神高度契合。滑鼠移至圖點上可查看詳細分值。

<div class="chart-container">
  <canvas id="radarChart"></canvas>
</div>

<script>
  // --- 互動工具 1：滑桿邏輯 ---
  const riskSlider = document.getElementById('riskSlider');
  const riskText = document.getElementById('riskText');
  const tableBody = document.getElementById('tableBody');

  const data = {
    1: {
      text: "🟢 低地震風險區 (非結構物/靜態載重為主)",
      color: "#28a745",
      tw: ["無強制要求", "可不考慮開裂", "一般錨栓即可", "ϕ = 0.75"],
      us: ["SDC A/B", "不考慮開裂", "一般認證", "ϕ = 0.75"],
      eu: ["Static Only", "不考慮開裂", "一般 ETA", "γ = 1.5"]
    },
    2: {
      text: "🟡 中地震風險區 (一般商辦設備)",
      color: "#ffc107",
      tw: ["建議 C1 等級", "考慮開裂 (0.3mm)", "具抗震認證", "ϕ = 0.75 (折減)"],
      us: ["SDC C", "強制開裂", "AC308 認證", "ϕ = 0.75"],
      eu: ["C1 等級", "強制開裂", "ETA C1", "γ = 1.5"]
    },
    3: {
      text: "🔴 高地震風險區 (維生管線/半導體廠)",
      color: "#D21F3C",
      tw: ["強制 C2 等級", "嚴格開裂 (0.5mm)", "極嚴格認證", "ϕ = 0.75 × 0.75"],
      us: ["SDC D/E/F", "極嚴格開裂", "AC308 測試", "ϕ = 0.75 × 0.75"],
      eu: ["C2 等級", "循環載重開裂", "ETA C2", "γ = 1.5 × 折減"]
    }
  };

  const rows = ["抗震等級需求", "混凝土開裂設定", "錨栓產品要求", "強度折減 (剪力)"];

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
  updateTable(1);

  // --- 互動工具 2：雷達圖 ---
  const ctx = document.getElementById('radarChart').getContext('2d');
  new Chart(ctx, {
    type: 'radar',
    data: {
      labels: ['抗震要求嚴格度', '計算複雜度', '產品認證門檻', '規範更新頻率'],
      datasets: [
        {
          label: '🇹🇼 TW 401-112',
          data: [90, 75, 85, 70],
          backgroundColor: 'rgba(210, 31, 60, 0.2)',
          borderColor: 'rgba(210, 31, 60, 1)',
          borderWidth: 2,
          pointBackgroundColor: 'rgba(210, 31, 60, 1)'
        },
        {
          label: '🇺🇸 ACI 318-19',
          data: [85, 80, 80, 90],
          backgroundColor: 'rgba(54, 162, 235, 0.2)',
          borderColor: 'rgba(54, 162, 235, 1)',
          borderWidth: 2,
          pointBackgroundColor: 'rgba(54, 162, 235, 1)'
        },
        {
          label: '🇪🇺 EN 1992-4',
          data: [80, 95, 95, 85],
          backgroundColor: 'rgba(255, 206, 86, 0.2)',
          borderColor: 'rgba(255, 206, 86, 1)',
          borderWidth: 2,
          pointBackgroundColor: 'rgba(255, 206, 86, 1)'
        }
      ]
    },
    options: {
      plugins: {
        legend: { position: 'top' }
      },
      scales: {
        r: { min: 40, max: 100, ticks: { display: false }, grid: { color: '#eee' } }
      }
    }
  });
</script>

---

### 💡 專家觀點：為什麼需要雙重折減？
在上述互動工具 1 中，當切換至 **高地震風險區** 時，你會發現台灣與美國規範皆出現了 `0.75 x 0.75` 的係數。
這是因為在地震力作用下，除了材料本身的強度折減外，還必須額外考量「混凝土開裂」與「負載循環」對剪力傳遞的負面影響。
