---
title: "八條單向蘊含推論規則 (Eight Implicational Rules of Inference)"
category: methods
chapters: ["Ch. 4"]
tags: [logic, method, natural-deduction, implicational-rules, MP, MT, DS, HS, Simp, Conj, Add, CD]
updated: 2026-11-22
---

# 八條單向蘊含推論規則 (Eight Implicational Rules of Inference)

> **所屬章節**：[[Ch04 自然演繹法證明 (Natural Deduction Proofs)]]
> **理論基礎**：[[有效性與健全性 (Validity and Soundness)]]、[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]
> **姊妹方法**：[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]、[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]
> **對應練習**：[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]

自然演繹法（Natural Deduction）的第一塊基石是 **8 條單向蘊含推論規則 (8 Implicational Rules of Inference)**。這 8 條規則每一個都是一個已經由真值表驗證為有效的基本論證形式（Valid Argument Form）。在證明中，任何具有該形式之**取代實例 (Substitution Instance)** 的步驟皆可合法推導。

---

## 1. 八條單向蘊含規則的使用鐵律（必考防呆限制！）

在使用這 8 條規則時，必須嚴格遵守以下**兩大鐵律**（詳見 [[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]]）：

1. **鐵律一：只能單向推導 (One-Way Derivation Only)**
   - 因為這 8 條規則只是「前提邏輯蘊涵結論 ($P \supset C$ 為恆真句)」，而**不是**邏輯等值 ($P \equiv C$ 並非恆真句)！
   - 例如由 $A \cdot B$ 可以用 Simp 推得 $A$，但絕對不能反過來由 $A$ 用 Simp 推得 $A \cdot B$！
2. **鐵律二：只能套用在整個列上，嚴禁套用在語句內部的部分子句上 (Whole Lines Only!)**
   - 這是初學者最常犯的致命錯誤！8 條蘊含規則必須以引用列的**主要連接詞 (Main Connective)** 為操作對象，**絕對不能深入括弧或條件句內部對某個局部子句使用**。
   - 🚫 **錯誤示範 1**：從 `1. (A · B) ⊃ C` 用 Simp 推得 `2. A ⊃ C` ❌（極度荒謬！例如「如果你同時喝農藥又吃解藥則會死」不能推出「如果你吃解藥就會死」！因為第 1 列的主要連接詞是 $\supset$ 而非 $\cdot$，不能對前件局部做 Simp）。
   - 🚫 **錯誤示範 2**：從 `1. A ⊃ B` 用 Add 推得 `2. A ⊃ (B ∨ C)` ❌（雖然這個結論在語意上剛好有效，但語法上違反了 Add 只能用在整列、把整列當成一個選言支的規定！對 `1. A ⊃ B` 用 Add 只能得出 `(A ⊃ B) ∨ C`）。

---

## 2. 八條單向蘊含規則完整圖式與解析

### (1) 肯定前件律 (Modus Ponens, MP)
$$\begin{array}{l} p \supset q \\ p \\ \hline \therefore q \end{array}$$
- **核心口訣**：有條件句，且**完整肯定其前件**，即可拆下後件。
- ⚠️ **常見陷阱（肯定後件謬誤 Affirming the Consequent）**：若給定 $p \supset q$ 與 $q$，**絕對不能**用 MP 推得 $p$！

### (2) 否定後件律 (Modus Tollens, MT)
$$\begin{array}{l} p \supset q \\ \sim q \\ \hline \therefore \sim p \end{array}$$
- **核心口訣**：有條件句，且**否定其後件**，即可推得**前件的否定**。
- ⚠️ **常見陷阱**：
  1. **否定前件謬誤 (Denying the Antecedent)**：若給定 $p \supset q$ 與 $\sim p$，**絕對不能**推得 $\sim q$！
  2. **雙重否定號細節**：若給定 `1. ~A ⊃ ~B` 與 `2. B`，注意第 2 列 `B` 並不是後件 `~B` 的否定（`~B` 的否定是 `~~B`）！必須先對第 2 列用 **DN** 得 `3. ~~B`，才能對 1, 3 用 **MT** 得 `4. ~~A`（再用 DN 得 `A`）。

