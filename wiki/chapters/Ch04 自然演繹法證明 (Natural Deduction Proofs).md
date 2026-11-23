---
title: "Ch04 自然演繹法證明 (Natural Deduction Proofs)"
category: chapters
chapter: "Ch. 4"
source: "Ch_04_證明.docx / Hausman Ch. 4"
tags: [logic, chapter, natural-deduction, proof, implicational-rules, equivalence-rules]
updated: 2026-11-22
---

# Ch04 自然演繹法證明 (Natural Deduction Proofs)

> **對應原始講義**：`raw/Ch_04_證明.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 4)（輔）

當論證包含許多原子語句時，[[Ch03 真值表 (Truth Tables)]] 的 $2^n$ 列數會呈指數爆炸，且真值表法無法直接套用於非真值函應的述詞邏輯。本章引入**自然演繹法 (Natural Deduction)**，透過 **8 條單向蘊含規則**與 **10 條雙向等值置換規則**，從前提一步步做語法推導（Syntactic Derivation）得出結論。
> **重要提醒**：自然演繹法只能用來證明論證**有效 (Valid)**，無法用來證明論證無效（證明無效須使用 [[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]）。

---

## 1. 核心架構與知識節點

### 4-1 ~ 4-5 第一部分：8 條單向蘊含推論規則 (8 Implicational Rules of Inference)
- **[[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]**
  - 本質：每一條皆為一個小型的**有效論證形式 (Valid Argument Form)**。
  - **兩大鐵律限制**（詳見 [[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]]）：
    1. **只能單向推導 (One-Way Only)**：從前提推向結論，不可逆推。
    2. **只能套用在整個列 (Whole Lines Only)**：**嚴禁套用在語句內部的一部分（子句）上**！例如絕對不能從 $(A \cdot B) \supset C$ 套用 Simp 推得 $A \supset C$（這是無效推論！）。

| 編號 | 規則名稱 | 英文與縮寫 | 規則形式 | 核心用途與注意事項 |
| :---: | :--- | :--- | :--- | :--- |
| 1 | **肯定前件律** | Modus Ponens (**MP**) | $p \supset q, p / \therefore q$ | 拆解條件句最基本規則；切勿犯「肯定後件」謬誤 |
| 2 | **否定後件律** | Modus Tollens (**MT**) | $p \supset q, \sim q / \therefore \sim p$ | 由否定後件推得否定前件；切勿犯「否定前件」謬誤 |
| 3 | **選言三段論** | Disjunctive Syllogism (**DS**) | $p \lor q, \sim p / \therefore q$<br>$p \lor q, \sim q / \therefore p$ | 否定其中一個選言支，必然肯定另一個選言支 |
| 4 | **假言三段論** | Hypothetical Syllogism (**HS**) | $p \supset q, q \supset r / \therefore p \supset r$ | 串聯兩個首尾相接的條件句（遞移性） |
| 5 | **簡化律** | Simplification (**Simp**) | $p \cdot q / \therefore p$<br>$p \cdot q / \therefore q$ | 拆解連言句以取出所需的單一成分 |
| 6 | **連言律** | Conjunction (**Conj**) | $p, q / \therefore p \cdot q$ | 將已證出的兩列合併為連言句 |
| 7 | **添加律** | Addition (**Add**) | $p / \therefore p \lor q$ | **引進前提未曾出現過的新語句 $q$**（弱化主張而非強化） |
| 8 | **建設性兩難律** | Constructive Dilemma (**CD**) | $p \lor q, p \supset r, q \supset s / \therefore r \lor s$ | **唯一需要同時引用 3 列**的推論規則 |

### 4-7 ~ 4-10 第二部分：10 條雙向等值置換規則 (10 Equivalence Rules of Replacement)
- **[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]**
  - 本質：每一條皆建立在**邏輯等值 (`::`)** 之上（即雙條件句為恆真句）。
  - **兩大核心特權**：
    1. **雙向皆可推導 (Two-Way)**：左式可換右式，右式亦可換左式。
    2. **可套用在部分子句 (Parts of Lines Allowed)**：不僅可用於整列，更可直接置換一個複雜語句內部的某個子句（且同一列中不必一致置換所有相同子句）。

| 編號 | 規則名稱 | 英文與縮寫 | 邏輯等值形式 (`::`) | 核心用途與注意事項 |
| :---: | :--- | :--- | :--- | :--- |
| 9 | **雙重否定律** | Double Negation (**DN**) | $p :: \sim\sim p$ | 湊出 DS 或 MT 所需的雙重否定形式 |
| 10 | **狄摩根定理** | DeMorgan's Theorem (**DeM**) | $\sim(p \cdot q) :: \sim p \lor \sim q$<br>$\sim(p \lor q) :: \sim p \cdot \sim q$ | 否定號移入/移出括弧，同時將 $\cdot$ 與 $\lor$ 互換 |
| 11 | **交換律** | Commutation (**Comm**) | $p \lor q :: q \lor p$<br>$p \cdot q :: q \cdot p$ | 交換選言支或連言支順序（注意：$\supset$ 無交換律！） |
| 12 | **結合律** | Association (**Assoc**) | $p \lor (q \lor r) :: (p \lor q) \lor r$<br>$p \cdot (q \cdot r) :: (p \cdot q) \cdot r$ | 相同連詞（皆 $\lor$ 或皆 $\cdot$）移動括弧位置 |
| 13 | **分配律** | Distribution (**Dist**) | $p \cdot (q \lor r) :: (p \cdot q) \lor (p \cdot r)$<br>$p \lor (q \cdot r) :: (p \lor q) \cdot (p \lor r)$ | **極重要**！用來將 $p \lor (q \cdot r)$ 轉為連言後用 Simp 割離多餘字母 $r$ |
| 14 | **異質換位律** | Contraposition (**Contra**) | $p \supset q :: \sim q \supset \sim p$ | 原命題與逆否命題邏輯等值（前件後件互換並各加/減一否定號） |
| 15 | **蘊涵律** | Implication (**Impl**) | $p \supset q :: \sim p \lor q$ | **條件句與選言句互換的橋樑** |
| 16 | **輸出律 / 移出律** | Exportation (**Exp**) | $(p \cdot q) \supset r :: p \supset (q \supset r)$ | 將連言前件拆為雙層條件句（或反之） |
| 17 | **恆真律 / 重言律** | Tautology (**Taut**) | $p :: p \cdot p$<br>$p :: p \lor p$ | 消除重複項（如從 $\sim A \supset A \xRightarrow{\text{Impl}} \sim\sim A \lor A \xRightarrow{\text{DN}} A \lor A \xRightarrow{\text{Taut}} A$） |
| 18 | **等值律** | Equivalence (**Equiv**) | $p \equiv q :: (p \supset q) \cdot (q \supset p)$<br>$p \equiv q :: (p \cdot q) \lor (\sim p \cdot \sim q)$ | 拆解或組合雙條件句 $\equiv$ |

### 4-6, 4-11 & 4-12 證明解題策略與五大常見錯誤
- **解題黃金策略**：
  1. **從短句與單一字母下手**：優先觀察前提中的單一原子語句或其否定，搭配 MP、MT、DS 連鎖拆解複雜句。
  2. **從結論倒推 (Working Backward)**：觀察結論的主要連接詞與包含的字母，思考哪條規則可以產生該結構。
  3. **拆解複合句**：看到 $\sim(A \lor B)$ 立即用 **DeM** 轉為 $\sim A \cdot \sim B$ 再用 **Simp**；看到 $A \equiv B$ 立即用 **Equiv**。
  4. **割離多餘字母 (Excess Baggage)**：當需要的語句 $A$ 與不需要的 $B \cdot C$ 被綁在選言句 $A \lor (B \cdot C)$ 時，用 **Dist** 轉為 $(A \lor B) \cdot (A \lor C)$，再用 **Simp** 取出 $A \lor B$！
  5. **條件句與選言句混雜時**：善用 **Impl** ($p \supset q :: \sim p \lor q$) 統一戰場。
- **五大常見錯誤 (Five Common Errors)**：
  1. **把 8 條單向蘊含規則錯誤套用在部分子句上**（最嚴重違規！）。
  2. 忘記可以用 **Add** 憑空引進結論需要的新字母。
  3. 忘記可以用 **Dist + Simp** 割離選言句中的多餘字母。
  4. 試圖去證明一個本來就**無效 (Invalid)** 的論證（陷入死胡同）。
  5. 忽略否定號的管轄範圍（如混淆 $\sim A \lor B$ 與 $\sim(A \lor B)$）。

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **承接前章** | [[Ch03 真值表 (Truth Tables)]] | 每一條推論規則的有效性與邏輯等值性，皆由 Ch.3 真值表所保證 |
| **深化方法** | [[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]] | 詳列 8 條單向規則的推論圖式、整列限制與錯誤案例診斷 |
| **深化方法** | [[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]] | 詳列 10 條等值規則的子句置換技巧與複合變形策略 |
| **向後延伸** | [[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]] | 僅靠 18 條規則無法證明無前提的恆真句，Ch.5 引入 CP 與 IP 使系統達到完備 |
| **向後對比** | [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]] | 在 PL 中，18 條 SL 規則不能直接穿透量詞內部，須搭配 4 條量詞規則（UI/EI/UG/EG）與 QN |
| **實戰練習** | [[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]] | 對應 Ex 4-1 ~ Ex 4-14 全解（含正向/逆向 Dist 提公因式、一題多解與 Ex 4-14 語句邏輯表達完備性 DNF） |
| **期中考真題** | [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]] | 對應期中考第四大題（不使用 CP/IP，僅用 18 條規則之三種不同證明路徑） |
