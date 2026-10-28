---
marp: true
theme: corporate
title: 人工智慧應用開發實務 / Single Page Application
paginate: true
transition: slide
---

<!-- _class: cover -->

# 人工智慧應用開發實務
## Single Page Application

<hr>

許智超
<cchsu@mail.nsysu.edu.tw>


---

<!-- _class: section-page -->

<span class="num">01</span>

## Agentic Coding Systems

<hr>

---

<!-- _class: stats -->

### 什麼是 Agentic Coding？

<hr>

<div class="stat-wrap">
<div class="stat">

#### AI 是執行者，不只是顧問
<hr>

AI 代理 (Agent) 能自行讀寫檔案、執行指令、安裝套件並測試程式。

</div>
<div class="stat hi">

#### 目標導向的迴圈
<hr>

你給定目標，Agent 自行「規劃 → 實作 → 執行 → 檢查錯誤 → 修正」，直到完成。

</div>
<div class="stat">

#### 人負責方向與驗收
<hr>

人類專注於需求、決策與審查結果，不再逐行手寫程式。

</div>
</div>

---

<!-- _class: cols -->

### 從 Chatbot 到 Agentic Coding

<hr>

<div class="col-wrap">
<div class="col">

#### Chatbot 輔助

- **流程**：提問 → 取得程式碼片段 → 人工複製貼上 → 自行執行。
- **上下文**：只看得到你貼上的內容，不了解整個專案。
- **錯誤處理**：執行失敗後，需把錯誤訊息貼回對話。
- **角色**：AI 是顧問，人是唯一的執行者。

</div>
<div class="col alt">

#### Agentic Coding

- **流程**：描述目標 → Agent 直接修改專案並執行驗證。
- **上下文**：可瀏覽整個專案、讀取檔案與設定。
- **錯誤處理**：自行讀取錯誤訊息並反覆修正。
- **角色**：AI 是執行者，人是決策者與審查者。

</div>
</div>

---

### 為什麼要改用 Agentic Coding？

<hr>

- **省去搬運**：不用在對話視窗與編輯器間來回複製貼上
- **完整上下文**：理解專案結構，產出的程式碼能與既有程式一致
- **自動驗證**：執行、測試、除錯形成閉環，不只給出「看起來對」的程式
- **跨工具操作**：可呼叫 CLI（git、firebase）完成部署，不只是寫程式
- **適合 SPA 開發**：前端、資料庫、驗證、部署多個環節，Agent 可一次串起

> 注意：Agent 也會出錯，需要版本控制 (git) 與人工審查把關。

---

### Agentic Coding 系統的組成

<hr>

- **LLM（大型語言模型）**：負責理解與推理
- **CLI / 工具**：讓模型能讀寫檔案、執行指令（如 Claude Code）
- **MCP**：以標準協定連接外部服務與資料
- **Skill**：封裝可重複使用的做法與指引，讓 Agent 依流程工作

---

<!-- _class: stats -->

### CLI、MCP、Skill 三者的角色

<hr>

<div class="stat-wrap">
<div class="stat">

#### CLI：雙手
<hr>

命令列工具，讓 Agent 能執行 git、npm、firebase 等指令。

</div>
<div class="stat hi">

#### MCP：連接外部
<hr>

標準協定，讓 Agent 存取資料庫、文件、設計工具等外部服務。

</div>
<div class="stat">

#### Skill：工作手冊
<hr>

可重複使用的指引，讓 Agent 依既定流程與慣例完成任務。

</div>
</div>

---

### 介紹 CLI (Command Line Interface)

<hr>

- **定義**：以文字指令操作軟體的介面，不需圖形畫面
- **為何適合 Agent**：輸入輸出皆為文字，Agent 能直接執行並讀取結果
- **兩種角色**：
  - **Agentic Coding CLI**：Agent 本身，如 Claude Code、Gemini CLI、Codex CLI
  - **開發工具 CLI**：Agent 呼叫的工具，如 `git`、`node`、`firebase`
- **範例**：

