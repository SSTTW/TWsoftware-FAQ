---
layout: default
title: MOTW PROFIS Engineering FAQ
---

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  /* 全域與響應式風格 */
  body {
    color: #333;
    background-color: #ffffff;
    line-height: 1.8;
    font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif;
  }

  h1, h2, h3 {
    color: #D21F3C !important;
    border-bottom: 2px solid #D21F3C !important;
    padding-bottom: 12px !important;
    margin-top: 40px !important;
    font-weight: bold !important;
  }

  /* 下拉選單風格 */
  details {
    border: 1px solid #eee;
    border-radius: 8px;
    margin-bottom: 12px;
    padding: 12px 18px;
    background-color: #fafafa;
    transition: all 0.3s ease;
  }
  details:hover {
    border-color: #D21F3C;
    background-color: #ffffff;
    box-shadow: 0 4px 12px rgba(210, 31, 60, 0.08);
  }
  summary {
    font-size: 1.05em;
    font-weight: 600;
    color: #444;
    cursor: pointer;
    outline: none;
    list-style: none;
    display: flex;
    align-items: flex-start;
  }
  summary::before {
    content: "▶";
    color: #D21F3C;
    font-size: 0.8em;
    margin-right: 12px;
    margin-top: 5px;
    transition: transform 0.2s ease;
  }
  details[open] summary::before {
    transform: rotate(90deg);
  }
  details[open] summary {
    border-bottom: 1px solid #eee;
    padding-bottom: 10px;
    margin-bottom: 10px;
    color: #D21F3C;
  }

  /* 內容與圖片響應式 */
  .answer-content {
    padding: 10px 5px;
    color: #555;
  }
  img {
    border-radius: 6px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    margin: 15px 0;
    max-width: 100%; /* 確保圖片不超出手機螢幕 */
    height: auto;
    display: block;
  }

  a { color: #D21F3C; text-decoration: none; }
  a:hover { text-decoration: underline; }
  .site-footer, footer { display: none !important; }
  
  .back-btn {
    display: inline-block;
    padding: 8px 15px;
    background: #f0f0f0;
    color: #333 !important;
    border-radius: 5px;
    font-weight: bold;
    margin-bottom: 20px;
    font-size: 0.9em;
  }

  /* 規範專用框 */
  .regulation-box {
    background: #fdf2f3;
    border-left: 5px solid #D21F3C;
    padding: 15px 20px;
    margin-bottom: 30px;
    border-radius: 0 8px 8px 0;
  }
</style>

<a href="./" class="back-btn">← 回到首頁</a>

# 🏗️ MOTW PROFIS ENGINEERING FAQ

歡迎使用技術問答集。點擊問題可展開詳細解答與操作截圖。

---

## 📌 快速跳轉索引
* [🛠️ 軟體操作與系統設定](#軟體操作與系統設定)
* [⚖️ 法規、認證與標準](#法規認證相關)
* [📐 結構設計與力學分析 (CBFEM)](#結構設計與力學分析)
* [🏗️ 預埋槽 (Anchor Channel) 專區](#預埋槽專區)
* [💡 基礎知識與設計原理](#基礎知識與設計原理)

---

## <a name="軟體操作與系統設定"></a> 🛠️ 軟體操作與系統設定

<details>
<summary>Q: PROFIS Engineering 軟體的主要功能和優勢是什麼？</summary>
<div class="answer-content">
PROFIS Engineering 是一款專門用於優化錨栓與錨版設計的軟體。它能整合結構分析軟體，協助工程師快速確定底板和錨栓的設計載重，分析並設計錨栓和底板，並輸出設計結果與報告。主要優勢在於節省設計時間、即時更新規範、提供產品參數、解決工程師分開檢核的時間成本問題。
</div>
</details>

<details>
<summary>Q: 軟體功能多久會更新一次？</summary>
<div class="answer-content">
SaaS軟體每三到四週左右就會維修bug，針對功能上只要政府有調整法規，軟體會即時更新出相對應功能條件。
</div>
</details>

<details>
<summary>Q: 請問PROFIS Engineering要如何利用Excel輸入多重載重組合？</summary>
<div class="answer-content">
1. 先由結構計算軟體分析不同的載重組合<br>
<img src="./images/image%2011.png"><br>
2. 利用PE中的「導入荷載」將外力直接貼上<br>
<img src="./images/image%2012.png"><br>
<img src="./images/image%2013.png"><br>
3. 導入荷載後可以調整不同的外力軸向與方向(軟體預設為拉力為正，壓力為負)<br>
<img src="./images/image%2014.png"><br>
4. 調整輸入外力與彎矩單位<br>
<img src="./images/image%2015.png"><br>
5. 點擊應用，可一次輸入全部載重組合(一次最多1000種載重組合)<br>
<img src="./images/image%2016.png">
</div>
</details>

<details>
<summary>Q: PROFIS Engineering 可以將設計完的模型輸出成DWG檔，反向操作可以嗎？</summary>
<div class="answer-content">
反向的部分目前不行，輸入檔案僅能透過進階功能 CheckBot 輸入使用。<br>
1. 選擇 “輸出” <img src="./images/image%203.png"><br>
2. 選擇 “3D模型輸出” <img src="./images/image%204.png"><br>
3. 選擇 “輸出” <img src="./images/image%205.png"><br>
4. 選擇檔案形式 <img src="./images/image%206.png"><br>
5. 選擇輸出檔案類型 <img src="./images/image%207.png"><br>
6. 使用 AutoCAD 開啟 <img src="./images/image%208.png">
</div>
</details>

<details>
<summary>Q: 建好模型後如何更改檔名？</summary>
<div class="answer-content">
點選螢幕上方檔名，點擊設定圖示即可進入編輯。<br>
<img src="./images/image%209.png">
</div>
</details>

<details>
<summary>Q: 怎麼客製化表頭？</summary>
<div class="answer-content">
右上角 My report templates，選用自己的喜好設定。<br>
<img src="./images/image%2020.png"><br>
<img src="./images/image%2021.png"><br>
<img src="./images/image%2022.png">
</div>
</details>

<details>
<summary>Q: 如果沒有適合的型鋼呢？如何切換成其他形狀的型鋼？</summary>
<div class="answer-content">
設計種類繁多，如果真的沒有合適的型鋼截面，建議折衷方式：”自己算好慣性矩”，找一隻類似的型鋼做計算。<br>
若需切換其他標準（如正方形空心管）：<br>
Step 1 點選進入選擇型鋼類型 <img src="./images/image%2023.png"><br>
Step 2 點選此處切換標準 <img src="./images/image%2024.png"><br>
Step 3 選擇歐洲或美國標準即可找到更多型鋼 <img src="./images/image%2025.png">
</div>
</details>

<details>
<summary>Q: 軟體輸入外力的地方，可選擇「設計外力」或「可持續外力」，如何定義可持續外力？</summary>
<div class="answer-content">
可持續外力應用情境大多在吊掛、倒吊、側掛、帷幕、機台運作、隧道風機等，這類承受持續外力的情況易造成錨栓疲勞。
</div>
</details>

<details>
<summary>Q: SMART DESIGN 在 PROFIS Engineering 中的功能是什麼？</summary>
<div class="answer-content">
SMART DESIGN 根據大數據資料庫，提供設計者在不清楚產品資訊情況下，可以從專案類型透過系統推薦方便挑選產品，同時提供外力條件，系統會自動化計算完整配置。
</div>
</details>

<details>
<summary>Q: 如果已經建好一個模型了，是否能夠直接轉換不同的規範做計算？</summary>
<div class="answer-content">
不行。因為每個設計規範在計算上還是略有不同，所使用的參數也不一樣。因此如果需要更新設計規範，僅能重新新增一個客製化設計。
</div>
</details>

---

## <a name="法規認證相關"></a> ⚖️ 法規、認證與標準

<div class="regulation-box">
  <h3 style="margin-top:0 !important; border:none !important; color:#D21F3C;">🌍 適用法規與設計標準總覽</h3>
  <ul style="margin-bottom:0; color:#555; padding-left:20px;">
    <li><b>🇹🇼 台灣規範</b>：內政部「建築物混凝土結構設計規範」(土木401-112) 第17章 (自113年1月1日生效)。明訂錨栓須符合開裂混凝土要求與抵抗地震載重。</li>
    <li><b>🇺🇸 美國規範</b>：以 ACI 318-19 為基礎並考量 ACI 318-25。品質試驗參考 AC308, ACI 355.2。</li>
    <li><b>🇪🇺 歐洲規範</b>：ETAG 001, EAD 330232-00-0601。通過 DIBT/CSTB 實驗室測試之 ETA 認證。</li>
  </ul>
</div>

<details>
<summary>Q: 台灣沒有錨栓允收標準，那要使用怎麼辦？</summary>
<div class="answer-content">
台灣 CNS 有測試方法但無允收標準，因此建議參考美國規範 AC308 經過 ICC 實驗會出 ESR 認證；歐洲規範 ETAG 經過 DIBT/CSTB 實驗室測試出 ETA 認證。基本上有認證的 HILTI 產品 100% 會有 ETA 認證。
</div>
</details>

<details>
<summary>Q: 為什麼在結構設計中需要認真看待錨栓和緊固件的設計？</summary>
<div class="answer-content">
僅對主體結構進行抗震設計是不足夠的；過去事故顯示，若未認真處理緊固件，非結構性附掛物（如管線、設備）可能在地震時脫落。新的建築物混凝土結構設計規範中，明確規範必須使用有認證的混凝土結構用錨栓，且須符合開裂混凝土要求與抵抗地震載重。
</div>
</details>

<details>
<summary>Q: 如何確認一個錨栓是否具有抗震能力，並符合規範的地震要求 (C1/C2)？</summary>
<div class="answer-content">
確認錨栓抗震能力的關鍵是查看其 ICC-ESR 報告或 EOTA 報告。這些報告會顯示錨栓是否已通過在地震條件下的試驗，並註明其是否適用於開裂混凝土以及具備 C1 或 C2 等級的抗震能力。
</div>
</details>

<details>
<summary>Q: 在地震條件下，錨栓的承載能力與在靜止條件下有何不同？</summary>
<div class="answer-content">
地震條件下的錨栓試驗是在循環載荷、假設混凝土總是開裂、且裂縫寬度較大的情況下進行的。在地震情況下，錨栓的強度會顯著降低（差異約 1.5 倍）。
</div>
</details>

<details>
<summary>Q: 112年版RC規範 17.5.3 錨栓強度折減因數在哪調整？</summary>
<div class="answer-content">
計算錨栓折減係數可參考 ICC 報告（軟體無法手動更改）。若軟體計算選擇「狀態 A (有輔助鋼筋)」，則會根據報告直接對應到 17.5.3b 的折減係數。
</div>
</details>

<details>
<summary>Q: 如果想使用 HILTI 的產品 HUS 系列，為何無法在軟體上找到？</summary>
<div class="answer-content">
因產品 HUS 的認證測試報告為 ETA，選擇規範時需先選擇「歐盟規範」。<br>
<img src="./images/image%2026.png"><br>
<img src="./images/image%2028.png">
</div>
</details>

<details>
<summary>Q: HST3 想要調整埋深可以嗎？</summary>
<div class="answer-content">
美規測試要求在固定深度下進行測試，而歐規則沒有這樣的深度限制。建議可參照 ETAG-1992 標準進行設定。<br>
<img src="./images/image%2032.png">
</div>
</details>

---

## <a name="結構設計與力學分析"></a> 📐 結構設計與力學分析 (CBFEM)

<details>
<summary>Q: 平常都算剛性，為甚麼要算有限元素 (CBFEM)？</summary>
<div class="answer-content">
主要是因為實際狀況會有應力集中。建議可以先使用剛性做多重荷載計算，再將最大外力使用有限元素做分析，除了更安全之外也可與剛性同步做比較。
</div>
</details>

<details>
<summary>Q: 請問如付費版之柱基版分析，混凝土是採用何種邊界條件模擬？</summary>
<div class="answer-content">
CBFEM: 將混凝土視為「受壓彈簧」，錨栓視為「受拉彈簧」。有限元素法主要讓設計者能更貼近案場實際狀況。<br>
<img src="./images/image%2017.png"><br>
<img src="./images/image%2019.png">
</div>
</details>

<details>
<summary>Q: 為什麼材料強度顯示超過 2498 kgf/cm² 的圖像點？</summary>
<div class="answer-content">
報告為塑性設計，應力分佈到達最大值之後是 2498，因此超過的部分才沒有列出數值。但超過的部分若在 5% 內，有微量塑變也不影響整體設計安全。<br>
<img src="./images/image%2010.png">
</div>
</details>

<details>
<summary>Q: 剛性切換有限元素，會出現「偏差值」請問是什麼？</summary>
<div class="answer-content">
偏差值即為剛性與有限元素分析結果之間的差值。
</div>
</details>

<details>
<summary>Q: 為什麼剛性報告書顯示「未計算」，但仍提供建議厚度？</summary>
<div class="answer-content">
「
