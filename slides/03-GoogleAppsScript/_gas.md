# GAS 精選 12 單元教學範例

整理自 [temp.md](temp.md) 列出的 12 個想完成單元，對照 [GAS-整合版.md](GAS-整合版.md) 的週次，並補上每單元的學習重點、核心技術與可直接參考的程式範例。

---

## 總覽表

| # | 單元 | 學習重點 | 核心技術 | 對應整合版週次 |
|---|---|---|---|---|
| 1 | 學生資料批次整理、成績統計與自動標示 | 陣列/迴圈批次處理、排序、條件格式自動標示 | `SpreadsheetApp`、`Range`、Array | 第 1 週 |
| 2 | 表單自動收集與確認信 | `onFormSubmit` 觸發器、動態取值、自動寄信 | `FormApp`/`onFormSubmit`、`GmailApp` | 第 2 週 |
| 3 | 作業繳交與逾期通知系統 | 時間驅動觸發器、日期比對邏輯 | Time-driven Trigger、`Date` | 第 3 週 |
| 4 | 個人化文件／證書／PDF 產生器 | 範本文字取代（Template Merge）、批次匯出 PDF | `DocumentApp`、`DriveApp` | 第 4 週 |
| 5 | AI 自動分類客服訊息 | 分類 Prompt 設計、回應解析、標記寫回 | `UrlFetchApp`、Gemini API | 第 7 週（延伸） |
| 6 | 側邊欄助理 | `HtmlService` 前端、`google.script.run` 異步溝通 | `HtmlService`、Sidebar UI | 第 6 週 |
| 7 | 簡易聊天機器人（Gemini API） | Web App 對話端點、串接 Gemini 生成回覆 | `doGet`/`doPost`、Gemini API | 第 7～8 週（延伸） |
| 8 | 多模態應用：收據辨識 | 圖片轉 Base64、Vision Prompt、結構化輸出解析 | `DriveApp`、Gemini Vision | 第 11 週（部分） |
| 9 | 建立 GAS Web App | `doGet`/`doPost`、HTML Service、部署設定 | Web App 部署 | 第 8 週 |
| 10 | 建立 REST-like API | `ContentService`、CRUD、Sheets 當資料庫 | `ContentService`、CORS | 第 9 週 |
| 11 | LINE 整合 AI 助理 | Webhook 接收、簽章驗證、回覆訊息 API | LINE Messaging API、`doPost` | 第 10 週 |
| 12 | RAG 知識庫問答機器人（Gemini File Search） | File Search Store 建立、文件索引、Grounding 問答 | Gemini File Search API | 第 12 週 |

---

## 單元範例

### 1. 學生資料批次整理、成績統計與自動標示

```javascript
function processGrades() {
  const sheet = SpreadsheetApp.getActiveSheet();
  const data = sheet.getRange(2, 1, sheet.getLastRow() - 1, 4).getValues(); // 姓名, 國文, 數學, 英文

  const result = data.map(row => {
    const [name, ...scores] = row;
    const avg = scores.reduce((a, b) => a + b, 0) / scores.length;
    return [name, avg.toFixed(1), avg < 60 ? '不及格' : '及格'];
  });

  result.sort((a, b) => b[1] - a[1]); // 依平均分數高到低排序

  sheet.getRange(2, 5, result.length, 3).setValues(result);

  result.forEach((row, i) => {
    if (row[2] === '不及格') {
      sheet.getRange(i + 2, 5, 1, 3).setBackground('#f4cccc');
    }
  });
}
```

### 2. 表單自動收集與確認信

```javascript
function onFormSubmit(e) {
  const responses = e.namedValues; // { '姓名': ['王小明'], 'Email': ['xxx@gmail.com'] }
  const name = responses['姓名'][0];
  const email = responses['Email'][0];

  GmailApp.sendEmail(email, '報名確認',
    `${name} 您好，您已成功完成報名，我們會盡快與您聯繫。`);

  SpreadsheetApp.getActiveSheet().appendRow([new Date(), name, email, '已確認']);
}
```
> 需在 Apps Script 編輯器的「觸發條件」中，將 `onFormSubmit` 綁定到目標表單的送出事件。

### 3. 作業繳交與逾期通知系統

```javascript
function checkOverdueSubmissions() {
  const sheet = SpreadsheetApp.getActiveSheet();
  const data = sheet.getDataRange().getValues(); // 姓名, Email, 截止日, 繳交狀態
  const today = new Date();

  data.forEach((row, i) => {
    if (i === 0) return; // 略過標題列
    const [name, email, dueDate, status] = row;
    if (status !== '已繳交' && new Date(dueDate) < today) {
      GmailApp.sendEmail(email, '作業逾期提醒', `${name} 您好，您的作業已逾期，請盡快補交。`);
      sheet.getRange(i + 1, 4).setValue('已通知');
    }
  });
}
```
> 用「Triggers → Time-driven」設定每日固定時間（如早上 8 點）自動執行。

