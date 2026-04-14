---
layout: default
title: MOTW PROFIS Engineering FAQ
---

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  body { color: #333; background-color: #ffffff; line-height: 1.8; font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif; }
  h1, h2, h3 { color: #D21F3C !important; border-bottom: 2px solid #D21F3C !important; padding-bottom: 12px !important; margin-top: 40px !important; font-weight: bold !important; }
  details { border: 1px solid #eee; border-radius: 8px; margin-bottom: 12px; padding: 12px 18px; background-color: #fafafa; transition: all 0.3s ease; }
  details:hover { border-color: #D21F3C; background-color: #ffffff; box-shadow: 0 4px 12px rgba(210, 31, 60, 0.08); }
  summary { font-size: 1.05em; font-weight: 600; color: #444; cursor: pointer; outline: none; list-style: none; display: flex; align-items: flex-start; }
  summary::before { content: "▶"; color: #D21F3C; font-size: 0.8em; margin-right: 12px; margin-top: 5px; transition: transform 0.2s ease; }
  details[open] summary::before { transform: rotate(90deg); }
  details[open] summary { border-bottom: 1px solid #eee; padding-bottom: 10px; margin-bottom: 10px; color: #D21F3C; }
  .answer-content { padding: 10px 5px; color: #555; }
  img { border-radius: 6px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); margin: 15px 0; max-width: 100%; height: auto; display: block; }
  a { color: #D21F3C; text-decoration: none; }
  a:hover { text-decoration: underline; }
  .site-footer, footer { display: none !important; }
  .back-btn { display: inline-block; padding: 8px 15px; background: #f0f0f0; color: #333 !important; border-radius: 5px; font-weight: bold; margin-bottom: 20px; font-size: 0.9em; }
  .regulation-box { background: #fdf2f3; border-left: 5px solid #D21F3C; padding: 15px 20px; margin-bottom: 30px; border-radius: 0 8px 8px 0; }
</style>

<a href="./" class="back-btn">← 回到首頁</a>

# 🏗️ MOTW PROFIS ENGINEERING FAQ 

本技術庫整合了所有關於 PROFIS Engineering 軟體操作、力學原理及最新規範的常見問答。

---

## 📌 快速跳轉索引
* [🛠️ 軟體操作與功能設定](#軟體操作與功能設定)
* [⚖️ 法規、認證與標準](#法規認證相關)
* [📐 結構設計與力學分析 (CBFEM)](#結構設計與力學分析)
* [🏗️ 預埋槽 (Anchor Channel) 專區](#預埋槽專區)
* [💡 基礎知識與設計原理](#基礎知識與設計原理)

---

## <a name="軟體操作與功能設定"></a> 🛠️ 軟體操作與功能設定

<details>
<summary>Q: 請問PROFIS Engineering要如何利用Excel輸入多重載重組合？</summary>
<div class="answer-content">
1. 先由結構軟體分析載重組合：<img src="./images/image%2011.png"><br>
2. 利用「導入荷載」將外力貼上：<img src="./images/image%2012.png"> <img src="./images/image%2013.png"><br>
3. 調整軸向（拉力為正，壓力為負）：<img src="./images/image%2014.png"><br>
4. 點擊應用（一次最多 1000 種組合）：<img src="./images/image%2016.png">
</div>
</details>

<details>
<summary>Q: 建好模型後如何更改檔名？</summary>
<div class="answer-content">
點選螢幕上方檔名旁邊的「設定圖示」進入編輯：<br><img src="./images/image%209.png">
</div>
</details>

<details>
<summary>Q: 軟體功能多久更新一次？更新內容為何？</summary>
<div class="answer-content">
SaaS軟體每三到四週維修Bug。只要政府調整法規（例如台灣 113 年新規範），軟體會即時更新對應功能。
</div>
</details>

<details>
<summary>Q: 怎麼客製化表頭？</summary>
<div class="answer-content">
右上角 My report templates，可自定義 Logo 與專案資訊：<br>
<img src="./images/image%2020.png"> <img src="./images/image%2022.png">
</div>
</details>

---

## <a name="法規認證相關"></a> ⚖️ 法規、認證與標準

<div class="regulation-box">
  <h3 style="margin-top:0 !important; border:none !important; color:#D21F3C;">🌍 下載原始規範文件</h3>
  <ul style="margin-bottom:0; color:#555; padding-left:20px;">
    <li><a href="./土木401%20112.pdf" target="_blank">🇹🇼 台灣土木 401-112 (113/1/1 生效)</a></li>
    <li><a href="./ACI318%2019.pdf" target="_blank">🇺🇸 美國 ACI 318-19 規範</a></li>
    <li><a href="./ETAG-001-annex-c.pdf" target="_blank">🇪🇺 歐洲 ETAG 001 規範</a></li>
  </ul>
</div>

<details>
<summary>Q: 113年1月1日生效的「建築物混凝土結構設計規範」有何重點？</summary>
<div class="answer-content">
新規範（土木401-112 第十七章）要求錨栓須符合<b>開裂混凝土</b>要求並能抵抗<b>地震載重</b>。對於消防灑水、重型懸吊等安全相關附掛物，明確要求須使用有認證之錨栓。
</div>
</details>

<details>
<summary>Q: 如何確認錨栓是否具有抗震能力？</summary>
<div class="answer-content">
查閱 ICC-ESR 或 EOTA 報告。具備抗震能力的產品會標示通過 ACI 355.2 或 EAD 330232 測試，並註明 C1 或 C2 等級。<br>
<img src="./images/image%2033.png">
</div>
</details>

<details>
<summary>Q: 台灣沒有認證單位，那要如何參考認證？</summary>
<div class="answer-content">
台灣無認證單位。建議參考美國 <b>AC308 (ICC ESR)</b> 或歐洲 <b>ETAG (ETA)</b>。有認證的 Hilti 產品 100% 具有 ETA 認證。
</div>
</details>

---

## <a name="結構設計與力學分析"></a> 📐 結構設計與力學分析

<details>
<summary>Q: 為何材料強度達 2498kgf/cm2，但雲圖上出現超過此數值的點？</summary>
<div class="answer-content">
這是因為採用了<b>塑性設計</b>。應力達到最大值後會發生塑性應變。若超過部分不超過 5%，在規範下仍視為安全且不影響結構：<br>
<img src="./images/image%2010.png">
</div>
</details>

<details>
<summary>Q: 混凝土是採用何種邊界條件模擬？彈簧如何定義？</summary>
<div class="answer-content">
CBFEM 將混凝土視為<b>受壓彈簧</b>，錨栓視為<b>受拉彈簧</b>。相關楊氏係數公式可參考報告書附件：<br>
<img src="./images/image%2017.png"> <img src="./images/image%2019.png">
</div>
</details>

<details>
<summary>Q: 在單軸應力作用下，材料的縱向應變與橫向應變比值稱為什麼？</summary>
<div class="answer-content">
稱之為波松比 (Poisson's ratio)：<br>
<img src="./images/image%2031.png">
</div>
</details>

---

## <a name="預埋槽專區"></a> 🏗️ 預埋槽 (Anchor Channel) 專區

<details>
<summary>Q: 預埋槽除了 Facade 以外還有哪些應用？</summary>
<div class="answer-content">
1. <b>電梯設備</b>：導軌固定。<br>
2. <b>管線安裝</b>：風管、水管、電纜橋架。<br>
3. <b>設備固定</b>：機組、發電機架。
</div>
</details>

<details>
<summary>Q: 預埋槽完工後移動固定位置，會造成外力分布不均嗎？</summary>
<div class="answer-content">
正常施作下會完整咬合，不會有不均問題。PE 軟體會針對最嚴苛位置自動檢核。
</div>
</details>

---

## <a name="基礎知識與設計原理"></a> 💡 基礎知識與設計原理

<details>
<summary>Q: 機械錨栓 vs 化學錨栓 Nb 值初步判斷？</summary>
<div class="answer-content">
兩者考量因素不同。現場測試拉拔時，通常在鋼材拔出破壞前就已發生混凝土錐狀破壞。詳細報告參考：<br>
<img src="./images/image.png"> <img src="./images/image%201.png">
</div>
</details>

<details>
<summary>Q: 錨栓鋼板係數 1.5d 可以調整嗎？</summary>
<div class="answer-content">
根據 AISI S100，邊距不得小於 1.5d。若設計違反此條文軟體會顯示錯誤。但設計者可依工程判斷，手動輸入小於 1.50 的數值以降低對邊距的要求。
</div>
</details>

---

## 🙋‍♂️ 找不到答案？
[<img src="https://img.shields.io/badge/💬_點我提問-私密諮詢-red?style=for-the-badge&logo=googleforms">](https://forms.office.com/e/PngwicwAn8)

<p align="center">
  © 2026 Hilti Engineering Support Team | <b>MOTW 技術組</b> 維護
</p>
