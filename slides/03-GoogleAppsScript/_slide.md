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

### 部署為網絡應用程式 (Web App)

<hr>

> **將 GAS 變成線上網站或 API**

1. **點選部署**
   - 編輯器右上角點選「部署」 $\rightarrow$ 「新建部署」。
2. **設定類型與存取權限**
   - **類型**：選擇「網絡應用程式 (Web App)」。
   - **執行身分**：以「我」或存取使用者身分執行。
   - **存取權限**：設定「僅限自己」、「任何擁有 Google 帳戶的人」或「所有人 (含匿名)」。
3. **取得專屬 URL**
   - 完成後即可獲得一組網址，做為網頁入口或 API 端點。

---

<!-- _class: section-page -->

<span class="num">03</span>

## Gemini API

<hr>

---
<style scoped>
.col-wrap .col li, .col p { font-size: 0.7em; }
</style>

<!-- _class: cols -->

### Gemini API 簡介

<hr>
<div class="col-wrap">
<div class="col">

#### Gemini API

Gemini API 是 Google 提供的一套雲端程式介面，讓開發者與企業能將 Gemini 系列大語言模型的能力，直接整合進自己的軟體、網站、App 或後台系統中。


</div>
<div class="col alt">

#### 核心能力與特性

- 多模態處理：能同時接收並理解文字、圖片、音訊、影片、PDF 文件以及程式碼。
- 超長上下文視窗：支援最高百萬級 Token 的上下文長度。
- 結構化輸出：支援強制回傳符合特定 Schema 的 JSON 格式。
- 函式呼叫（Function Calling）：讓模型能主動調用外部 API、資料庫或自定義工具。
- 嵌入向量：提供語意向量生成，用於建立語意搜尋、文件問答系統（RAG）或推薦引擎。
</div>
</div>



---

### 申請 Gemini API Key

<hr>

**準備事項**
使用個人 Google 帳號登入；API Key 是存取 Gemini 的密碼，不能公開貼在網站、GitHub 或投影片中。

- **進入 Google AI Studio**
  - 開啟 [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)，並以 Google 帳號登入。
- **建立 API Key**
  - 點選「Create API key」，選擇既有 Google Cloud 專案，或建立新專案。
- **在 GAS 中安全設定**
  - 開啟「專案設定」→「指令碼屬性」，新增 `GEMINI_API_KEY`；程式以 `PropertiesService` 讀取，不要把金鑰直接寫進程式碼。

---

### GAS Gemini Chatbot

---

### Gemini File Search

<hr>

> **受管理的 RAG（檢索增強生成）工具**
> 讓 Gemini 先從自有文件找出相關內容，再依據內容回答；適合課程講義、規章、產品文件與內部知識庫。

1. **建立 File Search Store**
  - 建立專屬的文件儲存庫，作為可被語意搜尋的知識庫。
2. **上傳並建立索引**
  - 將 PDF、Word、試算表、文字或程式碼等檔案匯入；系統會自動分塊、產生嵌入向量並建立索引。
3. **提問時啟用 `file_search` 工具**
  - Gemini 將問題轉成嵌入向量，找出語意最相關的文件片段，再據以生成回答。
4. **取得可追溯的回答**
  - 回應可附帶 `file_citation` 引文；PDF 還可取得引用頁碼，方便核對來源。

**注意**：原始 `File` 物件會在 48 小時後刪除，但已匯入儲存庫的索引資料會保留至手動刪除；單一文件上限為 100 MB，目前不支援音訊與影片。

---

### GAS File Search and Chatbot

---

### GAS File Search Manager


---

### GAS Line Bot

---

<!-- _class: section-page -->

<span class="num">03</span>

## 資料庫基本觀念

<hr>

---

<!-- _class: stats -->

### 什麼是資料庫？

<hr>

<div class="stat-wrap">
<div class="stat">

#### 結構化儲存
<hr>

以固定的欄位格式儲存大量資料，避免雜亂無章。

</div>
<div class="stat hi">

#### 方便查詢與管理
<hr>

可依條件搜尋、排序、篩選，快速取得所需資料。

</div>
<div class="stat">

#### 支援程式化存取
<hr>

程式可自動讀寫資料，實現自動化與跨系統整合。

</div>
</div>

---

<!-- _class: quad -->

### 資料庫的基本結構

<hr>

<div class="quad-wrap">
<div class="item">

#### 資料表 Table

儲存同一類資料的集合

</div>
<div class="item">

#### 記錄 Record

資料表中的一列，代表一筆資料

</div>
<div class="item">

