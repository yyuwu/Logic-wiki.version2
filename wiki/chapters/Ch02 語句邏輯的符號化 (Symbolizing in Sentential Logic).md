---
title: "Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)"
category: chapters
chapter: "Ch. 2"
source: "Ch_02_語句邏輯裡的符號化.docx / Hausman Ch. 2"
tags: [logic, chapter, sentential-logic, symbolization, truth-function, connectives]
updated: 2026-11-22
---

# Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)

> **對應原始講義**：`raw/Ch_02_語句邏輯裡的符號化.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 2)（輔）

本章進入**語句邏輯 (Sentential Logic, SL)**（又稱命題邏輯 Propositional Logic）。透過將自然語言中的原子語句與複合連接詞形式化，我們得以消除日常語言的歧義，並以**真值函應原則 (Principle of Truth-Functionality)** 嚴格定義五大邏輯連詞的語意。

---

## 1. 核心架構與知識節點

### 2-1 ~ 2-5 語法學、語意學與真值函應原則
- **語法學 (Syntax)** vs. **語意學 (Semantics)**（詳見 [[語法學與語意學的雙軌對稱架構 (Syntactic vs Semantic Dual Architecture in Logic)]]）：
  - **語法學**：規定哪些符號序列是合法的**完構式 (Well-Formed Formula, wff)**（Formation Rules）。
  - **語意學**：規定符號與真假值（T / F）之間的對應關係與真值條件（Truth Conditions）。
- **原子語句 (Atomic Sentences)** vs. **複合語句 (Compound Sentences)**：
  - 原子語句是不含任何其他語句作為構成部分的基本陳述句。
  - 複合語句是由一或多個原子語句透過語句連接詞（Sentential Connectives）組合而成的語句。
- **[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]**
  - **二值原則 (Principle of Bivalence)**：每個陳述句非真（T）即假（F）。
  - **真值函應原則 (Principle of Truth-Functionality)**：一個複合語句的真假值，**完全由其構成成分語句（Component Sentences）的真假值唯一決定**。
  - **非真值函應連接詞 (Non-Truth-Functional Connectives)**：日常語言中的「因為（because）」、「在……之前（before）」、「眾所周知（It is well known that）」、「某人相信 $p$」皆**不是**真值函應連接詞。因為即使固定成分語句的真值（例如 $p$ 為真），複合句仍可能有時為真、有時為假。
- **語句常元 (Sentence Constants)** vs. **語句變元 (Sentence Variables)**（詳見 [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]）：
  - **語句常元 ($A, B, C \dots$)**：代表特定的具體陳述句，具有確定的真假值（只對應真值表中的某一特定列）。
  - **語句變元 ($p, q, r \dots$)**：代表任意語句的空位（Placeholders），本身沒有真假值；由變元與連詞構成的式子稱為**語句形式 (Statement Form)**，語句形式才具有完整的 $2^n$ 列真值表。

### 2-3, 2-6, 2-9, 2-11, 2-12 五大真值函應邏輯連詞

| 邏輯連詞 | 本庫標準符號 | 常見替代符號 | 構成部分名稱 | 真值條件摘要 |
| :--- | :---: | :---: | :--- | :--- |
| **否定 (Negation)** | $\sim p$ | $\neg p, -p$ | — | $p$ 為 T 時 $\sim p$ 為 F；$p$ 為 F 時 $\sim p$ 為 T |
| **連言 / 合取 (Conjunction)** | $p \cdot q$ | $p \land q, p \& q$ | 連言因子 (Conjuncts) | 僅當 $p, q$ **皆為 T** 時為 T，其餘皆為 F |
| **選言 / 析取 (Disjunction)** | $p \lor q$ | — | 選言因子 (Disjuncts) | 相容選言（Inclusive Or）：僅當 $p, q$ **皆為 F** 時為 F，其餘皆為 T |
| **實質條件句 (Material Conditional)** | $p \supset q$ | $p \rightarrow q$ | 前件 (Antecedent) $p$<br>後件 (Consequent) $q$ | 僅當**前件 $p$ 為 T 且後件 $q$ 為 F** 時為 F；**當 $p$ 為 F 時恆為 T** |
| **實質雙條件句 (Material Biconditional)** | $p \equiv q$ | $p \leftrightarrow q$ | — | 當 $p, q$ **真值相同**（同為 T 或同為 F）時為 T，不同時為 F |

- **實質條件句 $p \supset q$ 的核心性質**：
  - 定義為 $\sim(p \cdot \sim q) \equiv \sim p \lor q$（保留日常條件句的**最小邏輯意義**：斷言「不會前件真而後件假」）。
  - **充分與必要條件**：在 $p \supset q$ 中，$p$ 是 $q$ 的**充分條件 (Sufficient Condition)**，$q$ 是 $p$ 的**必要條件 (Necessary Condition)**。

### 2-7 & 2-8 括弧、主要連接詞、使用與提及
- **括弧與主要連接詞 (Parentheses & Main Connective)**：
  - 如 $A \lor B \supset C$ 因具有歧義而不是合法完構式（wff），必須加括弧區分為 $(A \lor B) \supset C$（主要連接詞為 $\supset$）或 $A \lor (B \supset C)$（主要連接詞為 $\lor$）。
  - 否定號 $\sim$ 的管轄範圍（Scope）預設為緊隨其後的最短完整句式：$\sim A \lor B$ 代表 $(\sim A) \lor B$，主要連接詞為 $\lor$；而 $\sim(A \lor B)$ 的主要連接詞則是 $\sim$。
- **使用與提及 (Use vs. Mention)** & **對象語言與後設語言 (Object Language vs. Metalanguage)**（詳見 [[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]）：
  - **使用 (Use)**：直接用一個語詞指稱世界上的對象（例：`Paris is the capital of France.`）。
  - **提及 (Mention)**：加上引號指稱該語詞符號本身（例：`'Paris' has five letters.`）。
  - **對象語言 (Object Language)**：我們正在研究的形式語言（如 SL 符號系統）。
  - **後設語言 (Metalanguage)**：我們用來討論、定義對象語言的語言（如我們用繁體中文或英文搭配變元 $p, q$ 來討論 SL 的語法規則與真值表）。

### 2-10 & 2-13 四大高頻複合句型翻譯鐵律
1. **不會既 A 又 B (Not both A and B)**：$\sim(A \cdot B)$（等值於 $\sim A \lor \sim B$）。注意區分「兩者皆非 (Neither A nor B)」。
2. **既不 A 也不 B (Neither A nor B)**：$\sim A \cdot \sim B$ 或 $\sim(A \lor B)$。
3. **A 僅當 B / 只有 B 才 A (A only if B)**：$A \supset B$（或 $\sim B \supset \sim A$）。
   - **口訣**：「`if` 後接前件（充分條件），`only if` 後接後件（必要條件）」！
   - 對比：`A if B` 譯為 $B \supset A$；`A only if B` 譯為 $A \supset B$；`A if and only if B` 譯為 $(B \supset A) \cdot (A \supset B) \equiv (A \equiv B)$。
4. **A 除非 B / 除非 B 否則 A (A unless B)**：$\sim B \supset A$ 或 $A \lor B$。
5. **排斥選言 (Exclusive Or, $A \text{ xor } B$)**：$(A \lor B) \cdot \sim(A \cdot B)$ 或 $\sim(A \equiv B)$。

### 2-15 波蘭記號法 (Polish Notation)（原文書補充）
- 由波蘭邏輯學家盧卡謝維奇（Jan Łukasiewicz）發明，將連接詞置於運算元**前方（Prefix）**，完全不需要使用括弧即可消除歧義：
  - $N = \sim$, $K = \cdot$, $A = \lor$, $C = \supset$, $E = \equiv$
  - 例：$\sim(A \cdot B)$ 寫為 $NKab$；$(\sim A \cdot B)$ 寫為 $KNab$；$(A \supset B) \supset C$ 寫為 $CCabc$。

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **承接前章** | [[Ch01 邏輯導論 (Introduction to Logic)]] | 將 Ch.1 的自然語言論證轉化為 SL 的形式符號語言 |
| **深化概念** | [[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]] | 深入探討實質條件句怪論、真值表定義的證成、連言與選言的語用陷阱 |
| **深化概念** | [[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]] | 延伸探討對象語言 vs. 後設語言、使用 vs. 提及 |
| **向後延伸** | [[Ch03 真值表 (Truth Tables)]] | 利用 Ch.2 的五大連詞真值表，計算任意複雜複合語句與論證的真值 |
| **向後對比** | [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] | 比較 SL 的「Only if ($A \supset B$)」與 PL 的「Only A are B ($(x)(Bx \supset Ax)$)」之結構同構性 |
| **實戰練習** | [[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]] | 對應 Exercise 2-7 複合句符號化、Exercise 2-10 真值函應與 Lady Gaga 原子/複合句辨析 |
| **期中考真題** | [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]] | 對應期中考是非題 (1) 反事實條件句與實質條件句、(2) 否定句語法定義 |