```bash
git commit -m "Add login page"
firebase deploy --only hosting
```

---

### 介紹 MCP (Model Context Protocol)

<hr>

- **定義**：連接 AI 與外部工具、資料的開放標準協定
- **類比**：如同 AI 的「USB 接口」，一次規格，到處可接
- **運作方式**：MCP Server 提供工具與資料，Agent 作為 Client 呼叫
- **應用範例**：
  - 查詢 Firebase 專案與 Firestore 資料
  - 讀取 Figma、Google Stitch 的設計稿
  - 存取 Google Drive、GitHub、資料庫
- **注意**：MCP 會授權 Agent 操作外部資料，需確認權限範圍

---

### 介紹 Skill

<hr>

- **定義**：以 Markdown 撰寫的指引（`SKILL.md`），封裝特定任務的做法
- **運作方式**：Agent 依任務需求，才載入對應的 Skill，節省上下文
- **內容**：任務說明、步驟、慣例，可附帶範本與腳本
- **優點**：
  - 可重複使用、可分享給團隊
  - 讓 Agent 的產出風格穩定一致
- **範例**：後面會介紹的 `grill-me`，在動手寫程式前先追問釐清需求

---

### CLI、MCP、Skill 比較

<hr>

| | CLI | MCP | Skill |
|---|---|---|---|
| **提供什麼** | 可執行的指令 | 外部服務的連線與工具 | 做事的流程與知識 |
| **形式** | 命令列程式 | 標準協定的 Server | Markdown 檔案 |
| **解決問題** | Agent 能「做」 | Agent 能「連接」 | Agent 知道「怎麼做」 |
| **範例** | `git`、`firebase` | Firebase、Figma MCP | `grill-me` |

---

<!-- _class: section-page -->

<span class="num">02</span>

## OpenCode

<hr>

---

<!-- _class: stats -->

### 什麼是 OpenCode？

<hr>

<div class="stat-wrap">
<div class="stat">

#### 開源的終端機 Agent
<hr>

在命令列中運行的 AI 程式開發代理，開放原始碼、可自由使用。

</div>
<div class="stat hi">

#### 不綁定單一模型
<hr>

可連接多家模型供應商（如 Anthropic、OpenAI、Google），也能使用本地模型。

</div>
<div class="stat">

#### 支援 MCP 與 Skill
<hr>

可擴充外部工具，並以設定檔管理專案規則。

</div>
</div>

---

### OpenCode 的特色

<hr>

- **終端機介面 (TUI)**：直接在專案資料夾中對話，Agent 可讀寫檔案、執行指令
- **Plan / Build 模式**：Plan 只分析規劃、不改檔案；Build 才實際修改程式
- **模型自由切換**：同一個工具，依成本與需求更換模型
- **專案規則檔**：`AGENTS.md` 記錄專案慣例，Agent 每次啟動都會參考
- **與 Claude Code 定位相近**：同屬 Agentic Coding CLI，操作概念可互通

---

### OpenCode 安裝與基本使用

<hr>

```bash
# 安裝（需先安裝 Node.js）
npm install -g opencode-ai

# 進入專案資料夾後啟動
cd my-spa-project
opencode
```

- `/connect`：連接模型供應商並登入／設定金鑰
- `/models`：選擇要使用的模型
- `/init`：分析專案並產生 `AGENTS.md`
- `Tab`：在 Plan 與 Build 模式間切換

---

<!-- _class: stats -->

### 什麼是 OpenRouter？

<hr>

<div class="stat-wrap">
<div class="stat">

#### 統一的模型入口
<hr>

一個平台、一組 API Key，即可呼叫來自多家供應商的上百種模型。

</div>
<div class="stat hi">

#### 相容 OpenAI API 格式
<hr>

多數工具只需更換 Base URL 與金鑰，就能切換模型。

</div>
<div class="stat">

#### 集中計費與管理
<hr>

預付額度、統一帳單，可查看各模型的用量與費用。

</div>
</div>

---

