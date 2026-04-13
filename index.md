---
layout: default
title: MOTW PROFIS Engineering FAQ
description: 喜立德工程軟體技術支援中心 - 常見問題與解決方案
---

<style>
  /* 1. 全域風格調整：優化閱讀質感 */
  body {
    color: #333;
    background-color: #ffffff;
    line-height: 1.8;
    font-family: "Helvetica Neue", Helvetica, Arial, "PingFang TC", "Microsoft JhengHei", sans-serif;
  }

  /* 2. 標題與重點色：使用喜立德紅 (#D21F3C) */
  /* 增加 !important 確保覆蓋主題預設樣式 */
  h1, h2, h3 {
    color: #D21F3C !important;
    border-bottom: 2px solid #D21F3C !important;
    padding-bottom: 12px !important;
    margin-top: 50px !important;
    font-weight: bold !important;
  }

  /* 3. 連結顏色與交互 */
  a {
    color: #D21F3C !important;
    text-decoration: none;
    transition: 0.3s;
  }
  a:hover {
    color: #A3182E !important;
    text-decoration: underline;
  }

  /* 4. 引用區塊 (Notes) 的優化 */
  blockquote {
    border-left: 5px solid #D21F3C !important;
    background-color: #fdf2f3;
    padding: 15px !important;
    color: #555;
  }

  /* 5. 隱藏預設頁尾標記 */
  .site-footer, footer {
    display: none !important;
  }

  /* 6. 圖片陰影與圓角 (增加網頁精緻感) */
  img {
    border-radius: 4px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    margin: 10px 0;
  }
</style>

# 🏗️ MOTW PROFIS ENGINEERING FAQ

歡迎使用 PROFIS Engineering 技術問答集。本頁面旨在協助工程師快速掌握軟體操作、法規更新及設計邏輯。

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

### Q: 軟體功能多久會更新一次？
**A:** SaaS 軟體每三到四週左右就會進行維修與更新。針對功能上，只要政府調整法規，軟體會即時更新相對應的功能條件。

---

### Q: PROFIS Engineering 模型輸出 DWG 流程？
**A:** 目前支援正向輸出（PE 轉 DWG），步驟如下：
1. 點擊 **「輸出」**：![步驟 1](./images/image%203.png)
2. 選擇 **「3D 模型輸出」**：![步驟 2](./images/image%204.png)
3. 執行 **「輸出」**：![步驟 3](./images/image%205.png)
4. 選擇檔案形式：![步驟 4](./images/image%206.png)
5. 匯出後使用 AutoCAD 開啟：![成果圖](./images/image%208.png)

---

### Q: 如何利用 Excel 輸入多重載重組合？
**A:** 1. 從結構軟體分析載重組合：![Excel 1](./images/image%2011.png)
2. 在 PE 中點選 **「導入荷載」** 並貼上：![Excel 2](./images/image%2012.png) ![Excel 3](./images/image%2013.png)
3. 調整軸向（拉力為正，壓力為負）：![Excel 4](./images/image%2014.png)
4. 調整單位後點擊應用（一次最多支援 1000 種組合）：![Excel 5](./images/image%2016.png)

---

### Q: 怎麼客製化報告表頭？
**A:** 進入右上角 **My report templates**，可依據專案需求設定公司 Logo 或資訊。
![表頭 1](./images/image%2020.png) ![表頭 2](./images/image%2021.png)

---

## <a name="法規與認證相關"></a> ⚖️ 法規與認證相關

### Q: 112 年版 RC 規範 17.5.3 錨栓強度折減因數在哪調整？
**A:** 軟體根據 ICC 報告自動定義折減係數（無法手動更改）。選擇 **狀態 A (有輔助鋼筋)** 或 **狀態 B (無輔助鋼筋)**，軟體會自動對應至規範分類。

---

### Q: 如何確認錨栓具備抗震能力 (C1/C2)？
**A:** 請查閱產品的 **ICC-ESR 或 EOTA 報告**。報告中會註明是否通過循環載荷試驗，並標示其在開裂混凝土中的抗震表現。

---

## <a name="結構設計與力學分析"></a> 📐 結構設計與力學分析

### Q: 平常都算剛性，為甚麼要算有限元素 (CBFEM)？
**A:** 實際狀況下底板會有應力集中。建議先用剛性做多重荷載計算，再針對最大外力使用有限元素分析。
> [!TIP]
> **CBFEM 模擬邏輯**：將混凝土視為受壓彈簧，錨栓視為受拉彈簧。
![模擬概念](./images/image%2017.png) ![參數設定](./images/image%2019.png)

---

### Q: 為什麼應力點會超過材料強度 2498 kgf/cm²？
**A:** 此為塑性設計結果。超過部分若在 5% 以內，微量塑變不影響整體設計安全。
![應力分析](./images/image%2010.png)

---

## <a name="預埋槽專區"></a> 🏗️ 預埋槽 (Anchor Channel) 專區

### Q: 槽式預埋件如何辨識耐震需求 (17.10)？
**A:** 軟體介面會根據選擇的荷載類型自動判別是否觸發抗震檢核。
![耐震辨識](./images/image%2033.png)

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
> **私密性說明：** 透過此表單提交的問題僅會傳送至技術後台，**其他使用者無法看見您的提問內容**，確保您的設計專案資訊安全。

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
