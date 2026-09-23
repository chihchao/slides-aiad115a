---
marp: true
theme: gaia-cust
title: 人工智慧應用開發實務 / Static Web Page
size: 16:9
paginate: true
transition: slide
---

<!-- _class: cover -->
<!-- _paginate: false -->
<!-- _footer: "" -->

# 人工智慧應用開發實務
## Static Web Page

許智超

<cchsu@mail.nsysu.edu.tw>

---

<!-- _class: section-page -->

## Web 基礎概念

---

<!-- _class: lead -->

### 開啟一個網頁時，發生了什麼事？

---
<style scoped>
section p { text-align: center; }
</style>

### Client-Server 架構

<hr>

- **Client（用戶端）**：瀏覽器，負責發出請求、顯示畫面
- **Server（伺服器）**：負責接收請求、處理邏輯、回傳資料

![w:900](assets/client-server-architecture.svg)

---

### HTTP 協定

<hr>

HyperText Transfer Protocol，瀏覽器與伺服器溝通的共同語言

- **Request（請求）**：方法（GET / POST...）、網址、附帶資料
- **Response（回應）**：狀態碼（200 成功 / 404 找不到 / 500 伺服器錯誤）、回傳內容

---

### 網址（URL）的組成

<hr>

```text
https://www.nsysu.edu.tw/news?id=123
  │        │                │    │
協定     網域(Domain)        路徑  參數(Query)
```

- 協定：如何連線（`https`）
- 網域：伺服器在哪裡（由 DNS 轉換成 IP）
- 路徑／參數：要哪一份資料、附帶什麼條件

---

### 網頁三要素

<hr>

- **HTML**：結構（骨架）— 網頁有哪些內容
- **CSS**：樣式（外觀）— 網頁長什麼樣子
- **JavaScript**：行為（互動）— 網頁能做什麼

---

<style scoped>
section p { text-align: center; font-size: 0.9em; }
</style>

### 瀏覽器如何呈現網頁？

![w:1100](assets/browser-rendering-flowchart.svg)

---

<style scoped>
section p { text-align: center; }
</style>

### 靜態網頁 vs 動態網頁

- **靜態網頁**：內容固定，伺服器只是把現成檔案原封不動送出
- **動態網頁**：內容依請求即時運算、組裝、更新