#### 欄位 Field

資料表中的一欄，代表一種屬性

</div>
<div class="item">

#### 主鍵 Primary Key

用來唯一識別每一筆記錄的欄位

</div>
</div>

---

<!-- _class: quad -->

### CRUD：資料庫的四大基本操作

<hr>

<div class="quad-wrap">
<div class="item">

#### Create 新增

寫入一筆新的記錄

</div>
<div class="item">

#### Read 讀取

查詢並取出既有的資料

</div>
<div class="item">

#### Update 更新

修改既有記錄的內容

</div>
<div class="item">

#### Delete 刪除

移除不再需要的記錄

</div>
</div>

---

<!-- _class: section-page -->

<span class="num">04</span>

## Google 試算表作為資料庫

<hr>

---

### 為什麼可以把試算表當資料庫？

<hr>

> **概念對應**
> 試算表的「工作表」就像資料表，「一列」就像一筆記錄，「一欄」就像一個欄位。

| 資料庫概念 | 試算表對應 |
| --- | --- |
| 資料表 (Table) | 工作表 (Sheet) |
| 記錄 (Record) | 一列資料 (Row) |
| 欄位 (Field) | 一欄資料 (Column) |
| 綱要 (Schema) | 標題列 (Header Row) |
| 主鍵 (Primary Key) | 具唯一值的欄位，如「編號」欄 |

---

### 用 GAS 存取試算表資料

<hr>

- **取得工作表**：`SpreadsheetApp.getActiveSpreadsheet().getSheetByName("名稱")`
- **讀取整批資料**：`sheet.getDataRange().getValues()`，回傳二維陣列
- **新增一列**：`sheet.appendRow([欄位1, 欄位2, ...])`
- **修改單一儲存格**：`sheet.getRange(列, 欄).setValue(新值)`
- **刪除整列**：`sheet.deleteRow(列號)`

---

<!-- _class: cols -->

### CRUD 對應範例：以「學生名冊」為例

<hr>

<div class="col-wrap">
<div class="col">

#### Create／Read

```javascript
function addStudent(id, name, score) {
  const sheet = SpreadsheetApp
    .getActiveSpreadsheet()
    .getSheetByName("學生名冊");
  sheet.appendRow([id, name, score]);
}

function getAllStudents() {
  const sheet = SpreadsheetApp
    .getActiveSpreadsheet()
    .getSheetByName("學生名冊");
  return sheet.getDataRange().getValues();
}
```

</div>
<div class="col alt">

#### Update／Delete

```javascript
function updateScore(row, newScore) {
  const sheet = SpreadsheetApp
    .getActiveSpreadsheet()
    .getSheetByName("學生名冊");
  sheet.getRange(row, 3).setValue(newScore);
}

function deleteStudent(row) {
  const sheet = SpreadsheetApp
    .getActiveSpreadsheet()
    .getSheetByName("學生名冊");
  sheet.deleteRow(row);
}
```

</div>
</div>

---

### 概念練習：設計一個試算表資料庫

<hr>

> **練習目標**
> 以「學生名冊」試算表為資料庫，練習資料庫的設計與 CRUD 操作。

1. **設計綱要**：建立標題列，例如「編號、姓名、成績」。
2. **新增資料**：撰寫函式將一筆新學生資料寫入試算表。
3. **查詢資料**：撰寫函式依「編號」找出對應的學生列。
4. **更新與刪除**：撰寫函式修改指定學生的成績，或刪除離校學生的記錄。

---

### GAS 名片自動 OCR APP

---

<!-- _class: section-page -->

<span class="num">05</span>

## 資料庫正規化

<hr>

---

<!-- _class: stats -->

### 為什麼需要正規化？

<hr>

<div class="stat-wrap">
<div class="stat">

#### 減少資料重複
<hr>

同一份資訊只存一次，不再散落在多筆記錄裡。

</div>
<div class="stat hi">

#### 避免更新異常
<hr>

改一筆資料就好，不必到處尋找同步修改。

</div>
<div class="stat">

#### 提升資料一致性
<hr>

拆分後的資料表彼此獨立，降低錯誤與矛盾。

</div>
</div>

---

### 範例：未正規化的訂單資料表

<hr>

| 訂單編號 | 客戶姓名 | 客戶電話 | 產品名稱 | 單價 | 數量 |
| --- | --- | --- | --- | --- | --- |
| 1001 | 王小明 | 0912-345-678 | 筆記本 | 50 | 3 |
| 1002 | 王小明 | 0912-345-678 | 原子筆 | 10 | 5 |
| 1003 | 陳美麗 | 0933-222-111 | 筆記本 | 50 | 2 |

