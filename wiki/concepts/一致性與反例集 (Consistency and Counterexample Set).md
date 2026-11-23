---
title: "一致性與反例集 (Consistency and Counterexample Set)"
category: concepts
chapters: ["Ch. 1", "Ch. 3", "Ch. 5", "Ch. 8"]
tags: [logic, concept, consistency, inconsistency, counterexample-set, indirect-proof]
updated: 2026-11-22
---

# 一致性與反例集 (Consistency and Counterexample Set)

> **所屬章節**：[[Ch01 邏輯導論 (Introduction to Logic)]]、[[Ch03 真值表 (Truth Tables)]]、[[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]]、[[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]]
> **對應方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]、[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]

**一致性 (Consistency)** 是陳述句集合（Set of Statements）的核心邏輯性質。透過**反例集 (Counterexample Set)** 的概念，我們得以將「論證的有效性 (Validity)」與「語句集合的不一致性 (Inconsistency)」完美統一起來，這不僅是簡短真值表法的基礎，更是自然演繹法中**間接證法（歸謬法，IP）**的理論靈魂。

---

## 1. 一致性 (Consistency) 與不一致性 (Inconsistency) 的定義

- **一致 (Consistent)**：
  - 一組陳述句 $\{S_1, S_2, \dots, S_n\}$ 是**一致的**，若且唯若在邏輯上**有可能 (Logically Possible)** 它們**同時全部為真**。
  - 在語句邏輯真值表中，表現為**至少存在一列**，使得 $S_1, S_2, \dots, S_n$ 的真值同時為 `T`（亦即它們的連言句 $S_1 \cdot S_2 \cdot \dots \cdot S_n$ 不是矛盾句）。
  - 在述詞邏輯中，表現為**至少存在一個解釋 (Interpretation)**，使得集合中所有語句同時為 `T`。
- **不一致 (Inconsistent)**：
  - 一組陳述句是**不一致的**，若且唯若在邏輯上**不可能 (Logically Impossible)** 它們同時為真（集合內部隱含邏輯矛盾）。
  - 在真值表中，表現為**沒有任何一列**能讓所有語句同時為 `T`（亦即它們的連言句 $S_1 \cdot S_2 \cdot \dots \cdot S_n$ 是**矛盾句 Contradiction**）。
  - **講義經典範例**：
    1. 顯性不一致：$\{p, \sim p\}$。
    2. 隱性不一致：
       - $S_1$：甘迺迪總統是一位品格高尚、沒有任何道德瑕疵的人。
       - $S_2$：任何背叛婚姻的人都有道德瑕疵。
       - $S_3$：甘迺迪總統曾多次背叛婚姻。
       - 這三句話在邏輯上不可能同時為真（由 $S_2$ 與 $S_3$ 可推得甘迺迪有道德瑕疵，與 $S_1$ 直接矛盾），故 $\{S_1, S_2, S_3\}$ 為**不一致集合**。
    3. **理髮師悖論 (Barber Paradox)**：
       - 「村裡有一位理髮師，他給且只給村裡所有不給自己刮鬍子的人刮鬍子。」
       - 若問：「這位理髮師給不給自己刮鬍子？」若他給自己刮，依定義他不該給自己刮；若他不給自己刮，依定義他就必須給自己刮（$Baa \equiv \sim Baa$，矛盾！），證明該描述本身是不一致的，邏輯上不可能存在這樣的理髮師。

---

## 2. 核心橋樑定理：有效性 $\iff$ 反例集不一致

對於任何一個論證：
$$P_1, P_2, \dots, P_n \ / \ \therefore C$$

我們定義該論證的**反例集 (Counterexample Set)** 為：**將所有前提與「結論的否定 ($\sim C$)」放在一起所構成的語句集合**：
$$\text{Counterexample Set} = \{P_1, P_2, \dots, P_n, \sim C\}$$

### 三位一體等價定理 (The Tripartite Equivalence Theorem)
在邏輯學中，以下三項陳述完全等價（見 [[Ch03 真值表 (Truth Tables)]] 3-6 節）：

1. **【論證有效性】**：論證 $P_1, P_2, \dots, P_n / \therefore C$ 是**有效的 (Valid)**。
   - *意義*：邏輯上不可能 $P_1 \dots P_n$ 皆為真而 $C$ 為假。
2. **【反例集不一致性】**：反例集 $\{P_1, P_2, \dots, P_n, \sim C\}$ 是**不一致的 (Inconsistent)**。
   - *意義*：邏輯上不可能 $P_1 \dots P_n$ 與 $\sim C$ 同時全部為真（亦即連言句 $P_1 \cdot P_2 \cdot \dots \cdot P_n \cdot \sim C$ 為**矛盾句 Contradiction**）。
3. **【相應條件句恆真】**：**相應條件句 (Corresponding Conditional)** $(P_1 \cdot P_2 \cdot \dots \cdot P_n) \supset C$ 為**恆真句 (Tautology)**。
   - *意義*：在所有可能的真值賦值下，只要前件 $(P_1 \cdot \dots \cdot P_n)$ 為真，後件 $C$ 必為真。

---

## 3. 這一定理在四大章節中的實戰應用

這條核心定理貫穿了本知識庫的四個核心方法：

| 應用章節與方法 | 如何運用「有效性 $\iff$ 反例集不一致」定理？ |
| :--- | :--- |
| **1. 簡短真值表法**<br>([[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]) | 要檢驗論證是否無效，就是檢驗其**反例集是否一致**！我們直接令所有前提 $P_i = T$ 且結論 $C = F$（即 $\sim C = T$），看能否找到一組使反例集同真的賦值。 |
| **2. 間接證法 / 歸謬法 (IP)**<br>([[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]) | 要證明結論 $C$，我們故意引入 $\sim C$ 作為自行假設前提（AP），把前提擴充為**反例集** $\{P_1 \dots P_n, \sim C\}$，然後推導出矛盾句 $q \cdot \sim q$，證明反例集不一致，從而確立 $C$！ |
| **3. 爆炸原理 (Ex Falso Quodlibet)**<br>([[Ch03 真值表 (Truth Tables)]] / [[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]]) | 若前提集合 $\{P_1 \dots P_n\}$ **本身就已經不一致**，那麼無論再加入什麼樣的 $\sim C$，反例集 $\{P_1 \dots P_n, \sim C\}$ 依然不一致！因此**不一致的前提可以有效推導出任何結論**。 |
| **4. 述詞邏輯反例解釋法**<br>([[述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)]]) | 證明述詞邏輯論證無效，就是構造一個模型解釋（如正整數或 $D=\{a,b\}$ 展開式），使該論證的**反例集**在該解釋下全部為真。 |

---

## 4. 相關概念與方法連結

- **前導概念**：[[有效性與健全性 (Validity and Soundness)]]
- **語意檢驗方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]
- **語法歸謬方法**：[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]
- **雙軌對稱總覽**：[[語法學與語意學的雙軌對稱架構 (Syntactic vs Semantic Dual Architecture in Logic)]]
- **實戰演練**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]、[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]
