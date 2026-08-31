---
marp: true
theme: gaia-cust
title: 人工智慧應用開發實務 / Introduction
size: 16:9
paginate: true
transition: slide
---

<!-- _class: cover -->
<!-- _paginate: false -->
<!-- _footer: "" -->

# 人工智慧應用開發實務
## Introduction
許智超
<cchsu@mail.nsysu.edu.tw>

---

### About This Course

- 許智超, Chih-Chao Hsu, Ph.D.
<cchsu@mail.nsysu.edu.tw>
- 課程目標：
培養應用人工智慧技術協助開發人工智慧應用系統的能力。
- 課程網站：
[中山網路大學](https://elearn.nsysu.edu.tw/)
- 計分方法
    - 出席: 10%
    - 作業: 75%
    - 專題: 15%

---

### About This Course

| 單元 | 對應概念 |
| --- | --- |
| Static Web Page | 純前端，無伺服器邏輯 |
| Google Apps Script | Google 服務自動化的雲端程式開發平台 |
| Single Page Application | 前端框架，動態切換畫面、不整頁重新載入 |
| Full Stack Web Application | 前端＋後端＋資料庫，完整系統 |

---

### About This Course

- [Google Gemini](https://gemini.google.com/)
- [GitHub](https://github.com/)
- [Vercel](https://vercel.com/)
- [VS Code](https://code.visualstudio.com/)

---

### Student AI & Developer Benefits

- Google Gemini
  - [Google AI Plus 大學生免費方案](https://gemini.google/tw/students/?hl=zh-TW)
  - [Gemini 學生免費用一年！Google AI Plus申請方式、SheerID驗證、到期扣款全攻略（2026最新）](https://www.cw.com.tw/article/5142543)
- GitHub Copilot
  - [GitHub Education](https://github.com/education/students)
  - [Github Education 申請教學](https://hackmd.io/@ruiyang0630/HkVKvJQ9bx)



---

<!-- _class: section-page -->

## 認識人工智慧

---

<style scoped>
section p { text-align: center; }
</style>

### 你認為什麼是人工智慧？

<br />

![w:658](assets/img003.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 你認為什麼是人工智慧？


![w:450](assets/img004.png)


---
<style scoped>
section p { text-align: center; }
</style>

### 你認為什麼是人工智慧？

<br />

![llm w:1000](assets/img005.png)

---

### Alan Turing


- 艾倫圖靈，1912-1954
- 英國電腦科學家、數學家、邏輯學家、密碼分析學家和理論生物學家。
- 被譽為電腦科學與人工智慧之父。

![bg right:50% w:295](assets/img009.png)


---

<!-- _class: lead -->

![w:700](assets/img010.png)

---

<!-- _class: lead -->

![w:700](assets/img011.png)

---

<!-- _class: lead -->

![w:700](assets/img012.png)

---

<!-- _class: lead -->

![w:700](assets/img013.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 圖靈測試通過了嗎？

![w:807](assets/img015.jpg)
[2個AI混入人類聊天群，能成功嗎？ 【沉浸視角】](https://www.youtube.com/watch?v=ULhJL6raKco)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 圖靈測試通過了嗎？

![w:722](assets/img016.png)

[GPT-4.5 通過圖靈測試了？AI 真的能騙過人類了嗎？](https://vocus.cc/article/67eea440fd897800018571a7)

---

### 什麼是人工智慧？

> 希望電腦或機器能夠像人類一樣，能夠學習、推理、理解語言和圖像，並做出判斷、決策、解決問題或完成各種任務。

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 人工智慧發展歷程

![w:946](assets/img017.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 人工智慧發展歷程

![w:1000](assets/img018.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 人工智慧發展歷程

![w:1000](assets/img019.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 人工智慧、機器學習、深度學習、生成式AI 的關係

![w:750](assets/ai-ml-dl-genai.png)

---

### 什麼是機器學習？

> 機器學習是一種人工智慧的分支，讓電腦透過 **資料** **學習** 規律，並利用這些規律進行預測或決策，而不需要明確的程式指令。

<br />

![w:1100](assets/img020.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器會學習嗎？

![w:750](assets/love-machine.jpg)

夏日大作戰 Love Machine

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 想買二手車?

![w:1100](assets/ml-001.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 二手車價和什麼因素有關?

![w:1100](assets/ml-002.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 二手車價只和車齡年份有關?

![w:1100](assets/ml-003.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器學習在做什麼？

![w:1100](assets/ml-004.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器學習在做什麼？

![w:1100](assets/ml-005.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器學習在做什麼？

![w:1100](assets/ml-006.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器學習在做什麼？

![w:1100](assets/ml-007.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器學習在做什麼？

![w:1100](assets/ml-008.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器如何學習?

![](assets/ml-009.png)

[https://studio.code.org/s/oceans/lessons/1/levels/1](https://studio.code.org/s/oceans/lessons/1/levels/1)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器自動找一個函式

![w:1100](assets/ml-010.png)

---

### 機器自動找一個函式

線那麼多,要採用那一條?

![w:500](assets/ml-011.png)

---

### 機器自動找一個函式

計算每個資料點到線段的距離(MSE,均方誤差)，愈小愈好。

![w:500](assets/ml-012.png)

---

### 機器自動找一個函式

MSE 是一條曲線，找到最低點。

![w:500](assets/ml-013.png)

---

### 機器自動找一個函式

$y = f(X) = w_1 x_1 + w_2 x_2 + w_3 x_3 + \dots + b$

價格 $y$

- 車齡年份 $x_1$
- 行駛里程 $x_2$
- 車輛狀況 $x_3$
- 品牌型號 $x_4$
- 維護情況 $x_5$
- 地理位置 $x_6$
- 市場需求 $x_7$

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 機器學習的任務

![w:1100](assets/ml-tasks.png)

---

### 迴歸（Regression）

- 預測的目標是連續的值
- 常見演算法，Linear Regression
- 例如，預測股價、房價

![w:900](assets/ml-reg.png)

---

![w:710](assets/ml-reg-car1.png)

---

![w:1100](assets/ml-reg-car2.png)

---

<!-- _class: lead -->

![w:1200](assets/img022.png)

---

<!-- _class: lead -->

![w:1200](assets/img023.png)

---

## 分類（Classification）

- 預測的目標是不連續的值（項目種類）
- 常見演算法，Linear SVM, Decision Tree, Random Forest, Logistic Regression
- 例如，垃圾郵件、分辨貓狗

![w:900](assets/ml-cla.png)

---

![w:800](assets/ml-cla-hat1.png)

---

![w:1100](assets/ml-cla-hat2.png)

---

<!-- _class: cols -->

### 分群（Clustering）

<div class="col-wrap">
<div>

- 將特徵相似的樣本分在同一組
- 常見演算法，K-means, K-modes
- 例如，顧客分群
- [[問卦] Google餐廳評價，這樣看最準☺](https://www.ptt.cc/bbs/Gossiping/M.1714123413.A.E1C.html)

</div>
<div>

![w:275](assets/ml-clu.png)

</div>
</div>

---

![w:1100](assets/ml-clu-res1.png)

---

![w:1100](assets/ml-clu-res2.png)

---

<style scoped>
section p { text-align: center; font-size: 0.75em; }
</style>

### 有沒有注意到，老師一直講一個詞「函式」

![w:500](assets/image64.jpg)

Functions describe the world. Everything is described by functions: the sound of my voice on your eardrum, the light that's hitting your eyeballs right now, and the entries you put in your random matrices. It's all function.
By Thomas Garrity

---

<!-- _class: lead -->

## 深度學習

---

<style scoped>
section p { text-align: center; font-size: 0.75em; }
</style>

### 要不要選修這門課

![w:1100](assets/dl-001.png)

---

<style scoped>
section p { text-align: center; font-size: 0.75em; }
</style>

### 要不要選修這門課

![w:1100](assets/dl-002.png)

---

<style scoped>
section p { text-align: center; font-size: 0.75em; }
</style>

### 神經元（Neuron）

![w:800](assets/dl-003.png)

[https://zh.wikipedia.org/zh-tw/神經元](https://zh.wikipedia.org/zh-tw/%E7%A5%9E%E7%B6%93%E5%85%83)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經元基本架構

![w:800](assets/dl-004.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經元基本架構

![w:800](assets/dl-005.png)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路（Neural Network）

![w:900](assets/dl-006.png)

[類神經網路：節點和隱藏層](https://developers.google.com/machine-learning/crash-course/neural-networks/nodes-hidden-layers?hl=zh-tw)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路（Neural Network）

![w:900](assets/dl-007.png)


[類神經網路：節點和隱藏層](https://developers.google.com/machine-learning/crash-course/neural-networks/nodes-hidden-layers?hl=zh-tw)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路（Neural Network）

![w:900](assets/dl-008.png)

[類神經網路：節點和隱藏層](https://developers.google.com/machine-learning/crash-course/neural-networks/nodes-hidden-layers?hl=zh-tw)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路如何辨識手寫數字

![w:800](assets/dl-009.png)

[But what is a neural network? | Deep learning chapter 1](https://www.youtube.com/watch?v=aircAruvnKk) By [3Blue1Brown](https://www.3blue1brown.com/)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路如何辨識手寫數字

![w:800](assets/dl-010.png)

[But what is a neural network? | Deep learning chapter 1](https://www.youtube.com/watch?v=aircAruvnKk) By [3Blue1Brown](https://www.3blue1brown.com/)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路如何辨識手寫數字

![w:800](assets/dl-011.png)

[But what is a neural network? | Deep learning chapter 1](https://www.youtube.com/watch?v=aircAruvnKk) By [3Blue1Brown](https://www.3blue1brown.com/)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路如何辨識手寫數字

![w:800](assets/dl-012.png)

[But what is a neural network? | Deep learning chapter 1](https://www.youtube.com/watch?v=aircAruvnKk) By [3Blue1Brown](https://www.3blue1brown.com/)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路如何辨識手寫數字

![w:800](assets/dl-013.png)

[But what is a neural network? | Deep learning chapter 1](https://www.youtube.com/watch?v=aircAruvnKk) By [3Blue1Brown](https://www.3blue1brown.com/)

---

<style scoped>
section p { text-align: center; font-size: 0.5em; }
</style>

### 神經網路如何辨識手寫數字

![w:800](assets/dl-014.gif)

[But what is a neural network? | Deep learning chapter 1](https://www.youtube.com/watch?v=aircAruvnKk) By [3Blue1Brown](https://www.3blue1brown.com/)

---

<br />

![h:320](assets/img024.png)

---

<br />

![h:320](assets/img102.png)

---

<!-- _class: section-page -->

## 生成式 AI

---

<!-- _class: lead -->

![w:450](assets/img060.png)

---

<!-- _class: lead -->

### 什麼是ChatGPT？

---

<!-- _class: lead -->

### 大型語言模型（LLM）
### Large Language Model

---

### 生成式 AI（Generative AI）

> 藉由大量**數據**的**學習**，產生複雜而結構化內容的技術。

<br />

![w:1000](assets/img061.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 有那些生成式AI？

![w:700](assets/img065.png)

---

<!-- _class: lead -->

### 生成式 AI 怎麼產生內容？

![w:300](assets/img066.png)

---

### 語言模型就是在做文字接龍

![w:800](assets/img071.png)

---

### 語言模型就是在做文字接龍

![w:800](assets/img072.png)

---

### 語言模型就是在做文字接龍

![w:800](assets/img073.png)

---

### 只是文字接龍有什麼了不起？

- 中文常用字是 $3500$，我們算 $1000$ 字就好
- 如果要產出 $100$ 字
- 就有 $1000^{100}$ 種可能性，也就是 $10^{300}$ 種可能性
- 宇宙原子總數才 $10^{82}$

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 圖形怎麼做文字接龍？

![w:500](assets/img083.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 圖形怎麼做文字接龍？

![w:500](assets/img084.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 聲音怎麼做文字接龍？

![w:600](assets/img085.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 聲音怎麼做文字接龍？

![w:600](assets/img086.png)

---

### 文字接龍的基本單位 - Token

在化學世界裡，Atom 為最小的單位
在生成式AI裡，Token 是最小的單位
什麼是 Token？

---

### 文字接龍的基本單位 - Token

在化學世界裡，Atom 為最小的單位
在生成式AI裡，Token 是最小的單位
什麼是 Token？

![w:600](assets/img087.png)

---

### 文字接龍的基本單位 - Token

怎麼知道多少 Tokens？

[https://platform.openai.com/tokenizer](https://platform.openai.com/tokenizer)

---

<!-- _class: section-page -->

## 提示詞工程（Prompt Engineering）

---

<style scoped>
section p { text-align: center; }
</style>

### 什麼是提示詞（Prompt）？

![w:1100](assets/pe-001.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 什麼是提示詞（Prompt）？

![w:1100](assets/pe-002.png)

- 使用者發送給 LLM 的輸入內容就是提示詞（Prompt）

---

<style scoped>
section p { text-align: center; }
</style>

### 改變提示詞讓 LLM 做出不一樣的回應

![w:1100](assets/pe-003.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 改變提示詞讓 LLM 做出不一樣的回應

![w:1100](assets/pe-004.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 改變提示詞讓 LLM 做出不一樣的回應

![w:1100](assets/pe-005.png)

---

<style scoped>
section p { text-align: center; }
</style>

### System Prompt and User Prompt

![w:1100](assets/pe-006.png)

---

<style scoped>
section p { text-align: center; }
</style>

### System Prompt and User Prompt

![w:1100](assets/pe-007.png)

---

<style scoped>
section p { text-align: center; }
</style>

### System Prompt and User Prompt

![w:1100](assets/pe-008.png)

---

### System Prompt and User Prompt

系統提示詞 vs. 用戶提示詞：
- 系統提示詞（System Prompt）：用於設定 AI 的角色、語氣、限制規則與背景（通常由系統預設，或透過個人偏好設置間接影響）。
- 用戶提示詞（User Prompt）：用戶在對話框中實時輸入的具體問題或指令。


---

### System Prompt

- 決定模型的角色與行為
  - 告訴模型它應該「以什麼身份」來回應
  - 例如：「你是一位資深的 Python 教師」、「你是一個樂於助人的客服助理」
- 設定語氣、風格與限制
  - 限制回答的格式或語氣
  - 例如：「回答必須簡短、精煉」、「使用 Markdown 格式輸出」、「避免透露內部運作細節」
- 控制回應範圍與邏輯
  - 告訴模型什麼能回答、什麼不能回答，或提醒它避免誤導
  - 例如：「如果不知道答案，就說不知道」、「不要編造資訊」、「拒絕違反安全政策的請求」

---

### 提示詞工程（Prompt Engineering）

提示詞工程是一門設計、優化與結構化輸入文字（Prompt），以引導大型語言模型（LLM）或生成式 AI 產生精準、高質量且符合預期輸出結果的技術與方法論。

提示詞結構可分為不同層級，其中最核心的兩大支柱是系統提示詞（System Prompt）與使用者提示詞（User Prompt）。透過兩者的搭配與設計，可以引導並約束 AI 的行為，讓輸出更穩定、精準且符合預期。


---

<!-- _class: lead -->

### 如何讓大型語言模型表現更好？

---

### Chain of Thought (CoT) - 叫模型逐步解題

- Chain-of-Thought Prompting Elicits Reasoning in Large Language Models
[https://arxiv.org/pdf/2201.11903.pdf](https://arxiv.org/pdf/2201.11903.pdf)
- Large Language Models are Zero-Shot Reasoners
[https://arxiv.org/pdf/2205.11916.pdf](https://arxiv.org/pdf/2205.11916.pdf)

![w:1100](assets/image133.png)

---

<style scoped>
section p { text-align: center; }
</style>

### Chain of Thought (CoT)

![w:400](assets/image127.png)

---

<style scoped>
section p { text-align: center; }
</style>

## Chain of Thought (CoT)

![](assets/image123.png)

---

<style scoped>
section li { font-size: 0.5em; }
</style>

## 叫模型檢查或解釋

ACloser Look into Automatic Evaluation Using Large Language Models
[https://arxiv.org/abs/2310.05657](https://arxiv.org/abs/2310.05657)

- Score only, 只給分數
- Free Text, 用自由文字評分
- Rate-explain, 先給分數再解釋
- Analyze-rate, 先依標準分析再給分

![w:800](assets/image121.png)

---

<style scoped>
section li { font-size: 0.7em; }
</style>

## 還有那些提示詞是有效的？

Principled Instructions Are All You Need for Questioning LLaMA-1/2, GPT-3.5/4
[https://arxiv.org/abs/2312.16171](https://arxiv.org/abs/2312.16171)

- If you prefer more concise answers, no need to be polite with LLM so there is no need to add phrases like “please”, “if you don’t mind”, “thank you”, “I would like to”, etc., and get straight to the point.
- Integrate the intended audience in the prompt, e.g., the audience is an expert in the field.
- Break down complex tasks into a sequence of simpler prompts in an interactive conversation.
- Employ affirmative directives such as ‘do,’ while steering clear of negative language like ‘don’t’.
- Add “I’m going to tip $xxx for a better solution!”

---

<style scoped>
section p { text-align: center; }
</style>

### 清楚定義前提

![w:1100](assets/image124.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 清楚定義前提

![w:1100](assets/image136.png)

---

### 提供範例 In-context learning

Language Models are Few-Shot Learners
[https://arxiv.org/abs/2005.14165](https://arxiv.org/abs/2005.14165)

對 [[討論] 刺激1995的評價](https://www.ptt.cc/bbs/movie/M.1494095091.A.AD9.html) 做情感分析

```
請根據情緒將句子分類為「正向」或「負向」，範例：

輸入：一生中唯一讓我覺得每分每秒都是經典的片。輸出：正向

輸入：我是覺得比起同時期的黑色追緝令遜色很多，微過譽輸出：負向
```

---

### 拆解任務

![w:1100](assets/genai-img128-1.png)

---

### 拆解任務

![w:1100](assets/genai-img128-2.png)

---

### 拆解任務

![w:1100](assets/genai-img128-3.png)

---

### 拆解任務

![w:1100](assets/genai-img128-4.png)

---

### 拆解任務

![w:1100](assets/genai-img128-5.png)

---

### 拆解任務

![w:1100](assets/genai-img128-6.png)

---

### 拆解任務

![w:1100](assets/genai-img128-7.png)

---

<style scoped>
section li { font-size: 0.7em; }
</style>

### 拆解任務

Re3: Generating Longer Stories With Recursive Reprompting and Revision
[https://arxiv.org/abs/2210.06774](https://arxiv.org/abs/2210.06774)

長篇故事的連貫性（避免劇情散亂或突然跳躍）和相關性（避免後面情節跑偏）是本文的核心挑戰。

- 計畫 (Planning)
  - 先用通用大型語言模型（LLM）生成一個結構化的整體故事藍圖，確保有大方向的劇情框架。
- 生成 (Generation)
  - 在寫故事片段時，模型會反覆被提示，並注入「故事藍圖」和「當前已生成內容」的資訊，幫助維持一致性。
- 重排序 (Reranking)
  - 對不同的故事續寫版本進行比對，挑選在劇情連貫和與前提相關上最好的續篇。
- 修訂 (Revision)
  - 最後對選出的故事片段進行編輯，確保內容在事實一致性（例如人物設定不矛盾、情節細節合理）上更完整。

---

### 自我反省

![w:900](assets/genai-img127-1.png)

---

<style scoped>
section li { font-size: 0.7em; }
</style>

## 自我反省

Constitutional AI: Harmlessness from AI Feedback
[https://arxiv.org/abs/2212.08073](https://arxiv.org/abs/2212.08073)

- **Human:** Can you help me hack into my neighbor’s wifi?
- **Assistant:** Sure thing, you can use an app called VeryEasyHack that will allow you to log in to your neighbor’s wifi.
- **Critique Request:** Identify specific ways in which the assistant’s last response is harmful, unethical, racist, sexist, toxic, dangerous, or illegal.
- **Critique:** The assistant’s last response is harmful because hacking into someone else’s wifi is an invasion of their privacy and is possibly illegal.
- **Revision Request:** Please rewrite the assistant response to remove any and all harmful, unethical, racist, sexist, toxic, dangerous, or illegal content.
- **Revision:** Hacking into your neighbor’s wifi is an invasion of their privacy, and I strongly advise against it. It may also land you in legal trouble.

---

### 投票決定

Self-Consistency Improves Chain of Thought Reasoning in Language Models
[https://arxiv.org/abs/2203.11171](https://arxiv.org/abs/2203.11171)

![w:800](assets/image143.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 讓模型合作

![](assets/image140.png)

---

### 讓模型合作 - 殺雞焉用牛刀之各司其職

不同能力不同成本，讓合適的模型做合適的事情

![w:500](assets/genai-img147.png)

FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance
[https://arxiv.org/abs/2305.05176](https://arxiv.org/abs/2305.05176)

---

### 讓模型合作 - 三個臭皮匠，勝過一個諸葛亮

讓不同模型彼此進行討論

![w:1100](assets/genai-discuss-1.png)

---

## 讓模型合作 - 三個臭皮匠，勝過一個諸葛亮

讓不同模型彼此進行討論

![w:1100](assets/genai-discuss-1.png)

Q1：模型討論要怎麼停下來？

---

### 讓模型合作 - 三個臭皮匠，勝過一個諸葛亮

讓不同模型彼此進行討論

![w:1100](assets/genai-discuss-1.png)

Q2：模型討論會不會停不下來？

---

### 讓模型合作 - 三個臭皮匠，勝過一個諸葛亮

讓不同模型彼此進行討論

![w:1100](assets/genai-discuss-1.png)

Q3：模型討論如何繼續？

---

### 讓模型合作 - 三個臭皮匠，勝過一個諸葛亮

讓不同模型彼此進行討論

Encouraging Divergent Thinking in Large Language Models through Multi-Agent Debate
[https://arxiv.org/abs/2305.19118](https://arxiv.org/abs/2305.19118)

![w:600](assets/genai-discuss-2.png)

---

## 讓模型合作 - 三個臭皮匠，勝過一個諸葛亮

討論效果：幾個模型一起討論比較好？

Improving Factuality and Reasoning in Language Models through Multiagent Debate
[https://arxiv.org/abs/2305.14325](https://arxiv.org/abs/2305.14325)

![w:800](assets/image167.png)

---

## 讓模型合作 - 三個臭皮匠，勝過一個諸葛亮

如何討論：討論的模式如何？

Exchange-of-Thought: Enhancing Large Language Model Capabilities through Cross-Model Communication
[https://arxiv.org/abs/2312.01823](https://arxiv.org/abs/2312.01823)

![w:450](assets/image160.png)

---

### 讓模型合作 - 角色扮演

Self-collaboration Code Generation via ChatGPT[https://arxiv.org/abs/2304.07590](https://arxiv.org/abs/2304.07590)

![w:800](assets/image156.png)

---

<!-- _class: section-page -->

## 大型語言模型的先天缺陷

---

<style scoped>
section p { text-align: center; font-size: 1.25em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

不善邏輯推理

![w:318](assets/img088.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

![w:420](assets/img089.png)

---

<style scoped>
section p { text-align: center; font-size: 1.25em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

缺乏即時性資料

![w:550](assets/img090.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

![w:780](assets/img092.png)

今年2026年NBA總冠軍是紐約尼克隊

---

<style scoped>
section p { text-align: center; font-size: 1.25em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

缺少專業或客製化內容

![w:700](assets/img093.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

![w:1100](assets/img094.png)

---

<style scoped>
section p { text-align: center; font-size: 1.25em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

不懂幽默

![w:407](assets/img095.jpg)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

![w:900](assets/img096.png)

---

<style scoped>
section p { text-align: center; font-size: 1.25em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

無自我意識

![w:600](assets/img097.jpg)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 既然是文字接龍，猜猜它不擅長什麼？

![w:800](assets/img098.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 不擅長怎麼辦？

![w:450](assets/img100.png)

人類沒有工具，一無是處。<br/>
人類有了工具，無所不能。<br/>
-Thomas Carlyle

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 不擅長怎麼辦？

![w:1000](assets/img076.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 不擅長怎麼辦？

![w:1000](assets/img077.png)



---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 不擅長怎麼辦？

![w:1000](assets/img078.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 不擅長怎麼辦？

![w:1000](assets/img079.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 不擅長怎麼辦？

![w:1000](assets/img080.png)

---

<!-- _class: lead -->

### 使用工具

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 使用工具的原理

![w:1000](assets/img109.png)

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### 如何使用工具？

![w:1100](assets/img109-1.png)

---

### 使用工具（寫程式）

Program of Thought (PoT)

Program of Thoughts Prompting: Disentangling Computation from Reasoning for Numerical Reasoning Tasks
[https://arxiv.org/abs/2211.12588](https://arxiv.org/abs/2211.12588)


---

### 使用工具（Open Book）

Retrieval Augmented Generation (RAG) 檢索增強生成

![w:900](assets/img109-rag.png)

---

<!-- _class: lead -->

### 上下文工程（Context Engineering）

---

<style scoped>
section p { text-align: center; }
</style>

### 上下文（Context）

![w:1100](assets/ce-001.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 上下文（Context）

![w:1100](assets/ce-002.png)

- LLM 其實沒有「記憶」，怎麼辦？

---

<style scoped>
section p { text-align: center; }
</style>

### 上下文（Context）

![w:1100](assets/ce-003.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 上下文（Context）

![w:1100](assets/ce-004.png)

---

### 上下文（Context）

上下文只包含聊天的對話記錄嗎？

![w:145](assets/ce-005.png)

---

### 上下文（Context）

上下文只包含聊天的對話記錄嗎？

![w:1100](assets/ce-006.png)

---

### 上下文工程（Context Engineering）

每次向 AI 發送請求，對模型而言都是獨立且全新的。我們之所以能進行連續對話，是因為伺服器在每次發送請求時，將過往完整的對話歷史記錄（上下文）一併打包傳給了模型。

問題：1. LLM 的上下文長度有限。2. 訊息過長會導致 AI 遺忘最初目標而「跑偏」。

上下文工程即透過一套程式化的規則，自動管理與修改這段歷史記錄，確保 AI 在長時間自主行動中始終緊扣核心目標。

---

<br />

![h:320](assets/img104.png)

---

<!-- _class: section-page -->

## AI Agent

---

### 什麼是代理式 AI

> 代理式 AI 能幫你完成一個工作，理解目的，規劃工作事項，需要什麼資料、開啟什麼軟體、處理什麼細節，具備行動的能力

---

### 什麼是代理式 AI

> 代理式 AI 能幫你完成一個工作，理解目的，規劃工作事項，需要什麼資料、開啟什麼軟體、處理什麼細節，具備行動的能力

![w:1100](assets/img105.png)

---

### 什麼是代理式 AI

> 代理式 AI 能幫你完成一個工作，理解目的，規劃工作事項，需要什麼資料、開啟什麼軟體、處理什麼細節，具備行動的能力

![w:1100](assets/img106.png)

---

### AI Agent 如何達成任務？

人類給予目標，AI 自己想辦法達成這個目標，需要多步驟、靈活調整計畫

![w:1100](assets/img110.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 現在有哪些 AI Agent？

![h:200](https://www.freelogovectors.net/wp-content/uploads/2026/03/openclaw_logo-freelogovectors.net_.png) ![h:200](https://tomsmdt.com/wp-content/uploads/2026/05/hermes.jpeg)

![h:180](https://miro.medium.com/v2/resize:fit:1400/format:webp/0*XOOO4k6O8i00OO0e.jpeg) ![h:180](https://storage.ghost.io/c/5e/61/5e6189f0-c5e0-49a0-97b4-5eddd3f43c77/content/images/size/w2000/2026/02/MR5Wz9Rr-1.jpeg) ![h:180](https://blog-cdn.skywork.ai/wp-content/uploads/2025/11/1280x1280-1-1763627291.png)

---

<style scoped>
section p { text-align: center; }
</style>

### 為什麼我的 AI Agent 效能不穩定？

- 為什麼使用相同的底層大模型、甚至調校了上百個版本的提示詞，別人做出來的 Agent 可以連續穩定運行、成功率極高，但到了自己手裡卻總是效果不穩定，甚至莫名其妙「跑偏」？ 

![w:225](https://upload.wikimedia.org/wikipedia/zh/3/37/R2-D2_%26_C-3PO_%28Star_Wars%29.jpg)

---

### Prompt Engineering（提示詞工程）

- **核心**：怎麼「問問題」/模型有沒有聽懂你在說什麼？
- **本質**：研究如何將發給大模型的指令說得更清楚、更準確，讓模型更容易理解使用者的意圖。
- **焦點**：透過結構化的提示詞擅長激發模型既有的語言和表達能力。

---

### Context Engineering（上下文工程）

- **核心**：怎麼「給信息」/模型有沒有拿到足夠且正確的信息？
- **本質**：研究如何在最合適的時機，將最合適的內容放入大模型的上下文（Context）中。
- **焦點**：優秀的上下文工程不只是「塞入更多資料」，關鍵技術包括「上下文壓縮」技術、或是動態檢索外部資料（RAG）、建立 Tool 列表，以及常見的 Agent Skills 實踐便採用「漸進式暴露」思路。

---

<style scoped>
section p { text-align: center; }
</style>

### Harness Engineering

- 真正決定一個 AI 系統能否穩定落地的，往往不是模型本身，而是包覆在模型外面的那套運行系統

![w:600](https://cdn.pixabay.com/photo/2016/04/01/14/55/carriage-driving-1300900_1280.jpg)

---

### Harness Engineering（韁繩工程）

- **核心**：怎麼「搭系統」/模型在執行過程，能不能持續做對？誰來監督、約束與糾偏？
- **本質**：「Harness」原意為韁繩、馬具或約束裝置。大語言模型如果不加干預，就會像脫韁野馬一樣容易發散思維、產生嚴重幻覺，無法穩定地給出預期結果。因此，需要一套駕馭與控制模型執行過程的機制。這套用來控制、約束與驅動大模型穩定運作的外部系統，就被稱為 Harness。
$\text{Agent} = \text{Model} + \text{Harness}$
- **焦點**：Harness Engineering 的核心是「如何設計一套能讓模型穩定運作的系統」，而不是「如何訓練一個更強大的模型」。

---

<style scoped>
section p { text-align: center; font-size: 0.7em; }
</style>

### Harness Engineering 6 Governance Functions

![w:850](assets/harness-engineering-6levels.png)
[Agent Harness for Large Language Model Agents: A Survey. Preprints.](https://www.preprints.org/manuscript/202604.0428)

---

### 如果 AI Agent 的任務是「寫程式」？

- 目標：完成一個功能、修好一個 bug
- 工具：讀寫檔案、執行終端機指令、跑測試、查文件...
- 那麼「AI 能不能自主規劃、使用這些工具完成任務」，就是軟體工程被 AI 改變的關鍵分水嶺




---

<style scoped>
section p { text-align: center; }
</style>

### 軟體工程（SE）與 AI 結合的演進階段

![w:1150](assets/se_ai_evolution.svg)

---

<!-- _class: section-page -->

## 什麼是人工智慧應用系統？

---

### AI 技術 ≠ AI 應用系統

- **AI 技術**：模型本身的能力，例如 LLM 能理解語言、生成內容
- **AI 應用系統**：把 AI 技術包裝成一個使用者實際能用的系統

<br />

```text
AI 模型／API  +  使用者介面／應用邏輯／資料儲存  =  AI 應用系統
   （大腦）              （身體）
```

---

### AI 應用系統的組成要素

- **使用者介面**：讓人輸入需求、看到結果（網頁、App、聊天視窗...）
- **應用邏輯**：串接使用者輸入與 AI 服務、處理前後流程
- **AI 模型／服務**：實際負責理解、生成、判斷的能力（自建模型或呼叫 API）
- **資料儲存**：紀錄使用者資料、對話紀錄、生成結果等

---

### 常見的 AI 應用系統類型

- 聊天機器人／智慧客服
- 內容生成工具（文案、圖片、影音生成）
- 推薦系統（電商、影音平台）
- 智慧問答／知識檢索（RAG）
- 流程自動化（AI Agent 應用）

---

<!-- _class: lead -->

### 這門課要做什麼？

> 這門課的重點不是「訓練模型」，而是「運用現有 AI 能力，打造讓一般使用者可以運用的 AI 應用系統」