> **潛藏問題**
> 客戶姓名、電話與產品單價一再重複；修改客戶電話要改好幾列，容易漏改或改錯。

---

### 第一正規化 (1NF)：欄位值須為單一值

<hr>

> **規則**
> 每個欄位只能存放單一數值，不可以塞入重複群組或清單。

**違反範例**：「產品名稱」欄位存成 `筆記本, 原子筆`，一格塞兩項產品。

**修正做法**：拆成兩列，一列只對應一項產品：

| 訂單編號 | 產品名稱 | 數量 |
| --- | --- | --- |
| 1001 | 筆記本 | 3 |
| 1001 | 原子筆 | 2 |

---

### 第二正規化 (2NF)：消除部分相依

<hr>

> **規則**
> 非主鍵欄位必須完全相依於「整個」主鍵，不能只相依於主鍵的一部分。

**問題**：若主鍵是複合鍵 (訂單編號, 產品名稱)，「客戶姓名」「客戶電話」其實只跟「訂單編號」有關，跟「產品名稱」無關 → 只依賴部分主鍵。

**修正做法**：把客戶資訊拆到獨立的「訂單」表，訂單明細只留數量等真正依賴兩個鍵的資料。

---

### 第三正規化 (3NF)：消除遞移相依

<hr>

> **規則**
> 非主鍵欄位不能相依於另一個「非主鍵」欄位。

**問題**：「單價」其實是相依於「產品名稱」，而不是直接相依於訂單的主鍵 → 產品名稱 $\rightarrow$ 單價，屬於遞移相依。

**修正做法**：把產品名稱與單價拆到獨立的「產品」表，訂單明細只記錄「產品編號」。

---

<!-- _class: quad -->

### 正規化後的資料表設計

<hr>

<div class="quad-wrap">
<div class="item">

#### 客戶 Customer

客戶編號、姓名、電話

</div>
<div class="item">

#### 產品 Product

產品編號、名稱、單價

</div>
<div class="item">

#### 訂單 Order

訂單編號、客戶編號、訂單日期

</div>
<div class="item">

#### 訂單明細 OrderDetail

訂單編號、產品編號、數量

</div>
</div>

---

<!-- _class: section-page -->

<span class="num">06</span>

## 用 Google 試算表做簡易正規化

<hr>

---

### 試算表正規化的做法

<hr>

- 把一張大表拆成多個**工作表 (Sheet)**，每個工作表對應一個正規化後的資料表。
- 用「編號」欄位作為工作表之間的關聯鍵，概念上就像資料庫的**外來鍵**。
- 查詢時用 `VLOOKUP` 或 `QUERY` 函式跨工作表取值，模擬資料庫的 JOIN。

---

### 範例：拆分後的四個工作表

<hr>

| 工作表 | 欄位 |
| --- | --- |
| 客戶 | 客戶編號, 姓名, 電話 |
| 產品 | 產品編號, 名稱, 單價 |
| 訂單 | 訂單編號, 客戶編號, 訂單日期 |
| 訂單明細 | 訂單編號, 產品編號, 數量 |

---

### 用 VLOOKUP 串連跨工作表的資料

<hr>

在「訂單明細」工作表中，依「訂單編號」查出對應的客戶姓名：

```text
=VLOOKUP(VLOOKUP(A2, 訂單!A:B, 2, FALSE), 客戶!A:B, 2, FALSE)
```

- 先用內層 `VLOOKUP` 依訂單編號到「訂單」表查出客戶編號。
- 再用外層 `VLOOKUP` 依客戶編號到「客戶」表查出姓名。
- 同樣的方式，也可以依「產品編號」到「產品」表查出單價。

---

### 概念練習：正規化「訂單資料表」

<hr>

> **練習目標**
> 把一張未正規化的訂單大表，改造成正規化的試算表資料庫。

1. **複製原始資料**：把未正規化的訂單大表放進一份新的 Google 試算表。
2. **拆分工作表**：依 1NF／2NF／3NF 的原則，拆成「客戶」「產品」「訂單」「訂單明細」四個工作表。
3. **建立關聯**：在「訂單明細」用 `VLOOKUP` 查出對應的客戶姓名與產品單價。
4. **驗證效果**：試著修改一筆客戶電話，確認只需要改「客戶」工作表裡的一格就好。


---

<!-- _class: closing -->

# 感謝聆聽

<hr>

如有任何問題，歡迎提問

許智超 <cchsu@mail.nsysu.edu.tw>
