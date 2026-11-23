---
title: "Ch03 真值表 (Truth Tables)"
category: chapters
chapter: "Ch. 3"
source: "Ch_03_真值表法.docx / Hausman Ch. 3"
tags: [logic, chapter, truth-table, tautology, contradiction, equivalence, short-truth-table]
updated: 2026-11-22
---

# Ch03 真值表 (Truth Tables)

> **對應原始講義**：`raw/Ch_03_真值表法.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 3)（輔）

本章建立語句邏輯（SL）的**語意學機械決定程序 (Semantic Decision Procedure)**。透過真值表（Truth Tables）與簡短真值表法（Short Truth Table Method），我們可以在有限步驟內100%判定任何 SL 語句是否為恆真句/矛盾句/適真句，以及任何 SL 論證是否有效、語句集合是否一致。

---

## 1. 核心架構與知識節點

### 3-1 計算真值 (Computing Truth-Values)
- **賦值 (Valuation, $V$)**：對原子語句指派真假值（如 $V(A) = T, V(B) = F$）。
- **由內而外計算法**：可採用**環狀法 (Loop Method)** 或**表列法 (Tabular Method)**，從最內層括弧的原子語句與否定號開始，逐層向外計算，最後得出**主要連接詞 (Main Connective)** 下方的真值，即為整句在該賦值下的真值。

### 3-2 邏輯形式與取代實例 (Logical Form & Substitution Instance)
- **[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]**
  - **取代實例 (Substitution Instance)**：將一個語句形式（Statement Form）中的變元以完構句代入，且**相同的變元在所有出現處必須以完全相同的語句一致取代 (Uniform Substitution)**。
  - **取代 (Substitution)** vs. **置換 (Replacement)**：
    - **取代**：語法操作，只能針對「語句變元 $p, q$」進行，且同一變元必須全句一致取代。
    - **置換**：根據邏輯等值關係（如 Ch.4 的 10 條等值規則），可針對具體語句中的「部分子句」進行，且不必全句一致置換。
  - **形式層級譜系**：
    - 任何語句皆是原子形式 $p$ 的取代實例。
    - **基本形式 (Basic Form)**：由語句的主要連接詞決定（如 $(A \cdot B) \supset \sim(A \lor B)$ 的基本形式為 $p \supset q$）。
    - **一對一邏輯形式 / 展開形式 (One-One / Expanded Logical Form)**：將所有相異原子語句對應相異變元、相同原子語句對應相同變元所得的最精細形式（如上例為 $(p \cdot q) \supset \sim(p \lor q)$）。
    - **鐵律**：語句的邏輯結構可以比其形式更複雜，但**絕對不能比其形式更簡單**（例如 $A$ 不是 $\sim\sim p$ 的取代實例）。

### 3-3 & 3-4 語句的語意分類、邏輯等值與邏輯蘊涵
- **三大語句語意分類**（由語句的「一對一邏輯形式」真值表決定）：
  1. **恆真句 / 套套邏輯 (Tautology, $\models \phi$)**：在一對一邏輯形式的真值表中，**每一列皆為 T**（例：$A \lor \sim A$、$A \supset (B \supset A)$）。
  2. **矛盾句 (Contradiction)**：在一對一邏輯形式的真值表中，**每一列皆為 F**（例：$A \cdot \sim A$）。恆真句的否定必為矛盾句，矛盾句的否定必為恆真句。
  3. **適真句 / 偶真句 (Contingent Sentence)**：真值表中**至少有一列為 T 且至少有一列為 F**（其真假取決於經驗世界的事實；所有原子語句皆為適真句）。
- **邏輯等值 (Logical Equivalence)**：兩語句 $X, Y$ 邏輯等值，若且唯若雙條件句 **$X \equiv Y$ 是恆真句**（在真值表每一列中，$X$ 與 $Y$ 的真值皆相同）。
- **邏輯蘊涵 (Logical Implication)**：語句 $X$ 邏輯蘊涵 $Y$，若且唯若條件句 **$X \supset Y$ 是恆真句**（沒有任何一列是 $X$ 為 T 而 $Y$ 為 F）。

### 3-5 ~ 3-7 真值表檢驗有效性與一致性
- **[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]**
  - 含有 $n$ 個相異原子語句的論證，完整真值表共有 $2^n$ 列。
  - **有效論證判定**：檢查每一列，若存在任何一列使得**所有前提皆為 T 且結論為 F**（稱為**反例列 Counterexample Row**），則論證**無效 (Invalid)**；若完全沒有此種列，則論證**有效 (Valid)**。
- **三大核心等價定理**（串聯 [[一致性與反例集 (Consistency and Counterexample Set)]]）：
  對於任意論證 $P_1, P_2, \dots, P_n / \therefore C$，以下三句話在邏輯上完全等價：
  1. 論證 $P_1, \dots, P_n / \therefore C$ 是**有效的 (Valid)**。
  2. 反例集 $\{P_1, \dots, P_n, \sim C\}$ 是**不一致的 (Inconsistent)**，即連言句 $(P_1 \cdot \dots \cdot P_n \cdot \sim C)$ 為**矛盾句 (Contradiction)**。
  3. **相應條件句 (Corresponding Conditional)** $(P_1 \cdot \dots \cdot P_n) \supset C$ 為**恆真句 (Tautology)**。
- **有效論證的三種次分類**：
  1. **正常有效論證**：前提一致，且結論非恆真句。
  2. **特殊有效論證 I（前提不一致）**：若前提本身不一致（無任何一列使前提同時為 T），則根據定義不可能出現「前提皆 T 而結論為 F」的反例列，故**從不一致（矛盾）的前提可以有效推導出任何結論 (Ex Falso Quodlibet)**。
  3. **特殊有效論證 II（結論為恆真句）**：若結論本身是恆真句（無任何一列使結論為 F），則同樣不可能出現反例列，故**恆真句可以從任何前提有效推導出來**。

### 3-8 ~ 3-9 簡短真值表法 (Short Truth Table Test)
- 當原子語句有 5、6 個以上時，完整真值表需 $32, 64 \dots$ 列，計算過於龐大。
- **逆向賦值核心思想**：
  - **檢驗有效性（尋找反例）**：直接假設**結論為 F**，且**所有前提皆為 T**，由外而內逆向推算各原子語句必須具備的真假值。若能找到一組不矛盾的原子語句賦值，即成功構造出反例，證明論證**無效**；若在所有分支都必然產生同一個原子語句既要是 T 又要是 F 的矛盾，則證明論證**有效**。
  - **檢驗一致性**：直接假設集合中**所有語句皆為 T**，逆向尋找是否存在一組一致的原子語句賦值。

### 3-10 真值表定義的證成方法 (Method of Justification for Truth Tables)
- 為什麼實質條件句 $p \supset q$ 在前件 $p$ 為 F 的第 3、4 列必須定義為 T？
- **反證證成法**：我們在日常直覺中確知「肯定前件律 (MP: $p \supset q, p / \therefore q$)」與「選言三段論」為**有效**，而「否定前件謬誤 ($p \supset q, \sim p / \therefore \sim q$)」與「肯定後件謬誤 ($p \supset q, q / \therefore p$)」為**無效**。
  - 若要使「否定前件」無效，必須讓 $p=F, q=T$（此時 $\sim p=T, \sim q=F$）那一列的 $p \supset q$ 為 **T**（第 3 列）！
  - 若要使「肯定後件」無效，搭配肯定前件有效，也能嚴格推導出 $p \supset q$ 的真值表定義。

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **承接前章** | [[Ch01 邏輯導論 (Introduction to Logic)]] | 將 Ch.1 的有效性與一致性定義落實為可計算的真值表列檢驗 |
| **承接前章** | [[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]] | 運用 Ch.2 的五大連詞真值表進行複合式真值運算 |
| **深化概念** | [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]] | 釐清取代 vs. 置換、一對一邏輯形式、恆真/矛盾/適真句 |
| **深化方法** | [[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]] | 完整示範長真值表、簡短真值表逆向賦值步驟與真值表定義證成 |
| **向後延伸** | [[Ch04 自然演繹法證明 (Natural Deduction Proofs)]] | 由於真值表有 $2^n$ 指數爆炸問題，Ch.4 引入語法推論規則（8+10 條）來直接推導有效論證 |
| **向後延伸** | [[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]] | 將簡短真值表法與有限模型展開式結合，用來證明述詞邏輯論證的無效性 |
| **實戰練習** | [[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]] | 對應 Ex 3-1 ~ Ex 3-13 全解（含取代實例 Walk-Through、Ex 3-7 邏輯等值、Ex 3-10/3-11 簡短真值表、Ex 3-12 真值表證成第 2, 4, 6 題） |
| **期中考真題** | [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]] | 對應期中考是非題 (3), (6), (7), (10) 及第二、三大題真值表檢驗一致性與有效性 |