### 為什麼 Agentic Coding 需要 OpenRouter？

<hr>

- **不必逐一註冊**：不用分別申請 Anthropic、OpenAI、Google 等帳號與金鑰
- **自由比較模型**：同一個工具中，依任務換用不同模型，比較品質與價格
- **有免費模型可試用**：部分模型提供免費額度，適合課堂練習
- **容錯與備援**：某供應商不穩定時，可自動改走其他路徑
- **控管成本**：設定額度上限，避免 Agent 大量呼叫造成超支

> 注意：Agent 會大量消耗 token，請妥善保管 API Key，勿上傳至 GitHub。

---

### 在 OpenCode 使用 OpenRouter

<hr>

1. 到 openrouter.ai 註冊帳號，並儲值或選用免費模型
2. 建立 **API Key**
3. 啟動 OpenCode，輸入 `/connect`，選擇 **OpenRouter**
4. 貼上 API Key
5. 輸入 `/models`，選擇要使用的模型

---

<!-- _class: stats -->

### 開發環境：git、Node.js、Python

<hr>

<div class="stat-wrap">
<div class="stat">

#### git
<hr>

版本控制工具，記錄每次修改，可隨時回到先前版本。Agent 改壞程式時，靠它還原。

</div>
<div class="stat hi">

#### Node.js
<hr>

讓 JavaScript 能在瀏覽器之外執行，並提供 npm 套件管理。React 專案與許多 CLI 都需要它。

</div>
<div class="stat">

#### Python
<hr>

語法簡潔的通用程式語言，AI 與資料處理的常用工具。部分 Agent 工具與腳本需要它。

</div>
</div>

---

<!-- _class: cols -->

### Matt Pocock Skills 與 Superpowers：兩套 Skill 的取向

<hr>

<div class="col-wrap">
<div class="col">

#### Matt Pocock Skills（以 grill-me 為代表）

- **定位**：小型、可組合的 Skill 集合，可自行挑選、修改。
- **流程**：grill-me → to-spec → to-tickets → implement (TDD) → code-review。
- **做法**：由你手動輸入指令，一站一站推進，每站都能檢視與調整。
- **解決問題**：Agent 做出的東西和你想要的不一樣（認知落差）。

</div>
<div class="col alt">

#### Superpowers

- **定位**：完整的軟體開發方法論與 Skill 框架。
- **流程**：brainstorming → writing-plans → 子 Agent 實作與互相審查 → TDD → code review。
- **做法**：Skill 自動觸發，先確認設計，之後 Agent 可自主運作較長時間。
- **解決問題**：避免 Agent 一開始就亂寫程式，並自動走完整個開發流程。

</div>
</div>

---

### Matt Pocock Skills 與 Superpowers 比較

<hr>

| | Matt Pocock Skills | Superpowers |
|---|---|---|
| **設計理念** | 小而可組合，挑需要的用 | 完整框架，整套一起用 |
| **觸發方式** | 以手動指令為主（如 `/grill-me`），部分由模型判斷 | 自動觸發 |
| **需求釐清** | `grill-me`：一次一題、附建議答案；`grill-with-docs` 另產出名詞表與 ADR | `brainstorming`：釐清意圖後分段呈現設計請你核准 |
| **規劃拆解** | `to-spec`、`to-tickets`：依使用者功能垂直切片 | `writing-plans`：拆成含檔案路徑與驗證步驟的小任務 |
| **實作與審查** | `implement` (TDD)、`code-review` | 子 Agent 實作並互相審查、TDD、`requesting-code-review` |
| **人的角色** | 每一站都親自把關 | 核准設計後，多由 Agent 自主執行 |
| **學習成本** | 低，可從 `grill-me` 單一指令開始 | 較高，需熟悉整套流程 |

> 兩者都先釐清需求再動工；差別在於前者由你逐站掌控，後者自動化程度高。本課程從 `grill-me` 入手：輕量，且重點是學會「先把需求講清楚」。

---

### grill-me 的運作規則

<hr>