![w:700](assets/frontend-backend-1.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 靜態網頁 vs 動態網頁

- **靜態網頁**：內容固定，伺服器只是把現成檔案原封不動送出
- **動態網頁**：內容依請求即時運算、組裝、更新

![w:700](assets/frontend-backend-2.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 前端 vs 後端

- **前端（Front-end）**：使用者看得到、互動的部分，程式碼在瀏覽器端執行
- **後端（Back-end）**：使用者看不到的部分，處理邏輯、資料庫、安全驗證等，程式碼在伺服器端執行

![w:700](assets/frontend-backend-3.png)

---

<!-- _class: lead -->

## 靜態網頁是什麼？

---

<!-- _class: "cols" -->

### 靜態網頁 vs 動態網頁

<hr>

<div class="col-wrap">
<div class="col alt">

**靜態網頁**

- 內容寫死在檔案裡
- 不需要後端伺服器運算
- 檔案直接丟給瀏覽器
- 範例：個人作品集、說明頁

</div>
<div class="col alt">

**動態網頁**

- 內容來自資料庫或 API
- 需要後端語言（PHP、Python…）
- 每次請求都重新產生頁面
- 範例：Facebook、Gmail

</div>
</div>

Notes: 靜態網頁雖然「靜態」，但 JavaScript 仍可讓它有豐富的互動效果！

---

<!-- _class: "cols3" -->

### 網頁三要素：HTML, CSS, Javascript

<hr>


<div class="col-wrap">
<div>

**HTML** / 結構與內容

- 告訴瀏覽器「有什麼內容」
- 標題、段落、圖片、按鈕…
- 像房子的**骨架與牆壁**

</div>
<div>

**CSS** / 樣式與外觀

- 告訴瀏覽器「長什麼樣子」
- 顏色、字型、排版、動畫…
- 像房子的**裝潢與油漆**

</div>
<div>

**JavaScript** / 行為與互動

- 告訴瀏覽器「做什麼事」
- 點擊、計算、更新畫面…
- 像房子的**電路與機關**

</div>
</div>

Notes: 三者分工合作——HTML 定義內容，CSS 負責呈現，JS 處理邏輯。初學時三個都寫在同一個 .html 檔最方便。

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 網頁三要素：HTML, CSS, Javascript

<hr>

```html
<!DOCTYPE html>
<html lang="zh-TW">
  <head>
    <meta charset="UTF-8">
    <title>我的網頁</title>
    <style>
      /* CSS 寫在這裡 */
    </style>
  </head>
  <body>
    <!-- HTML 結構寫在這裡 -->

    <script>
      // JavaScript 寫在這裡
    </script>
  </body>
</html>
```

Notes: 實際專案會拆成三個獨立檔案，但初學階段單一檔案更容易上手、方便對照學習。

---

<!-- _class: "section-page" -->

## HTML (HyperText Markup Language)

---

<!-- _class: "cols" -->

### HTML 的由來與發展

<hr>

<div class="col-wrap">
<div class="col alt">

#### 起源

- HyperText Markup Language — 超文字標記語言

- 1989 年，Tim Berners-Lee 在 CERN 提出，語法靈感來自 SGML（文件標記語言）
- 目的：讓科學家能透過網路分享文件

</div>
<div class="col alt">

#### 重要版本里程碑

| 年份 | 版本 |
|------|------|
| 1995 | HTML 2.0（首個正式標準） |
| 1997 | HTML 3.2 / 4.0 |
| 2000 | XHTML 1.0（嚴格語法） |
| 2014 | **HTML5**（現行標準） |

</div>
</div>

Notes: HTML5 由 WHATWG 與 W3C 共同維護，引入了 video、canvas、語意標籤等現代功能。

---

<!-- _class: "cols" -->

<style scoped>
pre code { font-size: 0.6em; line-height: 1.15; }
</style>

### HTML 基本結構

<div class="col-wrap">
<div class="col alt">


```html
<!DOCTYPE html>
<html lang="zh-TW">
  <head>
    <meta charset="UTF-8" />
    <title>我的第一個網頁</title>
  </head>
  <body>
    <h1>哈囉，世界！</h1>
    <p>這是一個段落。</p>
    <ol>
      <li>項目一</li>
      <li>項目二</li>
    </ol>
  </body>
</html>
```

</div>
<div class="col alt">

![w:600](assets/html-architecture.svg)

</div>
</div>

Notes: head 放設定與 CSS；body 放內容；script 擺在 body 底部，確保上方的 HTML 元素已載入完畢。

---

### 常用 HTML 標籤

<hr>

| 標籤 | 用途 | 範例 |
|------|------|------|
| `<h1>`～`<h6>` | 標題（由大到小） | `<h1>大標題</h1>` |
| `<p>` | 段落文字 | `<p>一段話</p>` |
| `<a>` | 超連結 | `<a href="...">點我</a>` |
| `<img>` | 圖片 | `<img src="cat.jpg">` |
| `<ul>` / `<li>` | 無序清單 | `<ul><li>項目</li></ul>` |
| `<div>` | 區塊容器 | `<div>...</div>` |
| `<button>` | 按鈕 | `<button>送出</button>` |
| `<input>` | 輸入框 | `<input type="text">` |

---

<!-- _class: "section-page" -->

## CSS (Cascading Style Sheets)

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### CSS 基本語法

<hr>

```css
/* 選擇器 { 屬性: 值; } */
/* tag 選擇器 */
h1 {
  color: #1a73e8;      /* 文字顏色 */
  font-size: 48px;     /* 字體大小 */
  text-align: center;  /* 置中對齊 */
}
/* class 選擇器 */
.highlight {
  background: yellow;
  padding: 8px 16px;
}
/* id 選擇器 */
#main-btn {
  background: #1a73e8;
  color: white;
  border-radius: 8px;
}
```

Notes: 選擇器有三種：tag、.class、#id，優先級依序提高。

---

<!-- _class: "cols" -->

### CSS 常用屬性速查

<hr>

<div class="col-wrap">
<div class="col">

## 文字樣式

- `color` — 文字顏色
- `font-size` — 字體大小
- `font-weight` — 粗體
- `text-align` — 對齊方式
- `line-height` — 行距

</div>
<div class="col alt">

## 盒子模型

- `width / height` — 寬高
- `margin` — 外距
- `padding` — 內距
- `border` — 邊框
- `background` — 背景色
- `border-radius` — 圓角

</div>
</div>

---

<!-- _class: "section-page" -->

## JavaScript

讓網頁動起來的程式語言

---

<!-- _class: "cols" -->

### JavaScript 的故事

<hr>

<div class="col-wrap">
<div>

- **1995 年**
Brendan Eich 在 **10 天**內創造出這門語言
- **原名 Mocha → LiveScript**
為了搭 Java 熱潮，改名為 **JavaScript**
⚠️ 和 Java **完全沒有關係**
- **1997 年**
成為 ECMAScript 國際標準，各瀏覽器開始支援

</div>
<div>

- **2009 年**
Node.js 讓 JavaScript 走出瀏覽器、進入伺服器
- **2015 年（ES6）**
語法大幅現代化，成為主流程式語言
- **今天**
世界上使用人數最多的程式語言之一

</div>
</div>

---

### JavaScript 能做什麼？

<hr>

- **操作頁面內容**
讀取或修改 HTML 元素的文字、樣式、屬性
- **回應使用者操作**
監聽點擊、輸入、滾動等事件並執行動作
- **計算與邏輯處理**
條件判斷、迴圈、數學運算、字串處理
- **與伺服器溝通**
透過 `fetch()` 取得或送出資料（AJAX）

---

<!-- _class: "section-page" -->

## JavaScript 基礎語法

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 變數宣告

<hr>

```javascript
// let — 可以重新賦值的變數（推薦）
let name = "Alice";
let age = 20;

// const — 宣告後不能再改的常數（推薦）
const PI = 3.14159;
const SITE_NAME = "我的網站";

// var — 舊寫法，避免使用
var oldStyle = "不推薦";

// 重新賦值
name = "Bob";   // let 可以改
// PI = 3;      // const 不能改，會報錯
```

Notes: 現代 JS 盡量用 const，需要改值才用 let，避免用 var。

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 資料型別

<hr>

```javascript
// 字串 (String)
let greeting = "哈囉！";
let template = `你好，${name}！`;  // 樣板字串（反引號）

// 數字 (Number)
let score = 95;
let price = 19.99;

// 布林值 (Boolean)
let isLoggedIn = true;
let isEmpty = false;

// 陣列 (Array)
let fruits = ["蘋果", "香蕉", "芒果"];
console.log(fruits[0]);  // → "蘋果"

// 物件 (Object)
let student = { name: "Alice", age: 20, grade: "A" };
console.log(student.name);  // → "Alice"
```

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 運算子

<hr>

```javascript
// 算術運算子
let a = 10, b = 3;
console.log(a + b);   // 13
console.log(a - b);   // 7
console.log(a * b);   // 30
console.log(a / b);   // 3.333...
console.log(a % b);   // 1  ← 餘數

// 比較運算子（回傳 true / false）
console.log(5 === 5);   // true  ← 嚴格相等（推薦）
console.log(5 !== 3);   // true
console.log(10 > 5);    // true
console.log(3 <= 3);    // true

// 邏輯運算子
console.log(true && false);  // false（且）
console.log(true || false);  // true（或）
console.log(!true);          // false（非）
```

Notes: 用 === 而非 ==，避免型別自動轉換的陷阱。

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 條件判斷

<hr>

```javascript
let score = 75;

// if / else if / else
if (score >= 90) {
  console.log("優秀！A");
} else if (score >= 80) {
  console.log("良好！B");
} else if (score >= 70) {
  console.log("及格！C");
} else {
  console.log("需要加油！");
}
// → 輸出：及格！C

// 三元運算子（簡短版）
let status = score >= 60 ? "通過" : "不通過";
console.log(status);  // → "通過"
```

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 迴圈

<hr>

```javascript
// for 迴圈
for (let i = 1; i <= 5; i++) {
  console.log(`第 ${i} 次`);
}
// → 第 1 次、第 2 次 … 第 5 次

// while 迴圈
let count = 0;
while (count < 3) {
  console.log("count =", count);
  count++;
}

// 陣列遍歷（最常用）
let colors = ["紅", "綠", "藍"];

colors.forEach(function(color) {
  console.log(color);
});

// 箭頭函式簡寫（現代寫法）
colors.forEach(color => console.log(color));
```

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 函式

<hr>

```javascript
// 函式宣告
function greet(name) {
  return `你好，${name}！`;
}
console.log(greet("Alice"));  // → 你好，Alice！

// 有預設值的參數
function add(a, b = 0) {
  return a + b;
}
console.log(add(5, 3));  // → 8
console.log(add(5));     // → 5

// 箭頭函式（Arrow Function）
const multiply = (x, y) => x * y;
console.log(multiply(4, 3));  // → 12

// 呼叫自己寫的函式
function square(n) {
  return n * n;
}
console.log(square(7));  // → 49
```

Notes: 箭頭函式是現代 JS 常見寫法，特別是在 callback 裡。

---

<!-- _class: "section-page" -->

## 操作網頁元素

DOM — Document Object Model

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 什麼是 DOM？

<hr>

瀏覽器把 HTML 解析成一棵「樹狀結構」，JavaScript 可以透過 DOM API 讀取或修改每個節點。

```html
<!-- HTML -->
<h1 id="title">原始標題</h1>
<p class="info">一段文字</p>
<button id="btn">點我</button>
```

```javascript
// 用 id 選取元素
const title = document.getElementById("title");

// 用 CSS 選擇器選取（更靈活，推薦）
const info  = document.querySelector(".info");
const btn   = document.querySelector("#btn");

// 選取多個元素 → 回傳陣列
const allItems = document.querySelectorAll("li");
```

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 修改元素內容與樣式

<hr>

```javascript
const title = document.querySelector("#title");

// 修改文字內容
title.textContent = "新標題！";

// 修改 HTML 內容（可放標籤）
title.innerHTML = "<em>斜體新標題</em>";

// 修改 CSS 樣式
title.style.color = "red";
title.style.fontSize = "60px";

// 新增 / 移除 CSS class（更乾淨的做法）
title.classList.add("highlight");
title.classList.remove("highlight");
title.classList.toggle("active");  // 有就移除、沒有就新增

// 讀取 / 修改屬性
const img = document.querySelector("img");
img.getAttribute("src");          // 讀取
img.setAttribute("src", "new.jpg"); // 修改
```

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 事件監聽

<hr>

```javascript
const btn = document.querySelector("#btn");

// addEventListener(事件名稱, 處理函式)
btn.addEventListener("click", function() {
  alert("你點到按鈕了！");
});

// 箭頭函式寫法
btn.addEventListener("click", () => {
  console.log("被點擊！");
});

// 常用事件
// "click"      — 點擊
// "mouseover"  — 滑鼠移入
// "mouseout"   — 滑鼠移出
// "input"      — 輸入框內容改變
// "keydown"    — 按下鍵盤
// "submit"     — 表單送出
// "load"       — 頁面載入完成
```

---

<!-- _class: "section-page" -->

## JSON

JavaScript Object Notation — 輕量的資料交換格式

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### 什麼是 JSON？

<hr>

- **純文字格式**，用來表示結構化資料
- 語法來自 JavaScript 物件，但**任何語言都能讀寫**
- 副檔名 `.json`，或作為 API 回傳的資料格式

```json
{
  "name": "Alice",
  "age": 20,
  "isStudent": true,
  "courses": ["數學", "程式設計", "英文"],
  "address": {
    "city": "高雄",
    "zip": "804"
  }
}
```

Notes: JSON 是現代前後端溝通最普遍的格式，幾乎所有 Web API 都用 JSON 回傳資料。

---

<!-- _class: "cols" -->

### JSON 語法規則

<hr>

<div class="col-wrap">
<div class="col alt">

#### 合法 JSON

```json
{
  "name": "Alice",
  "age": 20,
  "active": true,
  "tags": ["web", "js"],
  "extra": null
}
```

</div>
<div class="col alt">

#### 常見錯誤

```json
{
  name: "Alice",       // ✗ 鍵名沒有引號
  "age": 20,
  "active": true,
  "note": undefined,   // ✗ 不支援 undefined
  // 這是註解       // ✗ 不支援註解
}

```

</div>
</div>

Notes: JSON 的鍵名一定要用雙引號，值只能是字串、數字、布林、陣列、物件、null 六種類型。

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### JSON.stringify() 與 JSON.parse()

<hr>

```javascript
// JS 物件 → JSON 字串（用於儲存或傳送）
const student = { name: "Alice", age: 20, courses: ["數學", "程式"] };
const jsonStr = JSON.stringify(student);
console.log(jsonStr);
// → '{"name":"Alice","age":20,"courses":["數學","程式"]}'
console.log(typeof jsonStr);  // → "string"

// JSON 字串 → JS 物件（用於讀取或接收）
const obj = JSON.parse(jsonStr);
console.log(obj.name);        // → "Alice"
console.log(obj.courses[0]);  // → "數學"
console.log(typeof obj);      // → "object"

// 加上縮排，方便閱讀（第三個參數）
console.log(JSON.stringify(student, null, 2));
```

Notes: stringify 把物件「打包成字串」才能存進 localStorage 或透過網路傳送；parse 則是「解包」還原成物件。

---

### 開發者工具 DevTools

<hr>

開啟方式：`F12` 或 右鍵 → 「檢查」

- **Console**
執行 JS 指令、查看 `console.log()` 輸出、除錯
- **Elements**
即時查看與修改 HTML 結構和 CSS 樣式
- **Sources**
查看 JS 原始碼，設定中斷點 (breakpoint) 一行一行 debug
- **Network**
監看網路請求，查看載入的檔案與時間

Notes: DevTools 是前端開發者最重要的工具。

---

<!-- _class: "section-page" -->

## Gemini Canvas

用 AI 生成網頁：讓對話直接變成 HTML/CSS/JS

---

### 什麼是 Gemini Canvas？

<hr>

Google Gemini（gemini.google.com）內建的**互動式程式碼／文件編輯環境**，會在對話旁開一個「畫布」即時顯示產生的結果

- 請 Gemini 用文字描述一個網頁，它會**直接寫出 HTML/CSS/JS**
- 畫布會**即時預覽**渲染後的畫面，不只是顯示程式碼
- 可以繼續用**自然語言下指令修改**，不需要自己改程式碼
- 適合快速做出 prototype、Landing Page、小工具

---

<!-- class: "cols" -->

### 基本工作流程

<hr>

<div class="col-wrap">
<div class="col alt">

**Step 1～2**

1. 在 Gemini 輸入你想要的網頁描述
2. Gemini 產生程式碼，畫布同步顯示**即時預覽**

</div>
<div class="col alt">

**Step 3～4**

3. 用一句話描述要修改的地方（改顏色、加按鈕…）
4. 滿意後**下載程式碼**或複製到自己的專案繼續開發

</div>
</div>

---

### Prompt 的技巧

<hr>

<div class="col-wrap">
<div class="col alt">

**寫得不清楚**

```
幫我做一個網頁
```

AI 只能自由發揮，結果通常很陽春、
不一定符合你想要的方向

</div>
<div class="col alt">

**寫得清楚**

```
製作 html/css/js 網頁。
網頁內容是 [咖啡店] 的 Landing Page，要有：
- 頂部大圖 + 店名標語
- 三個特色介紹卡片
- 「立即預約」按鈕
- 淺棕色系配色
參考資訊：...
```

</div>
</div>

Notes: 和寫程式一樣，需求描述得越具體（版面、內容、配色、互動），Gemini 產出的結果就越接近你要的樣子。

---

### 用自然語言持續修改

<hr>

畫布產生初版後，直接對話即可迭代調整：

- 「把按鈕顏色改成綠色，字體加大一點」
- 「在卡片區塊加上滑鼠移過去的放大效果」
- 「幫我加一個聯絡表單，送出後用 alert 顯示謝謝訊息」
- 「這個網頁在手機上跑版了，幫我修成響應式排版」

---

### 匯出與接續開發

<hr>

- Canvas 產生的程式碼可以**下載成 .html**
- 下載後就是一般的靜態網頁，可以用 VS Code 打開繼續修改
- 部署方式與一般靜態網頁相同：GitHub Pages、Netlify、Vercel…

---

<!-- class: "cols" -->

### 使用時的注意事項

<hr>

<div class="col-wrap">
<div class="col alt">

**要做的事**

- 通讀一遍 AI 產生的程式碼，理解它在做什麼
- 測試各種操作與畫面尺寸，確認沒有壞掉
- 把不需要的功能或範例文字清乾淨

</div>
<div class="col alt">

**要避免的事**

- 完全不檢查就直接拿去交作業／上線
- 把帳密、API 金鑰等敏感資訊寫進 prompt
- 誤以為「AI 寫的就是對的」，跳過理解直接複製

</div>
</div>

---

<!-- _class: cols -->

### SWP01 Pomodoro Technique

<hr>

<div class="col-wrap">
<div>

#### 任務

使用 Gemini Canvas 製作一個「番茄鐘」網頁，並使用 HTML、CSS、JavaScript 完成。

#### 要求

1. 顯示倒數計時的時鐘
2. 開始/暫停按鈕
3. 直接以 Gemini 共用連結分享

</div>

<div>

番茄鐘（又稱番茄工作法，Pomodoro Technique）是一種在1980年代末期由義大利人弗朗西斯科·西里洛創立的時間管理方法。它透過將工作時間切割成多個短週期，幫助大腦保持高度專注並減少疲勞。

</div>
</div>

---

<!-- _class: cols -->

### SWP02 Landing Page

<div class="col-wrap">
<div>

#### 任務
任意挑選一個主題，設計一個 Landing Page，並使用 HTML、CSS、JavaScript 完成。

#### 要求

1. 任意主題的 Landing Page
2. 挑選設計風格並使用線上圖片
3. 部署至 Google Sites

</div>
<div>

Landing Page（引導頁）是網路行銷與廣告中的一個獨立網頁。當使用者點擊廣告、社群媒體連結、電子郵件或搜尋引擎結果後，會「降落」或進入這個頁面。

核心特徵與目的：
單一明確的目標，每個 Landing Page 都只有一個主要任務，例如：填寫表單領取優惠、註冊免費試用、購買特定商品、報名活動或下載電子書。

</div>
</div>

---

### 如何將 Landing Page 部署到 Google Sites？

<hr>

1. 前往 [Google Sites](https://sites.google.com)，建立一個新網站
2. 把 HTML、CSS、JavaScript 整合成單一 `.html` 檔案（直接複製 Gemini Canvas 產生的程式碼）
3. 在編輯畫面右側選單點選「插入」→「嵌入」→「嵌入程式碼」
4. 貼上完整的 HTML 原始碼，並調整嵌入框大小以符合版面
5. 點選右上角「發布」，設定網址後正式公開

Notes: Google Sites 的嵌入程式碼是在 sandboxed iframe 中執行，部分 JavaScript 功能可能受限；圖片等外部資源需使用可公開存取的網址，無法直接上傳本機圖片。

---

<!-- _class: cols -->

### 風格設計參考

<div class="col-wrap">
<div>

#### 設計風格

- [Pinterest](https://www.pinterest.com/) — 圖片靈感牆，搜尋主題找配色與版面參考
- [Awwwards](https://www.awwwards.com/) — 精選得獎網站作品，看頂尖視覺與互動設計
- [Land-book](https://land-book.com/) — 專門收錄 Landing Page 案例，最貼近作業主題

</div>
<div>

#### 線上圖庫

- [Unsplash](https://unsplash.com/) — 高解析度攝影作品，風格質感佳
- [Pexels](https://www.pexels.com/) — 免費圖片與影片，種類豐富好搜尋
- [Pixabay](https://pixabay.com/) — 圖片、插畫、向量圖都有，選擇多元

</div>
</div>
Note: Gemini Canvas 開發的網頁，無法使用上傳的圖片，必須使用網路上可直接存取的圖片網址。

---

<!-- _class: "section-page" -->

## 瀏覽器儲存：LocalStorage

網頁關掉再開，資料還在！

---

### 什麼是 LocalStorage？

<hr>

瀏覽器送給你的一個「小型私人儲物櫃」

- HTML5 內建的**鍵值儲存空間**，資料存在使用者的瀏覽器裡
- 關閉分頁、重新整理、甚至重開電腦後，資料**不會消失**
- 不需要透過網路向伺服器索取，直接在瀏覽器端讀寫

Notes: 這是一種 client-side storage，完全不依賴後端，非常適合靜態網頁使用。

---

<!-- _class: "cols" -->

### 為什麼需要 LocalStorage？

<hr>

以購物網站的購物車為例：

<div class="col-wrap">
<div class="col alt">

**沒有 LocalStorage**

商品加入購物車，一重新整理頁面
→ 購物車**清空了**

</div>
<div class="col alt">

**有了 LocalStorage**

選好的商品存進儲物櫃，下次再開網站
→ **自動恢復**購物車狀態

</div>
</div>

Notes: 除了購物車，常見應用還有：記住深色/淺色主題設定、記住使用者名稱、暫存表單草稿等。

---

### LocalStorage 的核心特點

<hr>

- **永久性** — 沒有過期時間，只要不主動刪除就會一直存在
- **容量限制** — 約 **5 MB**，適合設定、偏好、暫存資料，不能存大型檔案
- **字串格式** — 只能存字串；物件或陣列需先用 `JSON.stringify()` 轉換
- **網域隔離** — 網站 A 的資料，網站 B 完全讀不到，保護使用者隱私
- **本機限定** — 清除網站資料、更換瀏覽器或電腦後資料會消失，不會自動同步到其他裝置

---

<style scoped>
pre code { font-size: 0.5em; line-height: 1.15; }
</style>

### LocalStorage 基本操作

<hr>

```javascript
// 寫入
localStorage.setItem("username", "Alice");
localStorage.setItem("theme", "dark");

// 讀取（key 不存在時回傳 null）
const name  = localStorage.getItem("username"); // "Alice"
const theme = localStorage.getItem("theme");    // "dark"

// 刪除單筆 / 清除全部
localStorage.removeItem("theme");
localStorage.clear();

// 儲存物件：先轉成 JSON 字串
const user = { name: "Alice", age: 20 };
localStorage.setItem("user", JSON.stringify(user));

// 讀取物件：再從 JSON 字串還原
const loaded = JSON.parse(localStorage.getItem("user"));
```

Notes: DevTools → Application → Local Storage 可以查看目前存了哪些資料，也可以手動刪除。

---

### 與其他儲存方式的比較

<hr>

| 類型 | 生命週期 | 容量 | 常見用途 |
|------|---------|------|---------|
| **LocalStorage** | 永久（手動刪除才消失） | ~5 MB | 深色模式、長期購物車 |
| **SessionStorage** | 關閉分頁後自動刪除 | ~5 MB | 單次登入狀態、表單暫存 |
| **Cookies** | 可設定過期時間 | ~4 KB | 登入 Token、廣告追蹤 |

Notes: Cookies 因為容量小、且每次 HTTP 請求都會帶上，主要用於伺服器需要知道的資訊（如登入狀態）。靜態網頁通常用 LocalStorage 就夠了。

---

### 安全警告

<hr>

**千萬不要**在 LocalStorage 裡儲存密碼、信用卡號或其他敏感資訊

- 任何執行在該頁面的 JavaScript **都能讀取**到這些資料
- 若網站存在 **XSS 漏洞**，攻擊者可輕易竊取全部內容
- LocalStorage 適合存**非敏感**的偏好設定或暫存資料

Notes: XSS（Cross-Site Scripting）是最常見的網頁安全漏洞之一，攻擊者注入惡意 JS 後可直接呼叫 localStorage.getItem() 竊取資料。

---

### 部署成 GitHub Pages (1/2)

<hr>

- **準備單一網頁檔案**
  - 將 HTML、CSS 與 JavaScript 放在同一個檔案中，命名為 `index.html`。
  - 在瀏覽器開啟檔案，確認功能與版面正常。
- **建立 GitHub 儲存庫**
  - 登入 [GitHub](https://github.com)，點選右上角「+」 $\rightarrow$ 「New repository」。
  - 輸入儲存庫名稱，設定為 Public，然後建立儲存庫。
- **上傳網站檔案**
  - 在儲存庫中點選「Add file」 $\rightarrow$ 「Upload files」。
  - 上傳 `index.html`，再點選「Commit changes」。

---

### 部署成 GitHub Pages (2/2)

- **啟用 GitHub Pages**
  - 進入「Settings」 $\rightarrow$ 「Pages」。
  - 在 Build and deployment 選擇「Deploy from a branch」，分支選擇 `main` 與 `/ (root)`，按下「Save」。
- **開啟公開網址**
  - 等待約一分鐘，重新整理 Pages 設定頁面。
  - 點選 GitHub 顯示的 `https://帳號名稱.github.io/儲存庫名稱/` 網址，即可查看網站。

Notes: 首頁檔案必須命名為 `index.html`。之後只要重新上傳並 commit 新版本，GitHub Pages 會自動更新網站。

---

<!-- _class: cols -->

### SWP03 待辦清單（To-Do List）

<hr>

<div class="col-wrap">
<div>

#### 任務

製作一個「待辦清單」網頁，並使用靜態網頁技術與 LocalStorage 完成。

#### 要求

1. 可新增待辦事項
2. 可標記已完成與刪除事項
3. 重新整理頁面後清單內容仍會保留（LocalStorage）
4. 部署成 GitHub Pages

</div>

<div>

待辦清單（To-Do List）是一種用來記錄、整理與追蹤日常任務的工具。使用者可以隨時新增事項，完成後標記或刪除；透過 LocalStorage 將清單儲存在瀏覽器中，即使重新整理或關閉網頁，資料仍能在下次開啟時保留。

Notes: 加入 LocalStorage 後，重新整理頁面清單仍會保留。這是 LocalStorage 最常見的應用場景之一。

</div>
</div>


---

<!-- _class: cols -->

### SWP04 便利貼看板

<hr>

<div class="col-wrap">
<div>

#### 任務

製作一個「便利貼看板」網頁，並使用靜態網頁技術與 LocalStorage 完成。

#### 要求

1. 可新增不同顏色的便利貼
2. 可編輯與刪除便利貼內容
3. 重新整理後，便利貼內容仍會保留（LocalStorage）
4. 部署成 GitHub Pages

</div>

<div>

便利貼看板（Sticky Notes Board）是將零散想法、提醒事項或短期任務視覺化的工具。每張便利貼都是獨立資料；將它們儲存至 LocalStorage，可讓看板在關閉或重新開啟瀏覽器後，仍保有原本的內容與排列。

</div>
</div>

Notes: 可嘗試用不同顏色區分工作、學習與生活事項；進一步挑戰可加入拖曳排序功能。

---

<!-- _class: cols -->

### SWP05 網頁小遊戲

<hr>

<div class="col-wrap">
<div>

#### 任務

- 自行選擇一個遊戲主題（例如：貪食蛇、記憶翻牌或太空侵略者），製作一個可在瀏覽器中操作的網頁小遊戲。
- 使用 HTML、CSS、JavaScript 與 LocalStorage 完成。

Notes: 先做出可玩的最小版本，再逐步加入計分、倒數計時、音效或難度設定。
</div>

<div>

#### 要求

1. 提供明確的操作方式與開始／重新開始功能
2. 顯示遊戲結果，例如分數、時間、過關或失敗訊息
3. 使用 LocalStorage 儲存遊戲進度或最高分數
4. 部署成 GitHub Pages

</div>
</div>

---

<!-- _class: section-page -->

## API (Application Programming Interface)

---

### 什麼是 API？

應用程式介面（application program interface，API），廣義來說，能讓二個電腦系統進行互相溝通的方式就是API。

![w:1100](assets/api-001.png)

---

### 什麼是 API？

應用程式介面（application program interface，API），廣義來說，能讓二個電腦系統進行互相溝通的方式就是API。

![w:1100](assets/api-002.png)

---

### 什麼是 API？

應用程式介面（application program interface，API），廣義來說，能讓二個電腦系統進行互相溝通的方式就是API。

![w:1100](assets/api-003.png)

---

### 什麼是 API？

應用程式介面（application program interface，API），廣義來說，能讓二個電腦系統進行互相溝通的方式就是API。

![w:1100](assets/api-004.png)

---

### 前端呼叫 API 的架構

![w:1100](assets/api-client-server-001.png)

---

### 後端呼叫 API 的架構

![w:1100](assets/api-client-server-002.png)

---

### API 範例

- [Open-Meteo](https://open-meteo.com/) — 免費氣象 API / [高雄市氣象](https://api.open-meteo.com/v1/forecast?latitude=22.6273&longitude=120.3014&current=temperature_2m,relative_humidity_2m,apparent_temperature,precipitation,weather_code,wind_speed_10m&daily=weather_code,temperature_2m_max,temperature_2m_min,precipitation_probability_max&timezone=Asia%2FTaipei)
- [DOG CEO](https://dog.ceo/) — 隨機狗狗圖片 API / [隨機狗狗圖片](https://dog.ceo/api/breeds/image/random)
- [The RESTful Pokémon API](https://pokeapi.co/) — 寶可夢 API / [皮卡丘資料](https://pokeapi.co/api/v2/pokemon/pikachu)
- [Lorem Picsum](https://picsum.photos/) - 圖片 / [隨機圖片 1920*1080](https://picsum.photos/1920/1080)

**Notes:** 如果使用 API 需要金鑰（API Key），請務必保護好，不要放在公開的程式碼中。那如何在前端使用 API Key 呢？

---

### 政府資料開放平台

政府機關將可公開、可再利用的資料，以標準化格式放到網路上，讓民眾、研究者與開發者自由查詢和應用。

- 平台：[data.gov.tw](https://data.gov.tw/)
- 資料來源：中央與地方政府機關
- 常見主題：交通、空氣品質、觀光、教育、醫療、人口統計
- 核心精神：**公開透明、資料再利用、促進創新**

---

<!-- _class: cols3 -->

### 如何使用政府開放資料？

<div class="col-wrap">
<div class="col alt">

**1. 找資料**

- 用關鍵字或分類搜尋資料集
- 查看資料提供機關與更新日期
- 確認資料是否符合需求

</div>
<div class="col alt">

**2. 讀資料**

- 選擇下載檔案或 API
- 閱讀欄位說明與使用規則
- 確認格式、編碼與更新頻率

</div>
<div class="col alt">

**3. 做應用**

- 用 JavaScript `fetch()` 取得資料
- 將 JSON 轉成網頁上的圖表或清單
- 標示資料來源與最後更新時間

</div>
</div>

---

### 開放資料的常見格式

| 格式 | 適合用途 | 特點 |
|---|---|---|
| **CSV** | 試算表、統計分析 | 表格直觀，容易用 Excel 開啟 |
| **JSON** | 網頁與 API | 適合程式讀取，能表示巢狀資料 |
| **XML** | 系統交換、既有服務 | 結構明確，但文字較冗長 |
| **GeoJSON** | 地圖與地理資料 | 可描述點、線、面與座標 |

**使用前要檢查：**資料欄位、編碼（通常是 UTF-8）、更新時間、授權條款與資料來源。

---

### 從開放資料到網頁

![w:900](assets/open-data-architecture.svg)
```js
fetch("資料集的 API 網址")
  .then(response => response.json())
  .then(data => { console.log(data); });
```

---

### 使用政府資料時的責任

- **確認來源**：顯示資料提供機關與原始連結
- **確認時效**：資料可能延遲、停更或尚未完整更新
- **確認定義**：讀懂欄位說明、單位與統計範圍
- **尊重授權**：依資料集的授權條款使用與再發布
- **保護個資**：不嘗試還原或推測可識別個人的資訊

> 開放資料不代表「不需要查證」；它是應用程式的原料，品質與解讀仍需要負責任地確認。

---

### 開放資料範例

- [每月盛產農產品產地](https://data.moa.gov.tw/open_detail.aspx?id=061)
全台農產盛產期與產地資訊，非常適合拿來做程式開發、資料視覺化、節氣食譜應用或農產地圖網頁。
- [動物認領養](https://data.moa.gov.tw/open_detail.aspx?id=QcbUEzN6E6DL)
包含全台各公立動物收容所內待認養動物的詳細資訊，用來設計即時的流浪動物協尋、溫馨領養媒合通知介面。
- [個股日成交資訊](https://data.gov.tw/dataset/11549)
透過政府開放資料的 CSV/JSON 格式進行串接，打造個人化的股市看板、技術指標分析工具或自動化爬蟲腳本。

---

### 瀏覽器的安全限制：CORS

<hr>

**CORS**（Cross-Origin Resource Sharing，跨來源資源共享）是瀏覽器內建的安全機制。

- 瀏覽器預設遵守**同源政策（Same-Origin Policy）**：網頁只能自由存取「相同來源」的資源
- **來源（Origin）** = 協定 + 網域 + 埠號，三者都相同才算同源
  例：`https://a.com` 呼叫 `https://api.b.com` 就是**跨來源**
- 用 `fetch()` 呼叫別的網域的 API 時，瀏覽器會檢查該伺服器的回應標頭是否**明確允許**你的網站存取

Notes: CORS 限制的是瀏覽器端的 JavaScript，不是伺服器本身；用 Postman 或後端程式呼叫同一個 API 通常不會被擋。

---

### CORS 錯誤長什麼樣子？

<hr>

在瀏覽器的開發者工具 Console 常會看到：

```text
Access to fetch at 'https://api.example.com/data' from origin
'https://your-site.github.io' has been blocked by CORS policy:
No 'Access-Control-Allow-Origin' header is present on the requested resource.
```

- 這不是你的程式碼語法錯誤，資料其實有送出、伺服器也有回應，問題出在**伺服器沒有回傳允許的標頭**。
- 練習時的因應方式：（[檢測工具](https://sites.google.com/view/cors-check/)）
  1. 優先選擇文件中**明確支援 CORS** 或設計給前端直接呼叫的公開 API。
  2. 若必須串接不支援 CORS 的資料源，改由**後端伺服器代為請求**（Full-Stack 章節會介紹）

---

<!-- _class: cols -->

### SWP06 資訊看板

<hr>

<div class="col-wrap">
<div>

#### 任務

使用靜態網頁技術，串接至少一個 API 或政府開放資料，製作一個資訊看板。

資訊看板（Dashboard）：把即時或定期更新的資料轉化成一目了然的畫面。無論是氣象、寵物領養或農產品產地，重點都在於誠實標示來源、留意資料的更新頻率，並在請求失敗時給使用者明確的回饋，而不是留下一片空白。

</div>

<div>

#### 要求

1. 至少串接一個 API 或開放資料集，頁面明確標示資料來源
2. 將資料轉換為適合閱讀的呈現方式（列表、卡片或圖表皆可）
3. 處理載入中與請求失敗時的提示（例如來源暫時掛掉）
4. 部署成 GitHub Pages


</div>
</div>

---

### 地圖 API

Leaflet.js + OpenStreetMap 是製作互動式地圖的常見組合。

- **Leaflet.js**：輕量的 JavaScript 地圖函式庫，負責地圖、標記與互動
- **OpenStreetMap（OSM）**：由社群維護的開放街圖資料
- Leaflet 負責「怎麼顯示」，OSM 提供「顯示什麼地圖」

---

<!-- _class: cols3 -->

### Leaflet 地圖的基本組成

<div class="col-wrap">
<div class="col alt">

**地圖容器**

HTML 預留一個 `div`，Leaflet 將地圖畫在裡面。

</div>
<div class="col alt">

**圖磚圖層**

從地圖服務載入一張張圖磚，拼成完整地圖。

</div>
<div class="col alt">

**圖層與標記**

加入 Marker、Popup、Circle 或 GeoJSON 資料。

</div>
</div>

```text
HTML 容器 → Leaflet 地圖 → OSM 圖磚
↘ 標記、彈出視窗、路線
```

---

### 使用 OpenStreetMap 的注意事項

- 顯示圖磚時，必須保留 `OpenStreetMap` attribution
- 遵守 [OpenStreetMap Tile Usage Policy](https://operations.osmfoundation.org/policies/tiles/)
- 不要大量下載、快取或模擬正常使用者請求
- 商業或高流量服務應選擇合適的圖磚服務商
- OpenStreetMap 是地圖資料來源，不等於完整的導航或地址搜尋 API

---

<!-- _class: cols -->

### SWP07 地圖資訊

<hr>

<div class="col-wrap">
<div>

#### 任務

使用 Leaflet.js + OpenStreetMap，製作一個能在地圖上呈現即時資料點的網頁，例如 YouBike 站點、停車場空位或觀光景點。

可搭配政府開放資料中「含經緯度欄位」的資料集，例如各縣市 YouBike 2.0 即時資料、公共停車場資訊等，讓地圖上的標記會隨資料更新。

</div>

<div>

#### 要求

1. 設定合理的初始中心點與縮放層級
2. 至少串接一個含經緯度欄位的 API 或開放資料（例如 YouBike 即時資料）
3. 將每筆資料以 Marker 標示在地圖上，點擊後以 Popup 顯示重點資訊（如站名、可借／可還數量）
4. 部署成 GitHub Pages

</div>
</div>

---

<!-- _class: "section-page" -->

## Teachable Machine

讓機器學習模型走進靜態網頁

---

### 什麼是 Teachable Machine？

<hr>

- Google 推出的**免程式碼**機器學習訓練工具，網址：[https://teachablemachine.withgoogle.com](https://teachablemachine.withgoogle.com/)
- 在瀏覽器裡收集範例資料，訓練「圖片／聲音／姿勢」分類模型
- 背後技術是 **TensorFlow.js**，訓練完可直接匯出到網頁使用
- 不需要寫訓練程式碼，也不需要 GPU 或安裝環境

Notes: 訓練過程全部在瀏覽器內完成，資料不會上傳到 Google 的伺服器。

---

<!-- _class: "cols3" -->

### 三種模型類型

<hr>

<div class="col-wrap">
<div class="col alt">

**Image Project**

分類照片或即時攝影機畫面
例：手勢、物品、表情

</div>
<div class="col alt">

**Audio Project**

分類聲音片段
例：指令詞、環境音、拍手聲

</div>
<div class="col alt">

**Pose Project**

分類人體姿勢
例：動作偵測、運動計數

</div>
</div>

---

<!-- _class: "cols3" -->

### 訓練流程：Gather → Train → Export

<hr>

<div class="col-wrap">
<div class="col alt">

**1. 收集資料**

為每個類別（Class）用攝影機／麥克風蒐集範例，類別間數量盡量平衡

</div>
<div class="col alt">

**2. 訓練模型**

在瀏覽器內按一鍵訓練，即時顯示準確率與訓練曲線

</div>
<div class="col alt">

**3. 匯出模型**

輸出成 TensorFlow.js／TFLite／TensorFlow 格式，取得可用的網址或檔案

</div>
</div>

Notes: 這三步驟不需要離開瀏覽器；Export 之後才會需要把模型接到自己的網頁專案。

---

### 為什麼範例的「多樣性」很重要？

<hr>

- 光線、角度、背景、距離都要有變化，模型才不會只認得單一情境
- 每個類別的範例數量要盡量平衡，避免模型偏向數量多的類別
- 建議加入一個 **Background / Nothing** 類別，代表「什麼都不是」的情況
- 訓練與實際使用的環境差太多時，模型準確率會明顯下降

Notes: 這是機器學習常見的**過擬合（overfitting）**問題——模型記住的是訓練時的背景與角度，而不是真正的特徵。

---

### 把模型嵌入靜態網頁

<hr>

- Teachable Machine 匯出頁面的「TensorFlow.js」分頁，會直接提供一段可複製的範例程式碼
- 透過 `<script>` 載入對應函式庫：`@teachablemachine/image`／`/audio`／`/pose`
- 網頁端即時擷取攝影機或麥克風畫面，逐格丟進模型做預測（`predict()`）
- 所有運算都在**使用者的瀏覽器**完成，不需要後端伺服器

---

### 使用時的注意事項

<hr>

- 使用攝影機／麥克風需要使用者主動授權，瀏覽器會跳出權限請求視窗
- 呼叫 webcam／microphone API 需要 **HTTPS** 網站（GitHub Pages 部署後預設符合）
- 模型分享設定若為「Private」，他人將無法載入該模型網址，依需求調整
- 模型的準確率完全取決於訓練資料，正式使用前務必用不同情境實測

> 用攝影機或麥克風蒐集他人資料前，務必告知並取得同意；不要在使用者不知情的狀況下錄影或錄音。

---

### Teachable Machine 能做什麼應用？

<hr>

- **手勢控制網頁**：比讚換頁、比 OK 播放音樂
- **物品辨識小工具**：回收分類教學、教具/道具識別
- **聲音指令觸發**：拍手計數、喊口令啟動特效
- **姿勢辨識小遊戲**：深蹲計數、伸展提醒、體感互動

---

<!-- _class: cols -->

### SWP08 影像/姿勢/聲音互動遊戲

<hr>

<div class="col-wrap">
<div>

#### 任務

使用 Teachable Machine 訓練一個圖片、聲音或姿勢分類模型，將模型嵌入靜態網頁遊戲，做出會依辨識結果產生互動效果的遊戲。

</div>

<div>

#### 要求

1. 至少訓練 2 個類別，並說明怎麼進行遊戲或操作。
2. 頁面顯示攝影機或麥克風畫面，以及目前辨識結果與信心分數
3. 依辨識結果觸發至少一種畫面變化（換背景、播放音效、顯示訊息等）
4. 部署成 GitHub Pages

</div>
</div>

---

<!-- _class: "section-page" -->

## Web Speech API

讓網頁開口說話，也聽得懂你說的話

---

### 什麼是 Web Speech API？

<hr>

瀏覽器**原生內建**的語音功能，不需外部服務或安裝套件

- **SpeechSynthesis**：文字轉語音（Text-to-Speech），讓網頁「念」出文字
- **SpeechRecognition**：語音轉文字（Speech-to-Text），讓網頁「聽懂」使用者說的話
- 目前以 **Chrome／Edge** 等 Chromium 系瀏覽器支援最完整

Notes: Web Speech API 是 W3C 的規範草案，尚未所有瀏覽器都完整支援，例如 Safari 對 SpeechRecognition 的支援就相當有限，建議開發與展示都用 Chrome。

---

<!-- _class: "cols" -->

### 兩大功能比較

<hr>

<div class="col-wrap">
<div class="col alt">

**SpeechSynthesis（朗讀）**

文字 → 語音
輸入一段文字，瀏覽器用語音唸出來
例：唸出單字、朗讀文章

</div>
<div class="col alt">

**SpeechRecognition（聽寫）**

語音 → 文字
開啟麥克風錄音，轉成文字辨識結果
例：語音輸入、跟讀評分

</div>
</div>

---

<style scoped>
pre code { font-size: 0.6em; line-height: 1.2; }
</style>

### 語音合成：SpeechSynthesis

<hr>

```javascript
const utterance = new SpeechSynthesisUtterance("Hello, world!");
utterance.lang = "en-US";   // 語言（發音腔調）
utterance.rate = 1;         // 語速，範圍 0.1 ~ 10
utterance.pitch = 1;        // 音調，範圍 0 ~ 2

speechSynthesis.speak(utterance); // 開始朗讀
```

Notes: speechSynthesis.getVoices() 可以列出瀏覽器內建的語音包，挑選不同語言或語者（部分語音包需等頁面載入後才會就緒）。

---

<style scoped>
pre code { font-size: 0.55em; line-height: 1.2; }
</style>

### 語音辨識：SpeechRecognition

<hr>

```javascript
const recognition = new webkitSpeechRecognition(); // Chrome 需加上 webkit 前綴
recognition.lang = "en-US";
recognition.interimResults = false; // true 可即時顯示辨識中的結果

recognition.onresult = (event) => {
  const text = event.results[0][0].transcript;
  console.log("辨識結果：", text);
};

recognition.start(); // 開始錄音並辨識
```

Notes: 第一次呼叫 start() 時，瀏覽器會跳出麥克風授權請求；辨識結果的準確率會受口音、語速、環境噪音影響。

---

### 使用時的注意事項

<hr>

- 呼叫麥克風（SpeechRecognition）需要 **HTTPS** 網站，GitHub Pages 部署後預設符合
- 使用前瀏覽器會跳出麥克風授權請求視窗，需使用者主動同意
- SpeechRecognition 主要支援 **Chrome／Edge**，其他瀏覽器相容性較差，展示前務必先測試
- `lang` 屬性建議明確指定（如 `"en-US"`、`"zh-TW"`），發音與辨識才會準確

> 語音辨識過程可能將錄音送到瀏覽器背後的雲端服務處理，避免用來錄製機敏或個資內容

---

### Web Speech API 能做什麼應用？

<hr>

- **語言學習**：單字／例句聽讀、口說跟讀練習
- **語音助理**：用語音下指令操作網頁
- **無障礙輔助**：螢幕內容報讀、免手動輸入
- **語音筆記**：口述內容即時轉成文字紀錄

---

<!-- _class: cols -->

### SWP09 英文聽讀 APP

<hr>

<div class="col-wrap">
<div>

#### 任務

製作一個英文聽讀練習網頁，結合 SpeechSynthesis 朗讀英文，並用 SpeechRecognition 讓使用者跟讀，自動比對發音是否正確。

或是其他有運用到 Web Speech API 的互動應用也可以。

</div>

<div>

#### 要求

1. 提供一份英文單字或片語清單，可點擊播放正確發音
2. 使用者可按下錄音鍵跟讀，透過 SpeechRecognition 將語音轉成文字
3. 比對辨識結果與正確單字，顯示念對／念錯，並統計練習的正確率
4. 部署成 GitHub Pages

</div>
</div>