### (3) 選言三段論 (Disjunctive Syllogism, DS)
$$\begin{array}{l} p \lor q \\ \sim p \\ \hline \therefore q \end{array} \qquad \text{或} \qquad \begin{array}{l} p \lor q \\ \sim q \\ \hline \therefore p \end{array}$$
- **核心口訣**：二選一（或至少有一為真）的選言句，**否定其中一邊，就必然肯定另一邊**。
- ⚠️ **注意事項**：
  1. 在本教材（Hausman 13th Ed.）中，DS 允許直接否定左選言支或直接否定右選言支（無須先用 Comm 交換）。
  2. **肯定選言支謬誤**：因為 $\lor$ 是相容選言，若給定 $p \lor q$ 與 $p$，**絕對不能**推得 $\sim q$！
  3. 與 MT 相同，若選言句是 `~A ∨ B` 且另一列是 `A`，必須先對 `A` 用 **DN** 得 `~~A`，才能用 **DS** 推得 `B`。

### (4) 假言三段論 (Hypothetical Syllogism, HS)
$$\begin{array}{l} p \supset q \\ q \supset r \\ \hline \therefore p \supset r \end{array}$$
- **核心口訣**：兩個條件句**首尾相接**（第一個的後件 $q$ 與第二個的前件 $q$ 完全一致），即可消去中間橋樑 $q$，串聯為 $p \supset r$。

### (5) 簡化律 (Simplification, Simp)
$$\begin{array}{l} p \cdot q \\ \hline \therefore p \end{array} \qquad \text{或} \qquad \begin{array}{l} p \cdot q \\ \hline \therefore q \end{array}$$
- **核心口訣**：只要一列的主要連接詞是連言 **`$\cdot$`**，即可直接拆出左連言支或右連言支。
- **解題反射動作**：在證明題中，只要看到任何前提的主要連接詞是 $\cdot$，第一步幾乎都是直接用 **Simp** 把它拆成兩個獨立列！

### (6) 連言律 (Conjunction, Conj)
$$\begin{array}{l} p \\ q \\ \hline \therefore p \cdot q \end{array}$$
- **核心口訣**：將已經分別證出來的兩列 $p$ 與 $q$，用 $\cdot$ 綁在一起（常為了湊出某個複雜條件句的連言前件 $(p \cdot q) \supset r$ 以使用 MP，或為了在 IP 中湊出顯性矛盾句 $q \cdot \sim q$）。

### (7) 添加律 (Addition, Add)
$$\begin{array}{l} p \\ \hline \therefore p \lor q \end{array}$$
- **為什麼可以憑空加上任何語句 $q$？**
  - 因為根據選言 $\lor$ 的真值表，只要已確知 $p$ 為 **T**，那麼無論憑空加上的 $q$ 是 T 還是 F（哪怕 $q$ 是「月亮是起司做的」），選言句 $p \lor q$ 都**必然為 T**！
  - 从資訊量來看，$p \lor q$ 比 $p$ 所斷言的內容更弱（Weakening），而非更強。
- **關鍵戰略價值**：當**結論出現了前提中完全沒出現過的新原子語句**，或者要湊出某個條件句的選言前件 $(A \lor B) \supset C$ 時，100% 必須使用 **Add**！
- *注意*：標準 Add 是把新語句加在**右邊**（$p \lor q$）；若需要新語句在左邊（$q \lor p$），先用 Add 得 $p \lor q$ 後，再用一次 **Comm** 即可。

### (8) 建設性兩難律 (Constructive Dilemma, CD)
$$\begin{array}{l} p \lor q \\ p \supset r \\ q \supset s \\ \hline \therefore r \lor s \end{array}$$
- **核心口訣**：**唯一需要同時引用 3 列**的規則！結合一個選言句 $p \lor q$ 與分別以 $p, q$ 為前件的兩個條件句，推得兩後件的選言 $r \lor s$。

---

## 3. 相關概念與方法連結

- **姊妹規則**：可雙向使用且可用於部分子句的 10 條規則 $\implies$ [[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]
- **進階證法**：引入假設前提的條件證法與歸謬法 $\implies$ [[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]
- **三大限制橫向比較**：[[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]]
- **實戰演練**：[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]