動工前，讓 AI 反過來訪問你，把計畫想清楚。核心規則只有幾條：

- **決策樹**：把計畫視為決策樹，逐一走訪每個分支與邊界情況
- **一次一題**：等你回答後再問下一題
- **能查就不問**：可從程式碼或檔案查到的事，AI 自己查
- **附建議答案**：每題都附 AI 的建議與理由，你以「審查提案」的方式決策
- **先不寫程式**：共識達成前，不做任何修改

> 用法：在專案資料夾啟動 Agent，輸入 `/grill-me` 並簡述想做的 SPA，逐題回答即可。

---

### grill-me 之後：完整開發流程

<hr>

grill-me 是起點，可再串接 mattpocock/skills 的其他指令：

1. **grill-with-docs**：拷問時同步產出名詞表與架構決策紀錄 (ADR)
2. **to-spec**：把共識寫成規格書
3. **to-tickets**：依「使用者功能」垂直切片拆成可獨立驗收的任務
4. **implement**：以 TDD 實作，先寫測試再寫功能，避免 AI 寫出配合錯誤結果的假測試
5. **code-review**：以平行子代理檢查專案規範與是否忠實實現規格

> 本課程以 grill-me 為主；寫程式時可改用 grill-with-docs。

---

### 範例：用 grill-me 規劃一個 SPA

<hr>

> **你**：`/grill-me` 我想做一個班級相簿網站。
>
> **Agent**：誰可以上傳照片？需要登入嗎？
> **你**：只有老師能上傳，同學可瀏覽。
>
> **Agent**：照片要如何分類？以活動、日期，還是標籤？
> **你**：以活動分類。
>
> **Agent**：資料存放在哪裡？是否需要即時更新？

- 過程中逐步釐清**使用者角色、資料結構、頁面、驗證方式**
- 這些答案，正是後續 Firestore、Auth 設計的依據

---

<!-- _class: section-page -->

<span class="num">03</span>

## 認識 Single Page Application

<hr>

---

<!-- _class: stats -->

### 什麼是 Single Page Application (SPA)？

<hr>

<div class="stat-wrap">
<div class="stat">

#### 單一 HTML 頁面
<hr>

只載入一次 HTML、CSS 與 JavaScript，之後不再整頁重新載入。

</div>
<div class="stat hi">

#### 動態更新內容
<hr>

使用者操作時，由 JavaScript 向後端取得資料，只更新畫面需要變動的部分。

</div>
<div class="stat">

#### 接近原生 App 體驗
<hr>

切換頁面流暢、無白畫面閃爍，操作回應快速。

</div>
</div>

---

<!-- _class: cols -->

### 靜態網頁 vs. SPA：不一樣在哪？

<hr>

| | 靜態網頁 (Static Web Page) | SPA |
|---|---|---|
| **內容來源** | 寫死在 HTML 檔案中 | 執行時由 API 動態取得資料 |
| **互動性** | 僅能瀏覽、點連結換頁 | 可登入、新增、修改、刪除資料 |
| **換頁方式** | 每個頁面是獨立 `.html` 檔 | 同一頁內由 JavaScript 切換畫面 |
| **資料更新** | 需手動修改檔案並重新上傳 | 即時從資料庫讀寫，畫面自動更新 |
| **適合情境** | 公司簡介、說明文件、部落格 | 管理系統、訂單、相簿等應用程式 |

> 兩者都可部署在靜態主機（如 Firebase Hosting）；差別在於 SPA 的畫面由 JavaScript 動態產生，並連接後端服務。

---

<!-- _class: cols -->

### 傳統多頁式網站 vs. SPA

<hr>

<div class="col-wrap">
<div class="col">

#### 多頁式 (MPA)

- **換頁方式**：每次點擊連結，瀏覽器向伺服器請求並載入完整新頁面。
- **畫面渲染**：由伺服器產生 HTML（如 PHP、JSP）。
- **特色**：SEO 容易、架構單純，但換頁有等待與閃爍。

</div>
<div class="col alt">

#### 單頁式 (SPA)

