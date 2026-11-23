---
title: "條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)"
category: methods
chapters: ["Ch. 5", "Ch. 9"]
tags: [logic, method, conditional-proof, indirect-proof, reductio-ad-absurdum, theorem, scope-line]
updated: 2026-11-22
---

# 條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)

> **所屬章節**：[[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]]、[[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]]
> **理論基礎**：[[一致性與反例集 (Consistency and Counterexample Set)]]、[[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]
> **前置規則**：[[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]、[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]
> **對應練習**：[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]

**條件證法 (Conditional Proof, CP)** 與**間接證法 / 歸謬證法 (Indirect Proof, IP)** 是自然演繹法中允許我們「引入臨時假設前提 (Assumed Premise, AP)，並在達成目標後將該假設消去 (Discharge)」的兩大子證明機制。它們不僅能大幅簡化複雜證明，更是證明**無前提定理 (Zero-Premise Theorems)** 與實現系統**完備性 (Completeness)** 的關鍵。

---

## 1. 條件證法 (Conditional Proof, CP)

### (1) 形式圖式與操作機制
當我們要證明一個條件句 **$p \supset q$** 時：

```text
  1. (原有前提...)          p
     | m.   p              AP (自行假設前件)
     |      ...
     | n.   q              (由前面步驟推得後件)
  n+1. p ⊃ q               m–n CP (消去 AP，關閉封閉線)
```

- **為什麼 CP 在語意上是健全（保真）的？**
  - 考慮我們要證的條件句 $p \supset q$：根據實質條件句的真值表，當 $p$ 為 **F** 時，$p \supset q$ 自動為 **T**；我們唯一需要擔心的是「萬一 $p$ 為 **T** 時，$q$ 會不會是 F？」。
  - 因此，我們直接**假設 $p$ 為真 (`AP`)**，在這個假設下利用保真的推論規則一步步推導出 **$q$ 也必然為真**！這就證明了「不可能 $p$ 真而 $q$ 假」，故走出封閉線後，$p \supset q$ 無條件成立！

### (2) 巢狀條件證法 (Nested CP)
當要證明的結論是雙層或多層條件句，如 **$A \supset (B \supset C)$** 時，可以在第一層封閉線內再開啟第二層封閉線（或者先開啟一層假設 $A \cdot B$ 推得 $C$，得 $(A \cdot B) \supset C$ 後再用 **Exp** 轉為 $A \supset (B \supset C)$）：

```text
  | 1.   A                 AP (外層假設)
  | | 2.   B               AP (內層假設)
  | |    ...
  | | k.   C               (推得最內層後件)
  | k+1. B ⊃ C             2–k CP (先消去內層 AP！)
  k+2. A ⊃ (B ⊃ C)         1–(k+1) CP (再消去外層 AP！)
```

---

## 2. 間接證法 / 歸謬證法 (Indirect Proof, IP / Reductio ad Absurdum)

### (1) 形式圖式與操作機制
當結論 $C$ **不是條件句**（例如是單一原子語句 $A$ 或連言句 $A \cdot B$），且難以由前提直接正向推導時：

```text
  1. (原有前提...)          p
     | m.   ~C             AP (假設結論的否定)
     |      ...
     | n.   q · ~q         (推導出任何一個顯性矛盾句)
  n+1. C                   m–n IP (消去 AP，直接得出結論 C)
```

- **理論基礎**：根據 [[一致性與反例集 (Consistency and Counterexample Set)]] 的核心定理，將前提與結論的否定 $\sim C$ 放在一起即構成**反例集**。若反例集能推導出矛盾句 $q \cdot \sim q$，代表反例集不一致，故原結論 $C$ 必然為真！
- *細節提示*：若欲證結論本身帶有否定號（如結論為 $\sim A$），在引入 AP 時可以直接假設 $A$（或假設 $\sim\sim A$），導出矛盾後由 IP 得 $\sim A$。

### (2) 爆炸原理：如何僅用 4 步從矛盾句推導出任意結論 $X$？(Ex Falso Quodlibet)
為什麼說「有了 CP 與 18 條規則，其實就能導出 IP」？因為只要在假設 $\sim C$ 下推導出矛盾句 $q \cdot \sim q$，我們就能用以下經典 4 步推導出任何語句（包含 $C$）：
1. $q \cdot \sim q$ （已推得的矛盾列）
2. $q$ （由 1, **Simp**）
3. $q \lor C$ （由 2, **Add** —— **憑空把想要的結論 $C$ 加進來！**）
4. $\sim q$ （由 1, **Simp**）
5. **$C$** （由 3, 4, **DS**！）
接著由 **CP** 得 $\sim C \supset C$，再用 **Impl, DN, Taut** 即得 **$C$**！

---

## 3. 封閉線（作用域）的三大絕對禁令

在執行 CP 與 IP 時，封閉線（Scope Line）代表「在該假設前提 AP 的保護傘下才成立的臨時世界」。必須遵守以下三大鐵律（詳見 [[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]]）：

1. **禁令一：已消去封閉線內的列，外部絕對禁止引用！**
   - 一旦在第 $n+1$ 列用 CP 或 IP 關閉了第 $m \sim n$ 列的封閉線，第 $m$ 列到第 $n$ 列就像是已經拆掉的鷹架，第 $n+2$ 列之後的任何步驟**絕對不可再引用 $m \sim n$ 之間的任何一列**（只能引用第 $n+1$ 列得出來的結果）。
2. **禁令二：多層巢狀封閉線絕對禁止交叉！**
   - 必須遵守「**後進先出 (Last-In, First-Out)**」原則：較晚假設的內層 AP，必須先被 CP 或 IP 消去，之後才能消去外層 AP。
3. **禁令三：證明結束時，所有引入的 AP 必須全部消去！**
   - 證明的最後一列（最終結論）必須落在所有封閉線之外，不依賴任何未消去的 AP。
   - *(外加 [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]] 的 **UG 限制 3**：在未消去 AP 的封閉線內，不可對該 AP 中自由出現的準變元做 UG；但消去 AP 走出封閉線外後即可合法做 UG！)*

---

## 4. 無前提演繹：如何證明邏輯定理 (Proving Theorems, $\vdash \phi$)

當題目**沒有給任何前提**，要求證明一個恆真句 $\phi$ 為**定理 (Theorem)** 時：
- **策略 1（主要連接詞為 $\supset$）**：直接使用 **CP**（若有多層 $\supset$ 則用巢狀 CP），一步步假設前件、推導後件。
  - 例：證明 $\vdash A \supset (B \supset A)$
    ```text
    | 1.   A               AP
    | | 2.   B             AP
    | | 3.   A · B         1, 2 Conj
    | | 4.   A             3 Simp
    | 5.   B ⊃ A           2–4 CP
    6. A ⊃ (B ⊃ A)         1–5 CP
    ```
- **策略 2（主要連接詞為 $\equiv$）**：預計最後用 **Equiv** 組合，因此先開啟第一個 CP 證出左到右 $P \supset Q$，再開啟第二個平行的 CP 證出右到左 $Q \supset P$，然後用 **Conj** 與 **Equiv** 合併為 $P \equiv Q$。
- **策略 3（主要連接詞為 $\lor$ 或 $\sim$）**：可先在草稿將結論用 **Impl** 轉為條件句再用 CP，或者直接開啟 **IP** 假設整個結論的否定 $\sim \phi$，推導出矛盾句！

---

## 5. 相關概念與方法連結

- **後設理論意涵**：為什麼 CP 與 IP 讓語句邏輯具備完備性？ $\implies$ [[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]
- **在述詞邏輯中的升級**：CP + UG 解毒證明法 $\implies$ [[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]
- **三大限制橫向比較**：[[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]]
- **實戰演練**：[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]