### 4. 個人化文件／證書／PDF 產生器

```javascript
function generateCertificates() {
  const templateId = 'YOUR_TEMPLATE_DOC_ID';
  const folder = DriveApp.getFolderById('YOUR_OUTPUT_FOLDER_ID');
  const data = SpreadsheetApp.getActiveSheet().getDataRange().getValues();

  data.forEach((row, i) => {
    if (i === 0) return;
    const [name, course, score] = row;
    const copy = DriveApp.getFileById(templateId).makeCopy(`證書_${name}`, folder);
    const doc = DocumentApp.openById(copy.getId());
    const body = doc.getBody();

    body.replaceText('{{姓名}}', name);
    body.replaceText('{{課程}}', course);
    body.replaceText('{{成績}}', score);
    doc.saveAndClose();

    const pdf = DriveApp.getFileById(copy.getId()).getAs('application/pdf');
    folder.createFile(pdf).setName(`證書_${name}.pdf`);
  });
}
```
> 範本文件內先寫好 `{{姓名}}`、`{{課程}}`、`{{成績}}` 佔位符。

### 5. AI 自動分類客服訊息

```javascript
function classifyMessage(message) {
  const prompt = `請將以下客服訊息分類為「客訴」「詢問」或「讚美」其中之一，只回傳分類名稱：\n\n${message}`;
  const category = callGemini(prompt).trim();

  SpreadsheetApp.getActiveSheet().appendRow([new Date(), message, category]);
  return category;
}

function callGemini(prompt) {
  const apiKey = PropertiesService.getScriptProperties().getProperty('GEMINI_API_KEY');
  const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=${apiKey}`;
  const payload = { contents: [{ parts: [{ text: prompt }] }] };
  const res = UrlFetchApp.fetch(url, {
    method: 'post', contentType: 'application/json',
    payload: JSON.stringify(payload), muteHttpExceptions: true
  });
  return JSON.parse(res.getContentText()).candidates[0].content.parts[0].text;
}
```
> `callGemini()` 是共用函式，後面第 7、8、11、12 題都會重複使用同樣的呼叫模式。

### 6. 側邊欄助理

```javascript
// Code.gs
function onOpen() {
  SpreadsheetApp.getUi().createMenu('AI 助理')
    .addItem('開啟側邊欄', 'showSidebar')
    .addToUi();
}

function showSidebar() {
  const html = HtmlService.createHtmlOutputFromFile('Sidebar').setTitle('AI 助理');
  SpreadsheetApp.getUi().showSidebar(html);
}

function analyzeSelection() {
  const values = SpreadsheetApp.getActiveRange().getValues().flat().join('\n');
  return callGemini(`請對以下資料提出清洗建議：\n${values}`);
}
```

```html
<!-- Sidebar.html -->
<button onclick="run()">分析選取範圍</button>
<div id="result"></div>
<script>
function run() {
  google.script.run.withSuccessHandler(res => {
    document.getElementById('result').innerText = res;
  }).analyzeSelection();
}
</script>
```

### 7. 簡易聊天機器人（Gemini API）

```javascript
// Code.gs
function doGet() {
  return HtmlService.createHtmlOutputFromFile('Chat');
}

