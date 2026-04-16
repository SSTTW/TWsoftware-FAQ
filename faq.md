---
layout: default
title: MOTW PROFIS Engineering FAQ
---

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  /* 全域修正：防止內容溢出與跑版 */
  * { box-sizing: border-box; }
  body { color: #333; background-color: #ffffff; line-height: 1.8; font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif; overflow-x: hidden; }

  h1, h2, h3 { color: #D21F3C !important; border-bottom: 2px solid #D21F3C !important; padding-bottom: 12px !important; margin-top: 40px !important; font-weight: bold !important; }
  
  /* 摺疊面板優化 */
  details { border: 1px solid #eee; border-radius: 8px; margin-bottom: 12px; padding: 12px 18px; background-color: #fafafa; transition: all 0.3s ease; }
  details:hover { border-color: #D21F3C; background-color: #ffffff; box-shadow: 0 4px 12px rgba(210, 31, 60, 0.08); }
  summary { font-size: 1.05em; font-weight: 600; color: #444; cursor: pointer; outline: none; list-style: none; display: flex; align-items: flex-start; }
  summary::before { content: "▶"; color: #D21F3C; font-size: 0.8em; margin-right: 12px; margin-top: 5px; transition: transform 0.2s ease; }
  details[open] summary::before { transform: rotate(90deg); }
  details[open] summary { border-bottom: 1px solid #eee; padding-bottom: 10px; margin-bottom: 10px; color: #D21F3C; }
  
  .answer-content { padding: 10px 5px; color: #555; word-wrap: break-word; }
  
  /* 圖片響應式：確保手機版不超出螢幕 */
  img { border-radius: 6px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); margin: 15px 0; max-width: 100%; height: auto; display: block; }
  
  a { color: #D21F3C; text-decoration: none; }
  a:hover { text-decoration: underline; }
  
  /* 隱藏 Jekyll 預設頁尾 */
  .site-footer, footer { display: none !important; }
  
  .back-btn { display: inline-block; padding: 8px 15px; background: #f0f0f0; color: #333 !important; border-radius: 5px; font-weight: bold; margin-bottom: 20px; font-size: 0.9em; }
  .regulation-box { background: #fdf2f3; border-left: 5px solid #D21F3C; padding: 15px 20px; margin-bottom: 30px; border-radius: 0 8px 8px 0; }

  /* 手機版微調 */
  @media (max-width: 768px) {
    body { padding: 10px; }
    h1 { font-size: 1.6em; }
    summary { font-size: 0.95em; }
    .back-btn { width: 100%; text-align: center; }
  }
</style>

<a href="./" class="back-btn">← 回到首頁</a>

# 🏗️ MOTW PROFIS ENGINEERING FAQ 

本技術庫整合了軟體操作、力學原理及最新規範。點擊下方分類快速查看。

<div style="text-align: center; margin: 30px 0; position: relative;">
  <input type="text" id="search-input" placeholder="🔍 輸入關鍵字搜尋文章或手冊 (例如：ACI 318, 植筋)..." style="padding: 12px 20px; width: 100%; max-width: 500px; box-sizing: border-box; border-radius: 50px; border: 2px solid #fee2e5; font-size: 16px; outline: none; box-shadow: 0 4px 10px rgba(0,0,0,0.05);">
  <ul id="results-container" style="list-style: none; padding: 0; text-align: left; max-width: 500px; margin: 10px auto; background: white; border-radius: 12px; position: absolute; left: 0; right: 0; z-index: 1000; box-shadow: 0 10px 25px rgba(0,0,0,0.1);"></ul>
</div>

---

## 📌 快速跳轉索引
* [🛠️ 軟體操作與功能設定](#軟體操作與功能設定)
* [⚖️ 法規、認證與標準](#法規認證相關)
* [📐 結構設計與力學分析](#結構設計與力學分析)
* [🏗️ 預埋槽 (Anchor Channel) 專區](#預埋系統)
* [⚡ 機械與化學錨栓選型考量](#機械化學比較)
* [🧱 磚牆固定 (Masonry) 專區](#磚牆固定)

---

<div id="軟體操作與功能設定"></div>
## 🛠️ 軟體操作與功能設定

<details>
<summary>Q: PROFIS Engineering 軟體的主要功能和優勢是什麼？</summary>
<div class="answer-content">
PROFIS Engineering 是一款專門用於優化錨栓與錨版設計的軟體。它能整合結構分析軟體，協助工程師快速確定底板和錨栓的設計載重，分析並設計錨栓和底板，並輸出設計結果與報告。<br><br>
其主要優勢在於節省設計時間、即時更新規範、提供產品參數、解決工程師分開檢核與計算的時間成本問題，並提供全面的技術支援，協助工程師更有效率地完成符合建築規範且安全的專案設計。
</div>
</details>

<details>
<summary>Q: PROFIS Engineering 軟體如何協助設計者節省設計時間？</summary>
<div class="answer-content">
傳統的錨栓與錨版設計流程涉及多個步驟，包括結構分析、確定載重組合、錨栓與底板分析設計、以及輸出設計結果，總計可能需要 30 分鐘到 1.5 小時。<br>
PROFIS Engineering 透過整合載重輸入、自動選擇與分析錨栓方案、以及同步進行錨栓、錨版、混凝土基材、型鋼、加勁版與焊道的分析計算，顯著縮短了設計流程中的各個環節，有效節省了時間。
</div>
</details>

<details>
<summary>Q: PROFIS Engineering 在錨栓連接設計中提供了哪些關鍵能力？</summary>
<div class="answer-content">
1. <b>符合規範計算</b>：支援並整合最新的建築規範，例如國土署CH17（基於ACI 318）。<br>
2. <b>全面系統分析</b>：不只分析錨栓，還能同時針對錨栓、錨版、混凝土基材、型鋼、加勁版與焊道進行同時分析計算，解決分開計算的錯誤與時間成本。<br>
3. <b>多種載重處理</b>：可接受服務載重、從 Excel 導入，或手動輸入載重，並可同時運行高達 1000 個載重組合。<br>
4. <b>產品與規範整合</b>：整合產品參數，能根據優化偏好自動選擇高效的錨栓解決方案。
</div>
</details>

<details>
<summary>Q: SMART DESIGN 在 PROFIS Engineering 中的功能是什麼？</summary>
<div class="answer-content">
SMART DESIGN 根據大數據資料庫，提供設計者在不清楚產品資訊情況下，可以從專案類型透過系統推薦方便挑選產品。同時提供外力條件，系統會自動化計算完整配置。
</div>
</details>

<details>
<summary>Q: PROFIS Engineering 的功能介紹中提到了哪些設計應用？</summary>
<div class="answer-content">
包含：磚牆設計、後置鋼筋設計、磚體設計、錨固系統設計、Deck設計、欄杆扶手等，且會持續新增。
</div>
</details>

<details>
<summary>Q: 挑選產品技術手冊很麻煩要翻很久？</summary>
<div class="answer-content">
過去翻閱 FTM 確實相對耗時，軟體屬於 HILTI 工程服務，因此可透過提供外力分析進行快速選型進行一次性計算全部(剛性)，或者是挑選過去習慣的產品使用。
</div>
</details>

<details>
<summary>Q: 軟體功能多久會更新一次？</summary>
<div class="answer-content">
SaaS 軟體每三到四週左右就會維修 bug，針對功能上只要政府有調整法規，軟體會即時更新出相對應功能條件。
</div>
</details>

<details>
<summary>Q: 如果已經建好一個模型了，是否能夠直接轉換不同的規範做計算？</summary>
<div class="answer-content">
不行。因為每個設計規範在計算上還是略有不同，所使用的參數也不一樣。因此如果設計完成需要更新設計規範，僅能重新新增一個客製化設計。
</div>
</details>

<details>
<summary>Q: 建好模型後如何更改檔名？</summary>
<div class="answer-content">
點選螢幕上方檔名旁邊的「設定圖示」即可點進去編輯：<br>
<img src="./images/image 9.png">
</div>
</details>

<details>
<summary>Q: 如何切換成其他形狀的型鋼？</summary>
<div class="answer-content">
選擇型鋼類型上方將標準更換為其他國家的標準，即可有更多形狀的型鋼能夠選擇。<br>
(Ex: 如果需要選擇正方形空心型鋼)：<br>
Step 1: 點選進入選擇型鋼類型<br>
<img src="./images/image 23.png"><br>
Step 2: 點選此處切換標準<br>
<img src="./images/image 24.png"><br>
Step 3: 選擇歐洲標準即可找到正方形空心型鋼<br>
<img src="./images/image 25.png">
</div>
</details>

<details>
<summary>Q: 怎麼客製化表頭？</summary>
<div class="answer-content">
點擊右上角「My report templates」，選用自己的喜好設定：<br>
<img src="./images/image 20.png"><br>
<img src="./images/image 21.png"><br>
<img src="./images/image 22.png">
</div>
</details>

<details>
<summary>Q: 請問PROFIS Engineering要如何利用Excel輸入多重載重組合？</summary>
<div class="answer-content">
1. 先由結構計算軟體所分析不同的載重組合：<br>
<img src="./images/image 11.png"><br>
2. 利用 PE 中的導入荷載將外力直接貼上：<br>
<img src="./images/image 12.png"><br>
<img src="./images/image 13.png"><br>
3. 導入荷載後可以調整不同的外力軸向與方向 (軟體預設為拉力為正，壓力為負)：<br>
<img src="./images/image 14.png"><br>
4. 同時也可以調整輸入外力與彎矩單位：<br>
<img src="./images/image 15.png"><br>
5. 點擊應用並可一次輸入全部載重組合：<br>
<img src="./images/image 16.png">
</div>
</details>

<details>
<summary>Q: PROFIS Engineering 可以將設計完的模型輸出成DWG檔，請問反向操作可以嗎？</summary>
<div class="answer-content">
PROFIS Engineering 可以將設計完的模型輸出成 DWG 檔，反向的部分目前不行，輸入檔案僅能透過進階功能 CheckBot 輸入使用。<br>
1. 選擇「輸出」：<br>
<img src="./images/image 3.png"><br>
2. 選擇「3D模型輸出」：<br>
<img src="./images/image 4.png"><br>
3. 選擇「輸出」：<br>
<img src="./images/image 5.png"><br>
4. 點擊選擇檔案形式：<br>
<img src="./images/image 6.png"><br>
5. 選擇輸出檔案類型：<br>
<img src="./images/image 7.png"><br>
6. 使用 AutoCAD 開啟：<br>
<img src="./images/image 8.png">
</div>
</details>

<details>
<summary>Q: PROFIS Engineering 一次可以計算多少載重組合？</summary>
<div class="answer-content">
剛性設計可以同時運行 1000 個載重組合；CBFEM (有限元素) 可以同時運行 20 個載重組合。
</div>
</details>

---

<div id="法規認證相關"></div>
## ⚖️ 法規、認證與標準

<div class="regulation-box">
  <h3 style="margin-top:0 !important; border:none !important; color:#D21F3C;">🌍 原始規範文件下載</h3>
  <ul style="margin-bottom:0; color:#555; padding-left:20px;">
    <li><a href="./土木401%20112.pdf" target="_blank">🇹🇼 台灣土木 401-112 (113/1/1 生效)</a></li>
    <li><a href="./ACI318%2019.pdf" target="_blank">🇺🇸 美國 ACI 318-19 規範</a></li>
    <li><a href="https://www.eota.eu/en-gb/content/eads/56/" target="_blank">🇪🇺 EOTA / EAD 歐洲技術評估準則 (EADs)</a></li>
  </ul>
</div>

<details>
<summary>Q: 內政部修正「混凝土結構設計規範」為「建築物混凝土結構設計規範」是何時生效的？</summary>
<div class="answer-content">
自中華民國 113 年 1 月 1 日生效。規範中明訂錨栓須符合開裂混凝土要求與抵抗地震載重，由於無法確保混凝土在多年使用之後不會有開裂問題，規範定義上裂縫大於 0.3mm 就算是開裂，因此在計算過程要使用開裂混凝土。
</div>
</details>

<details>
<summary>Q: 台灣新的「建築物混凝土結構設計規範」(112年版) 中，關於錨栓的規範是依據什麼？適用範圍為何？</summary>
<div class="answer-content">
這份規範是以美國 ACI 318-19 規範為基礎，並考量納入下版 ACI 318-25 的重要內容修訂而成。其中第十七章「混凝土結構用錨栓」適用於結構構件與<b>非屬結構但與安全有關之附掛物</b>的結合，例如消防灑水系統、重型懸吊管或安全欄杆等。相關品質試驗方法建議參考美國混凝土學會的 ACI 355.2 和 ACI 355.4。
</div>
</details>

<details>
<summary>Q: 為什麼在地震多發地區需要特別重視錨栓的抗震設計？</summary>
<div class="answer-content">
台灣位於環太平洋地震帶，地震頻繁。過去的事故顯示，僅對主體結構進行抗震設計是不夠的，非結構性附掛物（如管線、設備等）的緊固件若設計不當，可能在地震時脫落，造成重大危險。新的規範也明確要求與安全有關的附掛物必須使用有認證的混凝土結構用錨栓並進行適當的抗震設計。
</div>
</details>

<details>
<summary>Q: 台灣沒有錨栓允收標準，那要使用怎麼辦？</summary>
<div class="answer-content">
補充說明：CNS 有測試方法但無允收標準。因此建議參考美國規範 AC308，經過 ICC 實驗會出 ESR 認證；或參考歐洲規範 ETAG 經過 DIBT / CSTB 實驗室測試出 ETA 認證。<br>
*HILTI產品生產之後經過實驗室測試，基本上有認證的 HILTI 產品 100% 會有 ETA 認證。
</div>
</details>

<details>
<summary>Q: 112年版RC規範章節17.5.3後置式錨栓分為三類，且有強度折減因數，請問軟體須於何處調整？</summary>
<div class="answer-content">
PE 的輔助鋼筋設計 a & b 狀態，計算錨栓折減係數可參考 ICC 報告，係數會因產品不同而有所不同（軟體無法手動更改）。<br>
舉例來說：機械錨栓 HST3 ICC報告書會明確定義折減係數，若軟體計算過程選擇狀態 A (有輔助鋼筋設置條件)，則會對應報告中折減係數來計算（剪力則無影響）。
</div>
</details>

<details>
<summary>Q: 錨栓耐震設計需求-荷載類型 規範章節（17.10）如何辨識？</summary>
<div class="answer-content">
<img src="./images/image 33.png">
</div>
</details>

<details>
<summary>Q: 如何確認一個錨栓是否具有抗震能力，並符合規範的地震要求 (C1/C2)？</summary>
<div class="answer-content">
確認錨栓抗震能力的關鍵是查看其 <b>ICC-ESR報告</b> 或 <b>EOTA報告</b>，這些報告會顯示錨栓是否已通過在地震條件下的試驗，並註明其是否適用於開裂混凝土 (Cracked Concrete) 以及具備 C1 或 C2 等級的抗震能力。
</div>
</details>

---

<div id="結構設計與力學分析"></div>
## 📐 結構設計與力學分析

<details>
<summary>Q: 平常都算剛性，為甚麼要算有限元素 (CBFEM)？</summary>
<div class="answer-content">
主要是因為實際狀況會有應力集中，確實台灣沒有特別規定，建議可以先使用剛性做多重荷載計算，再將最大外力使用有限元素做分析，除了更安全之外也可與剛性同步做比較。
</div>
</details>

<details>
<summary>Q: 剛性切換有限元素，會出現”偏差值”請問是什麼？</summary>
<div class="answer-content">
剛性計算後切換有限元素，偏差值即為剛性與有限元素之間的數值差值。
</div>
</details>

<details>
<summary>Q: 為什麼剛性報告書顯示「未計算」，但仍提供建議厚度？</summary>
<div class="answer-content">
根據 <b>ETAG 001 附錄 C</b> 中的標準建議值直接提供設計建議：<br>
1. 當設計拉力小於規範最大值時，可不進行具體計算。<br>
2. 若剪力設計未考慮混凝土邊緣效應，則可直接使用附表中的建議厚度。<br>
3. 若剪力設計有考慮邊緣效應，則使用第 6 節的建議厚度。<br><br>
<b>總結：</b>「未計算」代表軟體未執行剛性分析模擬（如有限元素分析）。「建議厚度」則是根據經驗值或表格數據提供的預設建議，屬於簡化設計方法的一部分。
</div>
</details>

<details>
<summary>Q: 請問如付費版之柱基版分析，混凝土是採用何種邊界條件模擬？</summary>
<div class="answer-content">
CBFEM：將混凝土視為受壓彈簧，錨栓視為受拉彈簧。有限元素法主要讓設計者能更貼近案場實際狀況。<br>
<img src="./images/image 17.png"><br>
<img src="./images/image 18.png"><br>
<img src="./images/image 19.png">
</div>
</details>

<details>
<summary>Q: CBFEM網格是否可以調整？</summary>
<div class="answer-content">
“進階錨板計算設定”下拉即可自定義，也可調整”鋼筋網(網格)Mesh”。
</div>
</details>

<details>
<summary>Q: 如果沒有適合的型鋼呢？</summary>
<div class="answer-content">
設計種類繁多，如果真的沒有合適的型鋼截面，建議可使用的折衷方式為”自己算好慣性矩”，找一隻類似的型鋼做替代計算。
</div>
</details>

<details>
<summary>Q: 錨版的材質是對當地的代號嗎？</summary>
<div class="answer-content">
材質的代號是世界通用的代號，並非僅針對當地的代號。
</div>
</details>

<details>
<summary>Q: 邊緣加固如果我知道鋼筋尺寸可以做選擇嗎？</summary>
<div class="answer-content">
軟體是跟著規範走 (401-112 17.7.2.5.1)，所以邊緣加固目前規範是指 4 號鋼筋，不過大於 4 號鋼筋給的反力更多，因此用 4 號鋼筋是最保守的算法。<br><br>
<b>簡述AB狀態：</b><br>
混凝土受拉造成錐狀破壞時，底下是否有鋼筋箍筋穿越，可否提供更多反力？建議依照技師判斷進行勾選。ex 水平鋼筋可選擇 A 狀態；反之，若為垂直向鋼筋或是無鋼筋箍筋，則發生破壞時無法提供更多反力，則選 <b>B 條件</b>。
</div>
</details>

<details>
<summary>Q: 懸臂裡面有一個”旋轉約束”如何選擇？</summary>
<div class="answer-content">
<b>α係數1 = 無約束；α係數2 = 完全約束。</b> ETAG 可參考 4.2.2.4 規範 (α係數介於 1～2)。<br>
<img src="./images/image 2.png">
</div>
</details>

<details>
<summary>Q: 軟體都使用什麼設計方式？</summary>
<div class="answer-content">
早期技師在計算上會使用 ASD，PE 軟體都是使用 <b>LRFD (負載與阻力因子設計)</b> 設計方式。
</div>
</details>

<details>
<summary>Q: 材料強度僅到達2498kgf/cm2，為何圖像中會有超過的圖像點？</summary>
<div class="answer-content">
報告看的是塑性設計，應力分佈到達最大值之後是 2498 因此超過的部分才沒有列出數值，但是超過的部分不超過 5%，有塑變也不影響設計。<br>
<img src="./images/image 10.png">
</div>
</details>

<details>
<summary>Q: 在單軸應力作用下，材料的縱向應變與橫向應變的比值稱為什麼？</summary>
<div class="answer-content">
<img src="./images/image 31.png">
</div>
</details>

<details>
<summary>Q: 輸入外力可選擇「設計外力」或「可持續外力」，如何定義可持續外力？</summary>
<div class="answer-content">
可持續外力應用情境大多在吊掛、倒吊、側掛、帷幕、機台運作、隧道風機 etc., 承受可持續外力易造成錨栓疲勞。
</div>
</details>

<details>
<summary>Q: 耐震設計與靜態設計差異性？</summary>
<div class="answer-content">
若使用地震載重，軟體會將強度折減兩次，由於折減兩次因此地震載重 & 靜態載重差異性約莫 1.5 倍，可由客戶端進行判斷是否使用耐震設計。
</div>
</details>

<details>
<summary>Q: 混凝土 λα 以及 λ 該如何分辨報告書中的計算方式？</summary>
<div class="answer-content">
根據土木 401 第 2 章 P17 λ, λα 有詳細表述定義。參考 17.2.4.1 λα 輕質混凝土修正係數；參考 19.2.4 詳細定義輕質混凝土 & 常重混凝土 λ 值為何。
</div>
</details>

<details>
<summary>Q: PE裡面 Plate design 不同類型的應用情境？</summary>
<div class="answer-content">
以客戶要固定的東西為主，沒有特別規定。
</div>
</details>

<details>
<summary>Q: Stand-off type 應用情境？</summary>
<div class="answer-content">
一般固定。灌漿：若將 HAC 灌漿則無法再移動。
</div>
</details>

<details>
<summary>Q: Anchor reinforcement 是什麼？</summary>
<div class="answer-content">
應用時機：1. 拉力大 2. 剪力大 3. 邊距小。這項功能主要是軟體自主配筋，參考 ACI318。
</div>
</details>

<details>
<summary>Q: 沒有底板時無法輸入彎矩的原因？</summary>
<div class="answer-content">
Bolt 本身不吃彎矩，要設置底板才有 M 方向外力可輸入。
</div>
</details>

<details>
<summary>Q: 專案類型上轉角設計功能，合力是在中心點嗎？</summary>
<div class="answer-content">
客戶需要自行將合力分析成單邊分力，再丟到軟體裡面進行計算。轉角設計功能主要是檢核轉角位置，避免內部預埋件相撞，輸入外力之後單純做單邊計算。
</div>
</details>

<details>
<summary>Q: Deck版可以分析嗎？</summary>
<div class="answer-content">
國家選擇「美國」即可分析。
</div>
</details>

<details>
<summary>Q: 錨固到混凝土 / 磚牆的常見應用？</summary>
<div class="answer-content">
<b>錨固到混凝土：</b>包括柱底板、梁到混凝土的連接、角鋼與混凝土的連接。<br>
<b>錨固到磚牆：</b>包括梁到磚石、角鋼與磚石的連接。
</div>
</details>

<details>
<summary>Q: C2C在新舊混凝土接合方面，PE 相關的應用與分類？</summary>
<div class="answer-content">
市面上植筋幾乎可以分成三種狀態：<br>
1. <b>結構延伸</b>：可參考土木 401-25 章，基本達成發展長度。<br>
2. <b>新結構物</b>：現場狀況不一定可以達到發展深度，可參考 HILTI 經過義大利學者提出的論文設計做法，沿用 401-17 章設計方式。<br>
3. <b>剪力牆</b>：可參考土木 401-22 章，剪力的部分純看鋼筋截面積，參考 22 章節計算。
</div>
</details>

<details>
<summary>Q: 為什麼在結構設計中需要認真看待錨栓和緊固件的設計？</summary>
<div class="answer-content">
緊固件的設計應如同結構構件一樣被認真對待。僅對主體結構進行抗震設計是不足夠的，過去的事故顯示，如果未認真處理緊固件，可能構成重大威脅。台灣地震頻繁，新的規範中明確要求必須使用<b>有認證</b>的混凝土結構用錨栓，並符合<b>開裂混凝土要求</b>與<b>抵抗地震載重</b>。
</div>
</details>

<details>
<summary>Q: PROFIS Engineering 的錨板係數預設是 1.5，可以調整嗎？</summary>
<div class="answer-content">
根據 AISI S100 規定「錨固件中心至邊緣的距離不得小於 1.5 倍直徑」。由於 1.5 是預設值，若設計違反此條文，軟體會顯示錯誤訊息提醒。不過，設計者可依據工程判斷適度調整數值，若有特殊需求可以手動輸入小於 1.50 的數值。
</div>
</details>

---

<div id="預埋系統"></div>
## 🏗️ 預埋槽 (Anchor Channel) 專區

<details>
<summary>Q: 通常做預埋比較多，後置不可控制因素太多？</summary>
<div class="answer-content">
錨固設計四個構件徒手計算會很麻煩，PE 軟體設計就可以協助解決這個問題。預埋很容易在現場施工狀況造成設計破壞（像是灌漿不小心把預留孔蓋過），這也是台灣很常見後置設計的原因。
</div>
</details>

<details>
<summary>Q: 槽式預埋件（HILTI HAC槽道）主要應用於哪些場景？</summary>
<div class="answer-content">
1. <b>建築外立面（Façade）</b>：用於幕牆、玻璃帷幕牆等結構，確保穩固安裝並提供調整空間。<br>
2. <b>電梯設備（Elevator）</b>：作為電梯導軌、支撐結構的固定基礎，確保運行穩定。<br>
3. <b>管線安裝（Piping）</b>：適用於水管、通風管道、電纜橋架的固定。<br>
4. <b>混凝土結構安裝</b>：在樓板、梁柱、牆體等部位預埋，以便後續安裝設備。<br>
5. <b>設備固定</b>：大型設備如空調機組、發電機、機械支撐架等。
</div>
</details>

<details>
<summary>Q: 功能裡TOLERANCE指的是什麼？</summary>
<div class="answer-content">
底板可調整範圍，系統會計算最嚴峻的，一次件與二次件之間的公差範圍越小越精準。
</div>
</details>

<details>
<summary>Q: Number of anchors指的是剪力釘嗎？能不能做調整？</summary>
<div class="answer-content">
對，就是 Anchor Leg，不能調整。
</div>
</details>

<details>
<summary>Q: HAC-V & HAC-T 差別？</summary>
<div class="answer-content">
V 無牙，相對彈性；T 有牙，增加咬住的力。台灣目前沒有 T 產品但可以從總部購買。
</div>
</details>

<details>
<summary>Q: Fastening technology 三個指令的差異？勾選時機？</summary>
<div class="answer-content">
系統提供預埋槽設計方式，也提供後置功能。假如客戶緊急需要調整可使用後置；若希望重新配置建議使用底板功能計算。
</div>
</details>

<details>
<summary>Q: inspection type指的是什麼？</summary>
<div class="answer-content">
查驗頻率：<br>
Continuous inspection：折減較少<br>
Period inspection：折減較多
</div>
</details>

<details>
<summary>Q: 預埋槽要怎麼固定？</summary>
<div class="answer-content">
Anchor Channel 上面有預留孔洞可以用錨栓固定。
</div>
</details>

<details>
<summary>Q: 預埋槽完工後可以移動被固定物位置，會不會造成外力分布不均？</summary>
<div class="answer-content">
正常施作情況下會是完整咬合，不會有外力分布不均的問題。
</div>
</details>

---

<div id="機械化學比較"></div>
## ⚡ 機械與化學錨栓：選型考量

<details>
<summary>Q: 後置式錨栓有哪些主要類型？原理有何不同？</summary>
<div class="answer-content">
<b>機械錨栓：</b>包含膨脹式、切底式和螺紋錨，主要依靠<b>摩擦力</b>或<b>鎖鍵力</b>將抗力集中在混凝土的底部或鑽孔壁。<br>
<b>化學錨栓：</b>透過化學藥劑產生的<b>黏著力</b>，將力量分散地傳遞到混凝土中，填充螺桿與混凝土之間的孔隙。
</div>
</details>

<details>
<summary>Q: 機械錨栓和化學錨栓各有哪些優缺點差異？</summary>
<div class="answer-content">
<b>機械錨栓：</b><br>
優點是安裝後可立即達到設計力值，安裝流程通常較簡易，對清孔程度和工作環境溫度較不敏感。缺點是埋深大多固定，且需要較大的邊間距。<br>
<b>化學錨栓：</b><br>
優點是可符合較小邊間距的需求，可搭配不同物件（螺紋桿件和鋼筋），可用於較深埋深與不同基材。缺點是無法立即受力，需要等待化學藥劑凝固，且對清孔要求較為嚴謹。
</div>
</details>

<details>
<summary>Q: 機械跟化學 Anchor 是否能初步判斷 Nb 值？</summary>
<div class="answer-content">
兩者考量因素不同，現場測試拉拔的時候，通常在發生鋼材拔出破壞之前，就已經發生混凝土錐狀破壞了。<br>
<img src="./images/image 1.png">
</div>
</details>

<details>
<summary>Q: 在地震條件下，錨栓承載力與靜止 / 非開裂混凝土有何不同？</summary>
<div class="answer-content">
地震條件下的試驗是在<b>循環載荷</b>、假設混凝土總是<b>開裂</b>、且裂縫寬度較大的情況下進行。在地震情況下，錨栓的強度<b>會顯著降低</b>，例如 M8 錨栓在開裂混凝土地震條件下的拔出抗力遠低於非開裂或開裂靜止條件。
</div>
</details>

<details>
<summary>Q: 在錨栓設計中，正確的安裝為什麼非常重要？</summary>
<div class="answer-content">
即使設計正確，如果安裝不當也無法發揮性能。特別是化學錨栓，清孔步驟至關重要以確保黏著力；對於機械錨栓，按照規定的安裝力矩進行安裝才能確保承載力。
</div>
</details>

<details>
<summary>Q: 設計一個錨栓連接需要考量哪些破壞模式？</summary>
<div class="answer-content">
對於拉力：考量鋼材破壞、混凝土拉拔破壞、劈裂破壞以及邊緣破壞。<br>
對於剪力：考量鋼材破壞、混凝土剪力破壞（包含邊緣破壞和撐壓破壞）以及栓桿群效應。<br>
最終強度必須取所有可能破壞模式中計算出的<b>最低抗力值</b>。
</div>
</details>

<details>
<summary>Q: 如果剛好收到國外的設計，台灣沒有符合的產品怎麼辦？</summary>
<div class="answer-content">
可以提早通知我們的業務進行產品庫存確認，如有需要可從國外調貨空運或海運。
</div>
</details>

<details>
<summary>Q: 想使用 HUS 系列，為何有些產品無法在軟體上找到？</summary>
<div class="answer-content">
因 HUS 產品的認證測試報告為 ETA，選擇規範時需先選擇「歐盟」的規範才找得到。<br>
<img src="./images/image 26.png"><br>
<img src="./images/image 27.png"><br>
<img src="./images/image 28.png"><br>
<img src="./images/image 29.png"><br>
<img src="./images/image 30.png">
</div>
</details>

<details>
<summary>Q: HST3想要調整埋深可以嗎？</summary>
<div class="answer-content">
美規測試要求在固定深度下進行測試，而歐規則沒有這樣的深度限制。因此，在機械錨栓的設計部分，建議可參照 ETAG-1992 標準進行設定來調整埋深。<br>
<img src="./images/image 32.png">
</div>
</details>

<details>
<summary>Q: HKD在軟體裡面如何選擇？</summary>
<div class="answer-content">
HKD 通常會打在倒吊面，由於機械錨栓需要使用多冗設計，單根不列入開裂認證，在軟體設計上無法模擬多冗設計，因此選擇時需要將「開裂」選項勾掉才可計算。
</div>
</details>

<details>
<summary>Q: 玻璃欄杆 HIT-Glass Method 中，若單側配置 3 顆砂漿墊塊，中心間距為多少？</summary>
<div class="answer-content">
23 cm。符合總自由空間為 46 cm，兩個砂漿墊塊的最大間距為 45.72 cm。
</div>
</details>

---

## 🙋‍♂️ 找不到答案？？
[<img src="https://img.shields.io/badge/💬_點我提出問題-red?style=for-the-badge&logo=googleforms">](https://forms.office.com/e/PngwicwAn8)

<p align="center" style="margin-top: 50px; color: #888;">
  © 2026 Hilti Engineering Support Team | <b>MOTW 技術組</b> 維護
</p>