- **換頁方式**：由前端路由切換畫面，網址改變但頁面不重新載入。
- **畫面渲染**：瀏覽器端以 JavaScript 產生畫面，透過 API 交換 JSON 資料。
- **特色**：體驗流暢、前後端分離，但首次載入較重、SEO 需額外處理。

</div>
</div>

---

### SPA 的運作流程

<hr>

1. 瀏覽器第一次請求，伺服器回傳 `index.html` 與 JavaScript 程式包
2. JavaScript 啟動，由**前端路由 (Router)** 決定顯示哪個畫面
3. 需要資料時，以 `fetch` 呼叫 API，取得 **JSON**
4. 依資料更新 DOM，**不重新載入整頁**
5. 使用者切換功能，只重複步驟 2–4

---

<!-- _class: cols -->

### SPA 的優缺點

<hr>

<div class="col-wrap">
<div class="col">

#### 優點

- 操作流暢，使用者體驗佳
- 前後端分離，分工與維護容易
- 同一套 API 可供網頁、手機 App 共用
- 可搭配 PWA 打包成 App、支援離線

</div>
<div class="col alt">

#### 缺點

- 首次載入需下載較多 JavaScript
- 搜尋引擎最佳化 (SEO) 較困難
- 需處理瀏覽器上一頁、網址路由與狀態管理
- 禁用 JavaScript 時無法運作

</div>
</div>

---

### 常見 SPA 應用與技術

<hr>

- **應用案例**：Gmail、Google Maps、Trello、Notion、Figma
- **前端框架**：React、Vue、Angular、Svelte
- **本課程做法**：以 Firebase（Firestore、Auth、Hosting）作為後端，搭配 AI 輔助開發 (Agentic Coding) 完成 SPA
- **延伸**：將 SPA 封裝為 PWA，安裝到手機如同原生 App

---

<!-- _class: stats -->

### 什麼是 React？

<hr>

<div class="stat-wrap">
<div class="stat">

#### 建構使用者介面的函式庫
<hr>

由 Meta（原 Facebook）開發的開源 JavaScript 函式庫，是最普及的前端技術之一。

</div>
<div class="stat hi">

#### 元件化 (Component)
<hr>

把畫面拆成可重複使用的小零件，如按鈕、卡片、表單，再組合成完整頁面。

</div>
<div class="stat">

#### 資料驅動畫面
<hr>

資料（State）改變時，React 自動更新對應的畫面，不必手動操作 DOM。

</div>
</div>

---

### React 如何實現 SPA？

<hr>

- **元件 (Component)**：以函式描述一塊畫面，可重複使用與組合
- **JSX**：在 JavaScript 中以類似 HTML 的語法描述畫面
- **State**：元件內的資料，改變後畫面自動重新繪製
- **Router**：如 React Router，依網址切換元件，達成「換頁但不重載」
- **生態系**：搭配 Vite 建置專案，並可直接串接 Firebase

---

### React 程式碼範例

<hr>

```jsx
import { useState } from 'react'

function Counter() {
  const [count, setCount] = useState(0)

  return (
    <button onClick={() => setCount(count + 1)}>
      點擊次數：{count}
    </button>
  )
}
```

- `useState`：宣告 State，`setCount` 更新後畫面自動變化
- 沒有 `document.getElementById`，直接描述「畫面應該長什麼樣子」

---

### 為什麼選擇 React 開發 SPA？

<hr>

- **AI 熟悉度高**：資料與範例豐富，Agent 產生的 React 程式碼品質穩定
- **生態系完整**：UI 套件、路由、狀態管理皆有成熟選擇
- **與 Firebase 整合容易**：官方 SDK 與社群範例多
- **可延伸至行動端**：React Native、PWA 皆能沿用觀念
- **求職與社群資源多**：學習資源與職缺需求都高

---


安裝 CLI:
firebase

介紹 firestore 資料庫
介紹 firebase auth, hosting

介紹 由介面引導開發 google stitch

Package code into an App: PWA