function doPost(e) {
  const userMessage = JSON.parse(e.postData.contents).message;
  const reply = callGemini(`你是課程助教，請簡潔回答學生問題：\n${userMessage}`);
  return ContentService.createTextOutput(JSON.stringify({ reply }))
    .setMimeType(ContentService.MimeType.JSON);
}
```

```html
<!-- Chat.html -->
<input id="msg" placeholder="輸入問題"><button onclick="send()">送出</button>
<div id="reply"></div>
<script>
function send() {
  fetch(window.location.href, {
    method: 'POST',
    body: JSON.stringify({ message: document.getElementById('msg').value })
  }).then(r => r.json()).then(d => {
    document.getElementById('reply').innerText = d.reply;
  });
}
</script>
```

### 8. 多模態應用：收據辨識

```javascript
function extractReceiptInfo(fileId) {
  const file = DriveApp.getFileById(fileId);
  const base64 = Utilities.base64Encode(file.getBlob().getBytes());

  const apiKey = PropertiesService.getScriptProperties().getProperty('GEMINI_API_KEY');
  const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=${apiKey}`;
  const payload = {
    contents: [{
      parts: [
        { text: '請從這張收據圖片中提取店名、日期、金額、品項，以 JSON 格式回傳。' },
        { inline_data: { mime_type: file.getMimeType(), data: base64 } }
      ]
    }]
  };

  const res = UrlFetchApp.fetch(url, {
    method: 'post', contentType: 'application/json',
    payload: JSON.stringify(payload), muteHttpExceptions: true
  });
  const text = JSON.parse(res.getContentText()).candidates[0].content.parts[0].text;
  const info = JSON.parse(text.replace(/```json|```/g, '').trim());

  SpreadsheetApp.getActiveSheet()
    .appendRow([info.店名, info.日期, info.金額, JSON.stringify(info.品項)]);
}
```
> 可搭配 Drive 資料夾監聽（`DriveApp.getFolderById(...).getFiles()` + 觸發器）自動處理新上傳的收據。

### 9. 建立 GAS Web App

```javascript
function doGet(e) {
  return HtmlService.createHtmlOutputFromFile('Index').setTitle('我的 Web App');
}

function doPost(e) {
  const data = JSON.parse(e.postData.contents);
  SpreadsheetApp.getActiveSheet().appendRow([new Date(), data.name, data.message]);
  return ContentService.createTextOutput(JSON.stringify({ status: 'ok' }))
    .setMimeType(ContentService.MimeType.JSON);
}
```
> 部署方式：右上角「部署 → 新增部署作業 → 網頁應用程式」，存取權限設為「所有人」即可取得可公開訪問的網址。

### 10. 建立 REST-like API

```javascript
function doGet(e) {
  const action = e.parameter.action;
  const sheet = SpreadsheetApp.getActiveSheet();

  if (action === 'list') {
    return jsonResponse(sheet.getDataRange().getValues());
  }
  if (action === 'get') {
    const id = e.parameter.id;
    const row = sheet.getDataRange().getValues().find(r => r[0] === id);
    return jsonResponse(row || {});
  }
  return jsonResponse({ error: 'unknown action' });
}

function doPost(e) {
  const body = JSON.parse(e.postData.contents);
  SpreadsheetApp.getActiveSheet().appendRow([body.id, body.name, body.email]);
  return jsonResponse({ status: 'created' });
}

function jsonResponse(obj) {
  return ContentService.createTextOutput(JSON.stringify(obj))
    .setMimeType(ContentService.MimeType.JSON);
}
```
> 呼叫方式：`GET /exec?action=list`、`GET /exec?action=get&id=S001`、`POST /exec`（帶 JSON body）。

### 11. LINE 整合 AI 助理

```javascript
function doPost(e) {
  const json = JSON.parse(e.postData.contents);
  const event = json.events[0];
  const userMessage = event.message.text;
  const replyToken = event.replyToken;

  const reply = callGemini(`你是課程助教，請簡潔回答：\n${userMessage}`);

  const token = PropertiesService.getScriptProperties().getProperty('LINE_CHANNEL_TOKEN');
  UrlFetchApp.fetch('https://api.line.me/v2/bot/message/reply', {
    method: 'post',
    headers: { Authorization: `Bearer ${token}` },
    contentType: 'application/json',
    payload: JSON.stringify({
      replyToken,
      messages: [{ type: 'text', text: reply }]
    })
  });

  return ContentService.createTextOutput('OK');
}
```
> 將此 Web App 網址填入 LINE Developers 後台的 Webhook URL；`callGemini()` 同第 5 題共用函式。

### 12. RAG 知識庫問答機器人（Gemini File Search）

```javascript
// 1. 建立 File Search Store（僅需執行一次）
function setupFileSearchStore() {
  const apiKey = PropertiesService.getScriptProperties().getProperty('GEMINI_API_KEY');

  const res = UrlFetchApp.fetch(
    `https://generativelanguage.googleapis.com/v1beta/fileSearchStores?key=${apiKey}`,
    {
      method: 'post', contentType: 'application/json',
      payload: JSON.stringify({ displayName: '課程知識庫' })
    }
  );
  const storeName = JSON.parse(res.getContentText()).name;
  PropertiesService.getScriptProperties().setProperty('FILE_SEARCH_STORE', storeName);
  // 接著需將 Drive 中的課程文件上傳到此 Store（Files API 上傳 → 匯入 File Search Store）
}

// 2. 提問時帶入 file_search 工具，由 Gemini 自動檢索並附引用回答
function askKnowledgeBase(question) {
  const apiKey = PropertiesService.getScriptProperties().getProperty('GEMINI_API_KEY');
  const storeName = PropertiesService.getScriptProperties().getProperty('FILE_SEARCH_STORE');

  const payload = {
    contents: [{ parts: [{ text: question }] }],
    tools: [{ file_search: { file_search_store_names: [storeName] } }]
  };

  const res = UrlFetchApp.fetch(
    `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=${apiKey}`,
    { method: 'post', contentType: 'application/json', payload: JSON.stringify(payload) }
  );
  return JSON.parse(res.getContentText()).candidates[0].content.parts[0].text;
}
```
> 與手動 Embedding + Cosine Similarity 相比，File Search Store 由 Google 端自動處理分塊與索引，不需自己維護向量資料。
