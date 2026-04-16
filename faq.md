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

---

## 📌 快速跳轉索引
* [🛠️ 軟體操作與功能設定](#軟體操作與功能設定)
* [⚖️ 法規、認證與標準](#法規認證相關)
* [📐 結構設計與力學分析](#結構設計與力學分析)
* [🏗️ 預埋槽 (Anchor Channel) 專區](#預埋系統)
* [⚡ 機械與化學錨栓選型考量](#機械化學比較)

---

<div id="混凝土固定"></div>
## <a name="軟體操作與功能設定"></a> 🛠️ 軟體操作與功能設定

<details>
<summary>Q: 請問PROFIS Engineering要如何利用Excel輸入多重載重組合？</summary>
<div class="answer-content">
1. 先由結構軟體分析載重組合並複製。<br>
2. 在 PE 中點選「導入荷載」並貼上：<br>
<img src="./images/image11.png"><br>
3. 調整軸向與單位（拉力為正，壓力為負）：<br>
<img src="./images/image14.png"><br>
4. 點擊應用（一次最多支援 1000 種組合）：<br>
<img src="./images/image16.png"><br>
</div>
</details>

<details>
<summary>Q: 建好模型後如何更改檔名？</summary>
<div class="answer-content">
點選螢幕上方檔名旁邊的「設定圖示」即可重新編輯專案名稱：<br><img src="./images/image9.png">
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
<summary>Q: 113年1月1日生效的「建築物混凝土結構設計規範」有何重點？</summary>
<div class="answer-content">
新規範要求錨栓須考慮<b>開裂混凝土</b>及<b>地震載重 (Seismic Design)</b>。對於安全相關之附掛物，明確要求必須使用具有認證（如 ICC-ESR 或 ETA）的錨栓產品。
</div>
</details>

---

<div id="預埋系統"></div>
## 🏗️ 預埋槽 (Anchor Channel) 專區

<details>
<summary>Q: 預埋槽除了 Facade 以外還有哪些應用？</summary>
<div class="answer-content">
1. <b>電梯設備</b>：固定導軌與配重支架。<br>
2. <b>機電 MEP</b>：風管、水管與重型電纜橋架。<br>
3. <b>醫療設備</b>：手術室無影燈、設備滑軌固定。
</div>
</details>

---

<div id="機械化學比較"></div>
<div id="基礎知識與設計原理"></div>
## ⚡ 機械與化學錨栓：選型考量

<details open>
<summary>Q: 機械錨栓 vs 化學錨栓的 Nb 值與設計原理差異？</summary>
<div class="answer-content">
在 PROFIS Engineering 設計中，選型的主要考量如下：
<br><br>
1. **破壞模式**：機械錨栓靠擴張應力擠壓孔壁；化學錨栓則靠藥劑與混凝土膠結。<br>
2. **Nb 值 (混凝土錐狀破壞)**：現場測試時，通常化學錨栓的抗拔力上限受限於鋼材強度，而機械錨栓則較早發生混凝土破壞。<br>
3. **地震區建議**：高地震區建議優先考慮具備 C2 認證的化學錨栓（如 HIT-RE 500 V3），其對於較寬的裂縫有更佳的位移耐受度。
<br>
![Nb 值參考](./images/image.png)
</div>
</details>

<details>
<summary>Q: 如何手動輸入 1.5d 以下的邊距係數？</summary>
<div class="answer-content">
雖然 AISI S100 建議邊距不得小於 1.5d，但在 PE 軟體中，設計者可根據實際工程補強狀況，手動在參數欄位調整數值。若數值過低，軟體會顯示紅字警示，此時須檢核是否增加鋼板厚度或進行邊緣補強。
</div>
</details>

---

<div id="磚牆固定"></div>
## 🧱 磚牆固定 (Masonry) 專區
*(此區塊內容可根據未來需求補充，已預留錨點 ID)*

<details>
<summary>Q: 如何在 PE 中選擇磚牆基材？</summary>
<div class="answer-content">
在軟體首頁將「基材」切換為 Masonry 模式，即可針對空心磚、實心磚進行設計檢核。
</div>
</details>

---

## 🙋‍♂️ 找不到答案？
[<img src="https://img.shields.io/badge/💬_點我提問-私密諮詢-red?style=for-the-badge&logo=googleforms">](https://forms.office.com/e/PngwicwAn8)

<p align="center" style="margin-top: 50px; color: #888;">
  © 2026 Hilti Engineering Support Team | <b>MOTW 技術組</b> 維護
</p>
