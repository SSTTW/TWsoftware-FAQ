---
layout: default
title: MOTW PROFIS Engineering FAQ
---

<style>
  /* 1. 全域風格：簡約白底黑字 */
  body {
    color: #333;
    background-color: #ffffff;
    line-height: 1.8;
    font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif;
  }

  /* 2. 標題風格：深紅輪廓線 */
  h1, h2, h3 {
    color: #D21F3C !important;
    border-bottom: 2px solid #D21F3C !important;
    padding-bottom: 12px !important;
    margin-top: 40px !important;
    font-weight: bold !important;
  }

  /* 3. Notion 風格下拉選單 (Toggle) */
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
    align-items: center;
  }

  summary::before {
    content: "▶";
    color: #D21F3C;
    font-size: 0.8em;
    margin-right: 12px;
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

  .answer-content {
    padding: 10px 5px;
    color: #555;
  }

  img {
    border-radius: 6px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    margin: 15px 0;
    max-width: 100%;
    display: block;
  }

  a { color: #D21F3C; text-decoration: none; }
  a:hover { text-decoration: underline; }
  .site-footer, footer { display: none !important; }
</style>

# 🏗️ MOTW PROFIS ENGINEERING FAQ

歡迎使用技術問答集。點擊問題可展開詳細解答與操作截圖。

> [!NOTE]
> **法規更新提醒**：內政部「建築物混凝土結構設計規範」已於 113 年 1 月 1 日正式生效，要求錨栓須符合開裂混凝土與抗震要求。

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
<summary>Q: 軟體功能多久會更新一次？</summary>
<div class="answer-content">
SaaS 軟體每三到四週左右就會維修 Bug。針對功能上，只要政府調整法規，軟體會即時更新相對應的功能條件。
</div>
</details>

<details>
<summary>Q: 建好模型後如何更改檔名？</summary>
<div class="answer-content">
點選螢幕上方檔名旁邊的「設定」圖示，即可進入編輯。
![更改檔名](./images/image%209.png)
</div>
</details>

<details>
<summary>Q: 如何利用 Excel 輸入多重載重組合？</summary>
<div class="answer-content">
1. 先由結構軟體分析載重組合並複製：<br>
![Excel 1](./images/image%2011.png)<br>
2. 在 PE 中點選「導入荷載」並貼上：<br>
![Excel 2](./images/image%2012.png) ![Excel 3](./images/image%2013.png)<br>
3. 調整軸向與單位（拉力為正，壓力為負）：<br>
![Excel 4](./images/image%2014.png) ![Excel 5](./images/image%2015.png)<br>
4. 點擊應用（一次最多支援 1000 種組合）：<br>
![Excel 6](./images/image%2016.png)
</div>
</details>

<details>
<summary>Q: 模型可以輸出成 DWG 檔嗎？反向匯入可以嗎？</summary>
<div class="answer-content">
目前支援「正向輸出（PE 轉 DWG）」，但不支援反向匯入。步驟如下：<br>
1. 點擊「輸出」 -> 「3D 模型輸出」。<br>
![輸出步驟](./images/image%203.png) ![輸出步驟](./images/image%204.png)<br>
2. 選擇檔案形式並匯出。<br>
![輸出步驟](./images/image%206.png) ![輸出步驟](./images/image%207.png)<br>
3. 使用 AutoCAD 開啟。<br>
![DWG 成果](./images/image%208.png)
</div>
</details>

<details>
<summary>Q: 怎麼客製化報告表頭？</summary>
<div class="answer-content">
進入右上角 <b>My report templates</b>，即可選用自己的喜好設定 Logo 或資訊。<br>
![表頭設定](./images/image%2020.png) ![表頭設定](./images/image%2021.png)
</div>
</details>

<details>
<summary>Q: 如果沒有適合的型鋼截面怎麼辦？</summary>
<div class="answer-content">
建議折衷方式：先「自行計算好慣性矩」，然後在軟體中找一隻尺寸最接近的型鋼做計算。
</div>
</details>

<details>
<summary>Q: 如何切換成其他國家的型鋼標準（例如正方形空心管）？</summary>
<div class="answer-content">
點選型鋼選擇區，將標準更換為歐洲或美國標準，即可找到更多形狀。<br>
![切換標準](./images/image%2023.png) ![切換標準](./images/image%2024.png) ![成果](./images/image%2025.png)
</div>
</details>

---

## <a name="法規認證相關"></a> ⚖️ 法規、認證與標準

<details>
<summary>Q: 台灣沒有錨栓允收標準，要如何設計？</summary>
<div class="answer-content">
台灣 CNS 目前僅有測試方法但無允收標準。建議參考：<br>
1. <b>美國規範 AC308</b>：經 ICC 實驗室核發之 ESR 認證。<br>
2. <b>歐洲規範 ETAG/EAD</b>：經 DIBT/CSTB 實驗室核發之 ETA 認證。<br>
Hilti 有認證的產品 100% 具有 ETA 認證。
</div>
</details>

<details>
<summary>Q: 112 年版 RC 規範 17.5.3 的強度折減因數在哪調整？</summary>
<div class="answer-content">
軟體根據 ICC 報告自動定義（無法手動更改）。係數會因產品不同而異。當您勾選「狀態 A（有輔助鋼筋）」或「狀態 B（無輔助鋼筋）」時，軟體會自動對應至規範分類。
</div>
</details>

<details>
<summary>Q: 如何確認錨栓具備抗震能力 (C1/C2)？</summary>
<div class="answer-content">
請查閱產品的 <b>ICC-ESR 或 EOTA 報告</b>。報告中會註明是否通過循環載荷試驗，並標示其在開裂混凝土中的 C1/C2 抗震等級。
![抗震辨識](./images/image%2033.png)
</div>
</details>

<details>
<summary>Q: HUS 系列產品在軟體中找不到？</summary>
<div class="answer-content">
因為 HUS 產品的認證報告主要是 ETA (歐規)，請先在設計規範中選擇「歐盟規範」即可顯示該系列。<br>
![選擇歐規](./images/image%2026.png) ![顯示產品](./images/image%2028.png)
</div>
</details>

---

## <a name="結構設計與力學分析"></a> 📐 結構設計與力學分析 (CBFEM)

<details>
<summary>Q: 為何要算有限元素 (CBFEM)？剛性分析不夠嗎？</summary>
<div class="answer-content">
實際狀況下底板會有<b>應力集中</b>。剛性分析假設底板永遠平整，但這在薄底板或大載重下不成立。建議先用剛性做多重荷載篩選，再針對最大外力使用 CBFEM 分析，同步比較安全性。
</div>
</details>

<details>
<summary>Q: 混凝土是採用何種邊界條件模擬？彈簧如何定義？</summary>
<div class="answer-content">
CBFEM 將混凝土視為<b>受壓彈簧</b>，錨栓視為<b>受拉彈簧</b>。相關楊氏模數與公式可參考報告書附件。<br>
![彈簧模擬](./images/image%2017.png) ![參數設定](./images/image%2019.png)
</div>
</details>

<details>
<summary>Q: 為什麼材料強度顯示超過 2498 kgf/cm² 的圖像點？</summary>
<div class="answer-content">
這代表進入了<b>塑性設計</b>。軟體顯示的是塑性應變分佈，若超過部分在 5% 以內，微量塑變在設計上被視為安全可接受。<br>
![應力分析](./images/image%2010.png)
</div>
</details>

<details>
<summary>Q: 邊緣加固鋼筋尺寸可以手動選擇嗎？</summary>
<div class="answer-content">
規範 (401-112 17.7.2.5.1) 目前預設為 4 號鋼筋。若現場使用大於 4 號的鋼筋，其提供的反力更高，因此軟體使用 4 號設定是最保守安全的算法。
</div>
</details>

<details>
<summary>Q: 懸臂設計中的「旋轉約束 α 係數」如何選？</summary>
<div class="answer-content">
根據 ETAG 4.2.2.4：<br>
- <b>α = 1</b>：無約束。<br>
- <b>α = 2</b>：完全約束。<br>
![旋轉約束](./images/image%202.png)
</div>
</details>

---

## <a name="預埋槽專區"></a> 🏗️ 預埋槽 (Anchor Channel) 專區

<details>
<summary>Q: 預埋槽 (HAC) 除了幕牆外還有哪些應用？</summary>
<div class="answer-content">
1. <b>電梯設備</b>：導軌與支撐固定。<br>
2. <b>管線安裝</b>：水管、通風管、電纜橋架。<br>
3. <b>混凝土結構</b>：樓板或梁柱預留安裝點。<br>
4. <b>設備固定</b>：大型機組或機械支架。
</div>
</details>

<details>
<summary>Q: HAC-V 與 HAC-T 差別在哪？</summary>
<div class="answer-content">
- <b>HAC-V</b>：無齒牙，位置調整較具彈性。<br>
- <b>HAC-T</b>：具備齒牙，可增加咬住力（台灣目前需從國外購買）。
</div>
</details>

<details>
<summary>Q: 預埋槽移動被固定物位置，會造成外力分布不均嗎？</summary>
<div class="answer-content">
在正常施作情況下，T 型螺栓會與槽道完整咬合，不會有外力分布不均的問題。PE 軟體會針對最不利位置進行檢核。
</div>
</details>

---

## <a name="基礎知識與設計原理"></a> 💡 基礎知識與設計原理

<details>
<summary>Q: 機械錨栓 vs. 化學錨栓的優缺點？</summary>
<div class="answer-content">
- <b>機械錨栓</b>：安裝後可立即受力、安裝流程簡單，但埋深固定且邊距要求較大。<br>
- <b>化學錨栓</b>：邊間距需求小、可自定義埋深、適用多種基材，但需要等待固化時間且清孔要求極嚴。
</div>
</details>

<details>
<summary>Q: 為什麼後置不可控制因素太多，大家還是常用？</summary>
<div class="answer-content">
預埋件在現場容易被灌漿覆蓋或發生位移。後置設計雖然清孔要求高，但位置精準，搭配 PE 軟體可解決徒手計算四個構件（底板、錨栓、焊接、基材）的複雜問題。
</div>
</details>

<details>
<summary>Q: 錨栓鋼板係數（Anchor Plate Factor）預設 1.5 可調整嗎？</summary>
<div class="answer-content">
根據 AISI S100，中心至邊緣距離不小於 1.5d。若設計違反此條文，軟體會報錯。但設計者可依工程判斷，手動輸入小於 1.5 的數值來降低要求。
</div>
</details>

---

## 🙋‍♂️ 找不到您的問題？
如果您在上方 FAQ 中沒有找到答案，請點擊下方按鈕提交您的問題。

[<img src="https://img.shields.io/badge/💬_點我提問-私密諮詢表單-red?style=for-the-badge&logo=googleforms&logoColor=white">](https://forms.office.com/e/PngwicwAn8)

<p align="center">
  <a href="#📌-快速跳轉索引"><b>[↑ 回到頂部]</b></a><br><br>
  <b>MOTW PROFIS Engineering 技術支援小組</b><br>
  最後更新日期：2026年4月
</p>

<hr>
<p align="center">
  <font color="#808080" size="2">
    © 2026 Hilti Engineering Support Team | 僅供技術交流參考<br>
    本頁面內容由 <b>MOTW 技術組</b> 維護與更新
  </font>
</p>
