---
title: "十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)"
category: methods
chapters: ["Ch. 4"]
tags: [logic, method, natural-deduction, equivalence-rules, replacement, DN, DeM, Comm, Assoc, Dist, Contra, Impl, Exp, Taut, Equiv]
updated: 2026-11-22
---

# 十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)

> **所屬章節**：[[Ch04 自然演繹法證明 (Natural Deduction Proofs)]]
> **理論基礎**：[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]（取代 vs. 置換、邏輯等值）
> **姊妹方法**：[[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]、[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]
> **對應練習**：[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]

自然演繹法的第二塊基石是 **10 條雙向等值置換規則 (10 Equivalence Rules of Replacement)**。不同於 [[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]] 的嚴格整列限制，這 10 條規則建立在**雙向邏輯等值 (`::`)** 之上，因此擁有兩大特權：
1. **雙向皆可推導**：由左式可換為右式，由右式亦可換為左式。
2. **可套用於部分子句 (Parts of Lines)**：可以直接深入複雜語句的括弧內部，將某個子句置換為其等值式，而不改變整句的真假值！

---

## 1. 十條雙向等值置換規則詳解與實戰技巧

### (9) 雙重否定律 (Double Negation, DN)
$$p \ :: \ \sim\sim p$$
- **實戰用途**：
  - 消除多餘的雙重否定（如 $\sim\sim A \Rightarrow A$）。
  - 為 **MT** 或 **DS** 鋪路：要對 $\sim A \lor B$ 與 $A$ 使用 DS，必須先對 $A$ 用 **DN** 得 $\sim\sim A$。

### (10) 狄摩根定理 (DeMorgan's Theorem, DeM)
$$\begin{aligned} \sim(p \cdot q) \ &:: \ \sim p \lor \sim q \\ \sim(p \lor q) \ &:: \ \sim p \cdot \sim q \end{aligned}$$
- **核心口訣**：「**否定號乘進/抽出括弧，中間的連言 `$\cdot$` 與選言 `$\lor$` 必須互換**」！
- **黃金反射動作**：只要在證明中看到 **$\sim(A \lor B)$**，立刻用 **DeM** 轉成 **$\sim A \cdot \sim B$**，接著就能用 **Simp** 拆出 $\sim A$ 與 $\sim B$ 兩個超好用的短句！
- ⚠️ **常見錯誤**：把 $\sim(p \cdot q)$ 誤寫成 $\sim p \cdot \sim q$（忘了把 $\cdot$ 換成 $\lor$），或者把 $\sim p \cdot \sim q$ 誤寫成 $\sim(p \cdot q)$。

### (11) 交換律 (Commutation, Comm)
$$\begin{aligned} p \lor q \ &:: \ q \lor p \\ p \cdot q \ &:: \ q \cdot p \end{aligned}$$
- **注意事項**：只有 $\lor$ 與 $\cdot$ 具有交換律（雙條件句 $\equiv$ 雖也對稱，但不在 Comm 規則定義內；而**條件句 $\supset$ 絕對沒有交換律**！$p \supset q$ 與 $q \supset p$ 完全不等值）。

### (12) 結合律 (Association, Assoc)
$$\begin{aligned} p \lor (q \lor r) \ &:: \ (p \lor q) \lor r \\ p \cdot (q \cdot r) \ &:: \ (p \cdot q) \cdot r \end{aligned}$$
- **注意事項**：只有在**兩個連接詞完全相同**（兩個都是 $\lor$，或兩個都是 $\cdot$）時，才能用 **Assoc** 直接移動括弧！若一個是 $\cdot$ 一個是 $\lor$（如 $p \cdot (q \lor r)$），移動括弧會改變語意，必須使用下面的 **分配律 (Dist)**！

### (13) 分配律 (Distribution, Dist) —— 割離多餘字母的秘密武器！
$$\begin{aligned} p \cdot (q \lor r) \ &:: \ (p \cdot q) \lor (p \cdot r) \\ p \lor (q \cdot r) \ &:: \ (p \lor q) \cdot (p \lor r) \end{aligned}$$
- **代數類比**：
  - 第一式如同乘法對加法的分配律：$p \times (q + r) = (p \times q) + (p \times r)$。
  - 第二式則是邏輯獨有的「選言對連言的分配律」：把 `$p \lor$` 分配給括弧內的 $q$ 與 $r$，中間原本的 `$\cdot$` 變成新的**主要連接詞**！
- 💡 **高階必考技巧：用 Dist + Simp 割離多餘字母 (Removing Excess Baggage)**
  - 當你手上有 $A \lor (B \cdot C)$，但結論只需要 $A \lor B$（字母 $C$ 是多餘的累贅），你不能對 $(B \cdot C)$ 做 Simp（違反整列限制！）。
  - **正確解法**：對 $A \lor (B \cdot C)$ 使用 **Dist** 轉為 **$(A \lor B) \cdot (A \lor C)$**！此時主要連接詞變成了 **`$\cdot$`**，下一歩就可以合法使用 **Simp** 直接取出 **$A \lor B$**，完美甩掉多餘的 $C$！

### (14) 異質換位律 / 逆否命題 (Contraposition, Contra)
$$p \supset q \ :: \ \sim q \supset \sim p$$
- **核心口訣**：前件與後件**對調位置**，且**各自加上（或各自拿掉）一個否定號**。
- ⚠️ **注意**：從 $\sim A \supset B$ 用一次 Contra 是得 $\sim B \supset \sim\sim A$（而非 $\sim B \supset A$，還需再用一次 DN 才能消去雙重否定）。

### (15) 蘊涵律 (Implication, Impl) —— 條件句與選言句的任意門！
$$p \supset q \ :: \ \sim p \lor q$$
- **核心口訣**：「**條件號 $\supset$ 變選言號 $\lor$，前件加上（或拿掉）一個否定號，後件保持不動**」。
- **戰略價值**：
  - 當前提是選言句 $A \lor B$，而結論卻要證條件句（或要用 HS/MP）時：先對 $A \lor B$ 的左支用 **DN** 得 $\sim\sim A \lor B$，再用 **Impl** 就變成了 **$\sim A \supset B$**！
  - 當要否定一個條件句 **$\sim(A \supset B)$** 時：自然演繹法沒有直接拆解 $\sim(A \supset B)$ 的規則，必須先在括弧內用 **Impl** 轉為 $\sim(\sim A \lor B)$，接著用 **DeM** 轉為 $\sim\sim A \cdot \sim B$，再用 **DN** 與 **Simp** 即可拆出 **$A$** 與 **$\sim B$**！

### (16) 輸出律 / 移出律 (Exportation, Exp)
$$(p \cdot q) \supset r \ :: \ p \supset (q \supset r)$$
- **直覺意義**：「如果你既滿 18 歲又考過筆試，就能拿到駕照」$\equiv$「如果你滿 18 歲，那麼（只要你考過筆試，就能拿到駕照）」。

### (17) 恆真律 / 重言律 (Tautology, Taut)
$$\begin{aligned} p \ &:: \ p \cdot p \\ p \ &:: \ p \lor p \end{aligned}$$
- **戰略價值**：用來把兩個相同的選言支合併為單一語句！
  - **經典三步殺招**：當你推導出看似詭異的條件句 **$\sim A \supset A$**（若非 A 則 A）時：
    1. 用 **Impl** 轉為 $\sim\sim A \lor A$
    2. 用 **DN** 轉為 $A \lor A$
    3. 用 **Taut** 直接得出 **$A$**！

### (18) 等值律 (Equivalence, Equiv)
$$\begin{aligned} p \equiv q \ &:: \ (p \supset q) \cdot (q \supset p) \\ p \equiv q \ &:: \ (p \cdot q) \lor (\sim p \cdot \sim q) \end{aligned}$$
- **兩種形式的使用時機**：
  - **條件句形式** $(p \supset q) \cdot (q \supset p)$：最常用！因為主要連接詞是 $\cdot$，一轉完馬上可以用 **Simp** 拆出 $p \supset q$ 與 $q \supset p$ 搭配 MP、MT、HS 使用。
  - **同真同假形式** $(p \cdot q) \lor (\sim p \cdot \sim q)$：當題目給了 $\sim(p \cdot q)$ 或要證結論是選言結構時特別好用。

---

## 2. 常見複合變形組合技速查表

| 起始式 | 目標式 | 標準推導步驟（嚴格不跳步！） |
| :--- | :--- | :--- |
| **$\sim(A \supset B)$** | **$A \cdot \sim B$** | `1. ~(A ⊃ B)` $\xrightarrow{\text{Impl}}$ `2. ~(~A ∨ B)` $\xrightarrow{\text{DeM}}$ `3. ~~A · ~B` $\xrightarrow{\text{DN}}$ `4. A · ~B` |
| **$A \lor B$** | **$\sim A \supset B$** | `1. A ∨ B` $\xrightarrow{\text{DN}}$ `2. ~~A ∨ B` $\xrightarrow{\text{Impl}}$ `3. ~A ⊃ B` |
| **$\sim A \supset A$** | **$A$** | `1. ~A ⊃ A` $\xrightarrow{\text{Impl}}$ `2. ~~A ∨ A` $\xrightarrow{\text{DN}}$ `3. A ∨ A` $\xrightarrow{\text{Taut}}$ `4. A` |
| **$A \lor (B \cdot C)$** | **$A \lor B$** | `1. A ∨ (B · C)` $\xrightarrow{\text{Dist}}$ `2. (A ∨ B) · (A ∨ C)` $\xrightarrow{\text{Simp}}$ `3. A ∨ B` |

---

## 3. 相關概念與方法連結

- **姊妹規則**：8 條單向蘊含規則 $\implies$ [[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]
- **進階證法**：條件證法與間接證法 $\implies$ [[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]
- **述詞邏輯的第 11 條等值規則**：量詞否定規則 (QN) $\implies$ [[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]
- **實戰演練**：[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]
