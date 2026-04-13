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
    list-style: none; /* 隱藏預設箭頭 */
    display: flex;
    align-items: center;
  }

  /* 自定義前置箭頭 */
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

  /* 4. 內容與圖片樣式 */
  .answer-content {
    padding: 10px 5px;
    color: #555;
  }

  img {
    border-radius: 6px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    margin-top: 15px;
    max-width: 100%;
    display: block;
  }

  /* 5. 其他元件 */
  a { color: #D21F3C; text-decoration: none; }
  a:hover { text-decoration: underline; }
  .site-footer, footer { display: none !important; }
</style>

# 🏗️ MOTW PROFIS ENGINEERING FAQ

歡迎使用 PROFIS Engineering 技術問答集。點擊下方問題可展開詳細解答與操作截圖。

> [!NOTE]
> **法規更新提醒**：內政部「建築物混凝土結構設計規範」已於 113 年 1 月 1 日生效。

---

## 📌 快速跳轉索引
* [🛠️ 軟體操作與功能設定](#軟體操作與功能設定)
* [⚖️ 法規與認證相關](#法規與認證相關)
* [📐 結構設計與力學分析](#結構設計與力學分析)
* [🏗️ 預埋槽 (Anchor Channel) 專區](#預埋槽專區)
* [📚 參考法規下載](#參考法規下載)

---

## <a name="軟體操作與功能設定"></a> 🛠️ 軟體操作與功能設定

<details>
<summary>Q: 軟體功能多久會更新一次？</summary>
<div class="answer-content">
SaaS 軟體每三到四週左右就會進行維修與更新。針對功能上，只要政府調整法規，軟體會即時更新相對應的功能條件。
</div>
</details>

<details>
<summary>Q: PROFIS Engineering 模型輸出 DWG 流程？</summary>
<div class="answer-content">
目前支援正向輸出（PE 轉 DWG），步驟如下：<br>
1. 點擊 「輸出」<br>
![步驟 1](./images/image%203.png)<br>
2. 選擇 「3D 模型輸出」<br>
![步驟 2](./images/image%204.png)<br>
3. 執行 「輸出」<br>
![步驟 3](./images/image%205.png)<br>
4. 選擇檔案形式<br>
![步驟 4](./images/image%206.png)<br>
5. 使用 AutoCAD 開啟成果<br>
![成果圖](./images/image%208.png)
</div>
</details>

<details>
<summary>Q: 如何利用 Excel 輸入多重載重組合？</summary>
<div class="answer-content">
1. 從結構軟體分析載重組合：<br>
![Excel 1](./images/image%2011.png)<br>
2. 在 PE 中點選 「導入荷載」 並貼上：<br>
![Excel 2](./images/image%2012.png) ![Excel 3](./images/image%2013.png)<br>
3. 調整軸向與單位（一次最多支援 1000 種組合）：<br>
![Excel 5](./images/image%2016.png)
</div>
</details>

<details>
<summary>Q: 怎麼客製化報告表頭？</summary>
<div class="answer-content">
進入右上角 My report templates，可依據專案需求設定公司 Logo 或資訊。<br>
![表頭 1](./images/image%2020.png) ![表頭 2](./images/image%2021.png)
</div>
</details>

---

## <a name="法規與認證相關"></a> ⚖️ 法規與認證相關

<details>
<summary>Q: 112 年版 RC 規範 17.5.3 錨栓強度折減因數在哪調整？</summary>
<div class="answer-content">
軟體根據 ICC 報告自動定義折減係數（無法手動更改）。選擇 <b>狀態 A (有輔助鋼筋)</b> 或 <b>狀態 B (無輔助鋼筋)</b>，軟體會自動對應至規範分類。
</div>
</details>

<details>
<summary>Q: 如何確認錨栓具備抗震能力 (C1/C2)？</summary>
<div class="answer-content">
請查閱產品的 <b>ICC-ESR 或 EOTA 報告</b>。報告中會註明是否通過循環載荷試驗，並標示其在開裂混凝土中的抗震表現。
</div>
</details>

---

## <a name="結構設計與力學分析"></a> 📐 結構設計與力學分析

<details>
<summary>Q: 平常都算剛性，為甚麼要算有限元素 (CBFEM)？</summary>
<div class="answer-content">
實際狀況下底板會有應力集中。建議先用剛性做多重荷載計算，再針對最大外力使用有限元素分析。<br>
<b>CBFEM 模擬邏輯：</b> 將混凝土視為受壓彈簧，錨栓視為受拉彈簧。<br>
![模擬概念](./images/image%2017.png) ![參數設定](./images/image%2019.png)
</div>
</details>

<details>
<summary>Q: 為什麼應力點會超過材料強度 2498 kgf/cm²？</summary>
<div class="answer-content">
此為塑性設計結果。超過部分若在 5% 以內，微量塑變不影響整體設計安全。<br>
![應力分析](./images/image%2010.png)
</div>
</details>

---

## <a name="預埋槽專區"></a> 🏗️ 預埋槽 (Anchor Channel) 專區

<details>
<summary>Q: 預埋槽 (HAC) 除了幕牆 (Façade) 還有哪些應用？</summary>
<div class="answer-content">
1. <b>電梯設備</b>：導軌與支撐固定。<br>
2. <b>管線安裝</b>：水管、通風管、電纜橋架。<br>
3. <b>混凝土結構</b>：樓板或梁柱預留安裝點。<br>
4. <b>設備固定</b>：大型機組或機械支架。
</div>
</details>

<details>
<summary>Q: 槽式預埋件如何辨識耐震需求 (17.10)？</summary>
<div class="answer-content">
軟體介面會根據選擇的荷載類型自動判別是否觸發抗震檢核。<br>
![耐震辨識](./images/image%2033.png)
</div>
</details>

---

## <a name="參考法規下載"></a> 📚 參考法規下載

| 法規名稱 | 國家/地區 | 檔案連結 |
| :--- | :--- | :--- |
| **建築物混凝土結構設計規範 (土木 401)** | 🇹🇼 台灣 | [點此下載](./%E5%9C%9F%E6%9C%A8401%20112.pdf) |
| **ACI 318-19 錨固規範** | 🇺🇸 美國 | [點此下載](./ACI318%2019.pdf) |
| **ETAG-001 技術規範** | 🇪🇺 歐洲 | [點此下載](./ETAG-001-annex-c.pdf) |

---

## 🙋‍♂️ 找不到您的問題？
如果您在上方 FAQ 中沒有找到答案，請點擊下方按鈕提交您的問題。

[<img src="https://img.shields.io/badge/💬_點我提問-私密諮詢表單-red?style=for-the-badge&logo=googleforms&logoColor=white">](你的表單連結)

> [!TIP]
> **私密性說明：** 您的提問將以私密方式傳送，僅內部技術人員可見，確保設計專案安全。

---

<p align="center">
  <a href="#📌-快速跳轉索引"><b>[↑ 回到頂部]</b></a><br><br>
  <b>MOTW PROFIS Engineering 技術支援小組</b><br>
  最後更新日期：2026年4月
</p>

<hr>
<p align="center">
  <font color="#808080" size="2">
    © 2026 Hilti Engineering Support Team | 僅供技術交流參考，設計請依最終報告為準<br>
    本頁面內容由 <b>MOTW 技術組</b> 維護與更新
  </font>
</p>
