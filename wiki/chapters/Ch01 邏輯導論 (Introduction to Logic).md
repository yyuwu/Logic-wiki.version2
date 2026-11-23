---
title: "Ch01 邏輯導論 (Introduction to Logic)"
category: chapters
chapter: "Ch. 1"
source: "Ch_01_導論.docx / Hausman Ch. 1"
tags: [logic, chapter, argument, validity, soundness, consistency]
updated: 2026-11-22
---

# Ch01 邏輯導論 (Introduction to Logic)

> **對應原始講義**：`raw/Ch_01_導論.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 1)（輔）

本章奠定形式邏輯（Formal Logic）的基礎分析單位與核心評價判準，區分日常語言中「說服他人的論證」與「解釋原因的說明」，並釐清真假值（Truth-values）、有效性（Validity）、健全性（Soundness）與一致性（Consistency）四大後設概念的嚴格關係。

---

## 1. 核心架構與知識節點

### 1-1 論證的構成要素 (The Elements of an Argument)
- **[[論證與解釋 (Argument vs Explanation)]]**
  - **陳述句 (Statement)**：具有真假值（Truth-value: True `T` / False `F`）的語句（Sentence）。疑問句、命令句、感嘆句在字面上通常不是陳述句，但須依實際語境脈絡（Context）判定（例如主管問「誰是這裡的老大？」實質上是在做陳述）。
  - **論證 (Argument)**：由一系列陳述句所構成的語句集合，其中一個陳述句稱為**結論 (Conclusion)**（通常以 $\therefore$ 標示），其餘陳述句稱為**前提 (Premises)**，旨在提供理據（Reasons）以支持結論為真。
  - **指示詞 (Indicators)**：
    - **前提指示詞**：因為（since, because）、既然、由於、鑑於（for, as, given that）。
    - **結論指示詞**：所以（therefore, thus）、因此（hence, consequently）、由此可見（it follows that）。
  - **關鍵辨析：理由證成 (Justification) vs. 因果說明 (Causal / Genetic Explanation)**
    - 「$Q$，因為 $P$」在日常語言中具有歧義：
      - **因果解釋 (Explanation)**：說話者與聽者**已預設結果 $Q$ 為真**，提出 $P$ 是為了說明 $Q$ 發生的物理或心理原因（例：「新竹風很大，因為新竹三面環山一面臨海」、「小珍很氣他，因為他撞壞了她的車」）。
      - **論證 (Argument)**：結果 $Q$ 是否為真尚有爭議或待確立，說話者提出 $P$ 作為理據來說服聽者接受 $Q$（例：「小珍**應該**很氣他，因為他撞壞了她的車」、「我們應該限制溫室氣體排放，因為它正在破壞大氣臭氧層」）。

### 1-2 & 1-3 演繹與歸納 (Deduction and Induction) 及論證形式
- **[[有效性與健全性 (Validity and Soundness)]]**
  - **演繹有效論證 (Deductively Valid Argument)**：
    - **肯定表述**：若所有前提皆為真，結論**必然 (Necessarily)** 為真。
    - **否定表述**：**邏輯上不可能 (Logically Impossible)** 所有前提皆為真而結論為假。
    - **核心特質**：演繹有效性完全取決於**[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]**（例如選言三段論 $p \lor q, \sim p / \therefore q$ 或肯定前件律 $p \supset q, p / \therefore q$），與前提或結論在現實世界中的經驗真假無關；且結論的訊息已經隱含（Implicitly Contained）在前提之中。
  - **歸納強論證 (Inductively Strong Argument)**：
    - 結論的內容**超出**前提所包含的訊息（可擴展經驗新知），當所有前提為真時，依機率（Probability）提供強而有力的理由使結論**很可能 (Probably)** 為真，但邏輯上仍有可能前提皆真而結論為假（例：過去太陽每天升起 $\therefore$ 明天太陽也會升起；George Lucas 前幾部電影很賣座 $\therefore$ 下一部也會賣座）。

### 1-4 & 1-5 真值、有效性與健全性 (Truth, Validity, and Soundness)
- **範疇區分**：
  - **真與假 (True / False)** 是單一**陳述句 (Statements)** 的性質。
  - **有效與無效 (Valid / Invalid)**、**健全與不健全 (Sound / Unsound)** 是整個**論證 (Arguments)** 的性質。
- **真值與有效性的 8 種組合**：
  - 唯一在邏輯上**絕對不可能出現**的組合：**「論證有效 + 前提皆為真 + 結論為假」**。
  - 其餘 7 種組合皆可能出現！特別注意：**無效論證可以擁有全真的前提與為真的結論**（例：「華盛頓橫渡德拉瓦河 $\therefore$ 花椰菜是蔬菜」或肯定後件謬誤）。
- **健全論證 (Sound Argument)**：
  $$\text{Sound Argument} \iff \text{(1) 論證在形式上有效 (Valid)} \land \text{(2) 所有前提在事實上皆為真 (All Premises are Actually True)}$$

### 1-6 & 1-7 一致性與反例集 (Consistency and Counterexample Set)
- **[[一致性與反例集 (Consistency and Counterexample Set)]]**
  - **一致 (Consistent)**：一組陳述句在邏輯上有可能**同時為真**。
  - **不一致 (Inconsistent)**：一組陳述句在邏輯上**不可能同時為真**（隱含矛盾，如甘迺迪品格高尚卻又背叛婚姻的語句集合，或理髮師悖論 Barber Paradox）。
  - **有效性與一致性的雙向核心定理**：
    > 一個論證 $P_1, P_2, \dots, P_n / \therefore C$ 是**有效的 (Valid)**，若且唯若它的**反例集 (Counterexample Set)** $\{P_1, P_2, \dots, P_n, \sim C\}$ 是**不一致的 (Inconsistent)**。
  - 這一定理構成了後續 [[Ch03 真值表 (Truth Tables)]] 中的 [[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]] 以及 [[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]] 中**間接證法 (Indirect Proof, IP)** 的理論基石。

### 1-8 發現的脈絡與證成的脈絡 (Contexts of Discovery and Justification)
- **發現的脈絡 (Context of Discovery)**：一個人如何想到某個假說或結論的心理、歷史或偶然過程（例如牛頓被蘋果砸到而想到萬有引力、凱庫勒夢見蛇咬尾巴而想到苯環結構），屬於心理學、歷史學或社會學範疇。
- **證成的脈絡 (Context of Justification)**：提出什麼樣的證據、前提與邏輯推論來支持或檢驗該結論，這才是**邏輯學唯一關心的範疇**。

### 附錄：模態邏輯符號補充 (Modal Logic Notation)
- 必然性算子 $\Box p$（Necessarily $p$）與可能性算子 $\Diamond p$（Possibly $p$）：
  $$\Box p := \sim \Diamond \sim p \quad (\text{必然 } p \equiv \text{不可能非 } p)$$
- 演繹有效性的模態表達（前提連言為 $P$，結論為 $Q$）：
  $$\sim \Diamond (P \cdot \sim Q) \equiv \Box(P \supset Q)$$

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **深化概念** | [[論證與解釋 (Argument vs Explanation)]] | 深入剖析前提/結論指示詞、理由證成 vs. 因果解釋、發現脈絡 vs. 證成脈絡 |
| **深化概念** | [[有效性與健全性 (Validity and Soundness)]] | 完整列出「前提真假 × 結論真假 × 有效/無效」8 種組合矩陣與典型實例 |
| **深化概念** | [[一致性與反例集 (Consistency and Counterexample Set)]] | 建立「論證有效 $\iff$ 反例集不一致」橋樑，串聯語意檢驗與語法歸謬法 |
| **向後延伸** | [[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]] | 將 Ch.1 的自然語言陳述句形式化為原子語句與真值函應複合語句 |
| **向後延伸** | [[Ch03 真值表 (Truth Tables)]] | 用真值表機械化檢驗 Ch.1 所定義的有效性、一致性與反例集 |
| **實戰練習** | [[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]] | 對應 Ch.1 論證 vs. 因果解釋辨識題、Exercise 1-3 真值與有效性判斷題（十八尖山與新竹貢丸米粉例） |
| **期中考真題** | [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]] | 對應期中考是非題 (4), (5), (8), (9) 一致性、健全性與單調性考題 |
