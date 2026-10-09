---
marp: true
theme: corporate
title: 人工智慧應用開發實務/Google Apps Script
paginate: true
transition: slide
---

<!-- _class: cover -->

# 人工智慧應用開發實務
## Google Apps Script

<hr>

許智超
<cchsu@mail.nsysu.edu.tw>

---

<!-- _class: section-page -->

<span class="num">01</span>

## 認識 Google Apps Script

<hr>

---

<!-- _class: stats -->

### 什麼是 Google Apps Script (GAS)？

<hr>

<div class="stat-wrap">
<div class="stat">

#### 雲端自動化與擴充
<hr>

無需安裝軟體或伺服器，直接在雲端環境執行。

</div>
<div class="stat hi">

#### 整合 Google 生態系
<hr>

輕鬆連結並操控 Sheets, Docs, Gmail, Drive 與 Calendar。

</div>
<div class="stat">

#### 免維護基礎設施
<hr>

託管於 Google 雲端，具高可用度與免費使用額度。

</div>
</div>

---

<!-- _class: stats -->

### 為什麼要使用 GAS？

<hr>

<div class="stat-wrap">
<div class="stat">

#### 自動化重複工作
<hr>

定時寄送報表郵件、自動彙整表單回覆，大幅省時。

</div>
<div class="stat hi">

#### 串接跨服務流程
<hr>

表單提交自動建日曆行程、試算表更新自動發通知。

</div>
<div class="stat">

#### Web APP / API
<hr>

將試算表直接轉化為網頁應用程式或資料 API 介面。

</div>
</div>

---

<!-- _class: cols -->

### Google Apps Script 的專案類型

<hr>

<div class="col-wrap">
<div class="col">

#### 容器綁定專案

- **附屬關係**：依附於特定 Google 文件、試算表或表單中。
- **開啟方式**：選單點選「擴充功能」 $\rightarrow$ 「Apps Script」。
- **主要用途**：擴充該文件的專屬功能或建立自訂選單。

</div>
<div class="col alt">

#### 獨立專案

- **附屬關係**：獨立存在於 Google 雲端硬碟的檔案。
- **開啟方式**：Google Drive 點選「新增」 $\rightarrow$ 「更多」 $\rightarrow$ 「Google Apps Script」。
- **主要用途**：串接多項服務或作為獨立運行的 Web 服務。

</div>
</div>

---

<!-- _class: section-page -->

<span class="num">02</span>

## GAS 基本操作與部署

<hr>

---

### 基本操作流程 (1/2)：開啟與介面導覽

<hr>

1. **開啟開發者介面**
   - [Apps Script](https://script.google.com/)
   - 在 Google 雲端硬碟 $\rightarrow$ 選擇存放的資料夾後「新增」 $\rightarrow$ 「Google Apps Script」
   - 在 Google 試算表中，透過選單選取「擴充功能」 $\rightarrow$ 「Apps Script」。
2. **認識編輯器介面**
   - **左側檔案區**：管理腳本檔案與 HTML/CSS 檔。
   - **中央編輯區**：撰寫腳本邏輯與介面。
   - **上方工具列**：選擇要執行的函數、點選「執行」或「偵錯」。
   - **下方執行日誌**：檢視執行過程與紀錄輸出。

---

### 基本操作流程 (2/2)：執行與初次授權

<hr>

1. **選擇函數與執行**
   - 在工具列選擇目標函數，點選「執行」按鈕。
2. **授權驗證（第一次執行時）**
   - 因腳本需要存取你的 Google 服務（如 Gmail 或 Drive），系統會彈出權限請求。
   - 點選「審查權限」 $\rightarrow$ 選擇 Google 帳號 $\rightarrow$ 允許存取。
3. **查看執行結果**
   - 執行完成後可在「執行日誌」區塊確認結果或排錯。

---

### 觸發條件 (Triggers) 設定

<hr>

> **自動執行的核心機制**
> 無需人工手動點選「執行」，讓腳本在特定條件滿足時自動啟動。

- **時間驅動 (Time-driven)**
  - 定時執行，如：每天早上 8 點、每小時一次、每週一執行。
- **事件驅動 (Event-driven)**
  - 隨使用者動作啟動，如：開啟檔案時 (onOpen)、編輯試算表時 (onEdit)、提交 Google 表單時 (onFormSubmit)。



---

<style scoped>
.col-wrap .col li, .col p { font-size: 0.7em; }
</style>

<!-- _class: cols -->

### GAS01：每日行程彙整 Email — 任務與要求

<hr>

<div class="col-wrap">
<div class="col">

#### 任務

**時間觸發器實作**

利用時間驅動觸發器，每天早上自動抓取當天的 Google 日曆行程，整理後寄到自己的 Gmail。

</div>
<div class="col alt">

#### 要求

- **讀取行程**：取得當天 Google 行事曆所有行程（標題、起訖時間、地點）。
- **整理內容**：依時間排序，組成易讀的信件內文；當天沒有行程時也要寄出提示。
- **寄送信件**：寄到自己的信箱，主旨包含日期。
- **設定觸發器**：建立「時間驅動 → 日計時器」，每天早上 7～8 點自動執行。

</div>
</div>

---

### 繳交方式

<hr>

> **錄影影片繳交**
> 錄製操作影片，上傳至雲端硬碟或 YouTube（不公開），繳交連結。

- **程式說明**：展示 Apps Script 程式碼，說明主要函式的流程。
- **執行示範**：手動執行一次，並展示日曆行程與收到的 Email 內容相符。
- **觸發器設定**：展示「觸發條件」頁面的設定，以及執行紀錄。
- **注意事項**：錄影前確認連結權限可供檢視，並遮蔽個人隱私資訊。

---

<style scoped>
.col-wrap .col li, .col p { font-size: 0.7em; }
</style>

<!-- _class: cols -->

### GAS02：表單自動收集與確認信

<hr>

<div class="col-wrap">
<div class="col">

#### 表單送出觸發器實作
自訂一個報名或問卷主題（如活動報名、課程意見調查），以 Google 表單收集資料，送出後自動整理並寄確認信給填寫者。

</div>

<div class="col alt">

- **建立表單**：至少 5 個題目，須含姓名、Email 與一題選擇題，並連結回覆試算表。
- **表單送出觸發器**：建立「表單送出時」觸發器，由事件物件取得填寫內容。
- **確認信**：以 `MailApp` 或 `GmailApp` 寄給填寫者，主旨含表單名稱，內文列出填寫內容與送出時間。
- **回寫狀態**：在試算表新增「確認信狀態」欄，寄出後標記「已寄出」與寄信時間。
- **資料檢核**：Email 格式不正確或必填欄位空白時，不寄信並標記「資料有誤」。

</div>
</div>

---

<style scoped>
.col-wrap .col li, .col p { font-size: 0.7em; }
</style>

<!-- _class: cols -->

### GAS03 學生成績自動處理

<hr>

<div class="col-wrap">
<div class="col">

#### 表單送出觸發器實作
自訂一個報名或問卷主題（如活動報名、課程意見調查），以 Google 表單收集資料，送出後自動整理並寄確認信給填寫者。

</div>

<div class="col alt">

- 學生資料
- 自動計算：一鍵自動計算總分、平均、排名（需計算加權）
- 不及格背景加顏色
- 側邊欄查詢學生成績
- 一鍵生成學生成績單

</div>
</div>



