---
title: "Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)"
category: chapters
chapter: "Ch. 5"
source: "Ch_05_條件證法與間接證法.docx / Hausman Ch. 5"
tags: [logic, chapter, conditional-proof, indirect-proof, theorem, soundness, completeness, metalogic]
updated: 2026-11-22
---

# Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)

> **對應原始講義**：`raw/Ch_05_條件證法與間接證法.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 5)（輔）

僅靠 [[Ch04 自然演繹法證明 (Natural Deduction Proofs)]] 的 18 條規則，語句邏輯系統是**不完備的 (Incomplete)**：它既無法在「零前提」下證明任何恆真句（定理），也無法簡潔證明如 $A \supset B / \therefore A \supset (A \cdot B)$ 的有效論證。本章引入**條件證法 (Conditional Proof, CP)** 與**間接證法 / 歸謬證法 (Indirect Proof, IP)**，使語句邏輯自然演繹系統具備完整的**健全性 (Soundness)** 與**完備性 (Completeness)**。

---

## 1. 核心架構與知識節點

### 5-1 & 5-3 條件證法 (Conditional Proof, CP)
- **[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]**
  - **適用時機**：當欲證明的結論（或中間目標）是一個**條件句 $p \supset q$**（或可等值轉化為條件句，如用 Impl 將選言句 $\sim p \lor q$ 轉為 $p \supset q$，或用 Equiv 將 $p \equiv q$ 拆為兩個條件句）。
  - **操作步驟**：
    1. 引入條件句的前件 $p$ 作為**自行假設前提 (Assumed Premise, AP)**，並開啟一條**封閉線 / 作用域線 (Scope Line)**。
    2. 在封閉線內結合原有前提與 18 條規則，推導出後件 $q$。
    3. 結束封閉線，將該 AP **消去 (Discharge)**，在封閉線外寫出條件句 **$p \supset q$**，並標註引用範圍 `m–n CP`。
  - **作用域鐵律 (Scope Line Restrictions)**（詳見 [[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]]）：
    - **一旦 AP 被消去（封閉線關閉），封閉線內的所有步驟（第 $m$ 列至第 $n$ 列）即全部失效，後續步驟絕對不可再引用封閉線內的任何一列！**
    - **多層巢狀假設 (Nested Assumptions)**：可在一個 CP 內部再開啟內層 CP，但必須遵循「後進先出 (LIFO)」原則，**內層封閉線必須先消去，兩條封閉線絕對不可交叉**。
  - **逆否命題策略**：若直接假設 $p$ 難以推導（例如 $p$ 是複雜選言句），可改為假設後件的否定 $\sim q$ [AP]，推導出 $\sim p$，由 CP 得 $\sim q \supset \sim p$ 後，再用一次 **Contra** 得出 $p \supset q$。

### 5-2 間接證法 / 歸謬證法 (Indirect Proof, IP / Reductio ad Absurdum)
- **理論根據**：來自 [[一致性與反例集 (Consistency and Counterexample Set)]] 的核心定理——若將所有前提加上「結論的否定 $\sim C$」（反例集）會導出邏輯矛盾，則原論證必然有效。
- **操作步驟**：
  1. 欲證結論 $C$，先引入結論的否定 **$\sim C$** 作為**自行假設前提 (AP)**，開啟封閉線。
  2. 在封閉線內推導出任何一個顯性的**矛盾句 (Contradiction) $q \cdot \sim q$**。
  3. 結束封閉線並消去 AP，在封閉線外直接得出結論 **$C$**（或 $\sim\sim C$ 再用 DN 得 $C$），標註 `m–n IP`。
- **CP 與 IP 的相互可推導性**：
  - 有了 CP 與 18 條規則，其實可以導出 IP：因為從矛盾句 $q \cdot \sim q$ 可在 4 步內（透過 Simp 取出 $q$ 與 $\sim q$，對 $q$ 用 Add 得 $q \lor C$，再與 $\sim q$ 用 DS 得 $C$）推導出任意結論 $C$（即 **Ex Falso Quodlibet**）；或者從假設 $\sim C$ 推出 $q \cdot \sim q$ 後，也可推得 $C$，用 CP 得 $\sim C \supset C$，再用 Impl 與 Taut 得 $C$。

### 5-4 & 5-5 無前提演繹、定理 (Theorems) 與證明前提不一致
- **無前提演繹 (Zero-Premise Deductions) 與定理 (Theorems, $\vdash \phi$)**：
  - 一個不依賴任何給定前提（所有引入的 AP 皆已在證明結束前完全消去）而僅靠 CP 或 IP 證明出來的語句，稱為該邏輯系統的**定理 (Theorem)**，記為 $\vdash \phi$（例：$\vdash A \supset (B \supset A)$、排中律 $\vdash A \lor \sim A$）。
- **證明前提不一致 (Proving Premises Inconsistent)**：
  - 若題目給定一組前提，要求證明「前提不一致」，則無須引入 AP，直接從該組前提利用推論規則推導出一個矛盾句 $q \cdot \sim q$ 即可。

### 5-7 後設邏輯：語句邏輯的健全性與完備性 (Soundness and Completeness of SL)
- **[[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]** & **[[語法學與語意學的雙軌對稱架構 (Syntactic vs Semantic Dual Architecture in Logic)]]**
  - 區分「個別論證的健全性（Ch.1）」與「整個邏輯推論系統的後設健全性與完備性（Ch.5）」：
    - **系統健全性 (System Soundness)**：凡是在語法上可證明的（$\Gamma \vdash \phi$），在語意上必然有效（$\Gamma \models \phi$）。特別地，**每一個定理都是恆真句**（If $\vdash \phi$, then $\models \phi$）。代表推論規則不會「無中生有」證出無效的結論。
    - **系統完備性 (System Completeness)**：凡是在語意上有效的（$\Gamma \models \phi$），在語法上必然可由推論規則證明出來（$\Gamma \vdash \phi$）。特別地，**每一個恆真句都是定理**（If $\models \phi$, then $\vdash \phi$）。代表推論規則足夠強大，不會遺漏任何邏輯真理。

### 5-8 引進與消去規則系統 (Introduction and Elimination Rules System)
- 比較本教材的「18 條規則 + CP/IP 系統」與極簡的「引進—消去系統（Int-Elim System，共 11 條規則：5 個連詞各一組 Intro/Elim 加上重複律 Reiteration $R$）」：
  - **Int-Elim 系統優點**：規則極度精簡對稱，非常適合在後設邏輯（Metalogic）中以數學歸納法證明系統的健全性與完備性。
  - **18 條規則系統優點**：保留了人類日常推論最直覺的規則（如 MT, DS, HS, DeM, Contra），使實際推導步驟大幅縮短（在 Int-Elim 系統中，連簡單的 MT 或 DeM 都必須動用子證明才能導出，對初學者而言過於冗長）。

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **承接前章** | [[Ch04 自然演繹法證明 (Natural Deduction Proofs)]] | 在 18 條規則基礎上加入 CP 與 IP，解決 18 條規則無法證明定理的不完備問題 |
| **深化方法** | [[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]] | 詳細圖解單層/巢狀 CP、IP 歸謬法、無前提定理證明與 Ex Falso Quodlibet 4 步推導 |
| **深化概念** | [[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]] | 深入對比語法可證 ($\vdash$) 與語意有效 ($\models$) 的雙軌對應 |
| **向後延伸** | [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]] | CP 與 IP 在述詞邏輯中與全稱一般化（UG）結合（AP 消去後變元「解毒」可做 UG，即 UG 第 3 條限制） |
| **實戰練習** | [[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]] | 對應 Ex 5-1 ~ Ex 5-8 全解（含用 IP 與不用 IP 雙軌對照、無前提定理、Ex 5-7 證明前提集不一致、Ex 5-8 新規則有效性評估） |
| **期中考真題** | [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]] | 對應期中考第二大題 (2) 導出矛盾證明不一致，以及第五大題無前提定理之多重證法 |
