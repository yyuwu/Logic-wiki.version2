---
title: "Ch08 述詞邏輯語意學 (Predicate Logic Semantics)"
category: chapters
chapter: "Ch. 8"
source: "Ch_08_述詞邏輯_語意學.docx / Hausman Ch. 8 & Ch. 12"
tags: [logic, chapter, predicate-logic, semantics, interpretation, invalidity, counterexample, undecidability]
updated: 2026-11-22
---

# Ch08 述詞邏輯語意學 (Predicate Logic Semantics)

> **對應原始講義**：`raw/Ch_08_述詞邏輯_語意學.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 8 & Ch. 12)（輔）

在語句邏輯（SL）中，一個論證只有有限個（$2^n$）真值賦值列；但在述詞邏輯（PL）中，由於**論域 (Domain)** 可以包含任意數量（甚至無限多個）的個體，且述詞可有無限多種指派方式，因此一個 PL 論證擁有**無限多種可能的解釋 (Interpretations)**。本章探討如何嚴格定義 PL 的「解釋」，以及如何構造**反例解釋 (Counterexample Interpretation)** 來證明述詞邏輯論證的**無效性 (Invalidity)** 與**一致性 (Consistency)**。

---

## 1. 核心架構與知識節點

### 8-1 述詞邏輯的「解釋」(Interpretations in Predicate Logic)
- **[[述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)]]**
  - 給予一個述詞邏輯語句集或論證一個完整的**解釋 (Interpretation)**，必須包含以下 **5 個步驟**：
    1. **指定論域 (Domain of Discourse, $D$)**：規定變元 $x, y, z$ 所涵蓋的非空個體集合（至少要有 1 個個體）。
    2. **指派個體常元 (Individual Constants)**：為每個出現的個體常元 $a, b, c \dots$ 指定論域 $D$ 中的一個特定對象。
    3. **指派性質常元 / 述詞 (Property Constants)**：
       - **內涵解釋 (Intensional Interpretation)**：賦予每個述詞 $F, G \dots$ 一個具體意義（例如在正整數論域中，令 $Fx$ 代表「$x$ 是偶數」）。
       - **外延解釋 (Extensional Interpretation)**：直接列出或指派論域中每個個體代入該述詞後的真假值（例如在 $D=\{a, b\}$ 中，直接指派 $V(Fa)=T, V(Fb)=F$）。
    4. **指派語句常元 (Sentence Constants)**：若式中有獨立的語句常元 $A, B \dots$，直接指派其真假值 T 或 F。
    5. **計算量限語句的真值**：依據上述指派，決定每個全稱或存在語句在該解釋下的真假值。

### 8-2 & 8-3 證明述詞邏輯論證無效性的三種方法 (Three Methods for Proving Invalidity)
- **核心原則**：一個 PL 論證是有效的，若且唯若在**所有可能的解釋**下，只要前提皆真，結論必真。因此，要證明一個 PL 論證**無效 (Invalid)**，只需要找出**一個反例解釋 (Counterexample Interpretation)**，使得在此解釋下**所有前提皆為真 (T)，而結論為假 (F)**！
- **方法一：日常經驗事實反例法 (Factual Counterexample Method)**
  - 直接選取日常世界的事物作為論域與述詞意義，使前提在現實中皆為真、結論在現實中為假。
  - **範例**：要證明 $(x)(Ax \supset Bx), (x)(Cx \supset Bx) / \therefore (x)(Ax \supset Cx)$ 無效：
    - 令論域 $D =$ 所有動物；$Ax = x$ 是人；$Bx = x$ 會死；$Cx = x$ 是狗。
    - 前提 1「所有人都會死」(T)、前提 2「所有狗都會死」(T)，但結論「所有人都是狗」(F)！故無效。
  - **缺點**：有時日常事實真假會有爭議，或對複雜式子不易直覺想出日常例子。
- **方法二：自然數 / 正整數算術反例法 (Mathematical / Natural Numbers Counterexample Method)**
  - **最清晰且毫無經驗爭議的方法**！固定令論域 **$D =$ 所有正整數 (Positive Integers, $\{1, 2, 3, \dots\}$)**，並用基礎算術性質（如偶數、奇數、4 的倍數、$x > 1$、$x = 2$）來解釋述詞。
  - **範例**：要證明 $(x)[(Fx \cdot Gx) \supset Hx], Fa \cdot \sim Ha / \therefore \sim Ga$ 無效：
    - 令 $D =$ 正整數；$a = 2$；$Fx = x$ 是偶數；$Gx = x > 1$；$Hx = x$ 是 4 的倍數。
    - 檢驗：前提 2 $Fa \cdot \sim Ha$（「2 是偶數且 2 不是 4 的倍數」）為 **T**；結論 $\sim Ga$（「2 不大於 1」）為 **F**。
    - 為使前提 1 $(x)[(Fx \cdot Gx) \supset Hx]$ 也為 T，微調 $Fx$ 為「$x$ 是 4 的倍數或 $x=2$」並調整 $Gx$ 為「$x > 2$」等，即可嚴格構造出無爭議的算術反例。
- **方法三：有限模型論域展開式 + 簡短真值表法 (Finite Model Expansion Method)**
  - **最系統化、機械化的方法**！結合 [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] 7-8 節的展開式與 [[Ch03 真值表 (Truth Tables)]] 的簡短真值表法：
    1. 先嘗試包含 1 個個體的論域 $D_1 = \{a\}$；若無法使前提皆 T 且結論為 F，則擴充為 2 個個體的論域 **$D_2 = \{a, b\}$**（或 $D_3 = \{a, b, c\}$）。
    2. 將所有量限前提與結論展開為以 $Fa, Fb, Ga, Gb \dots$ 構成的語句邏輯複合句。
    3. 使用**簡短真值表逆向賦值法**，令展開後的結論為 **F**、所有前提皆為 **T**，求出 $V(Fa), V(Fb), V(Ga), V(Gb)$ 的具體 T/F 指派。

### 8-4 & 8-5 一致性、有效性與不可判定性 (Consistency, Validity, and Undecidability)
- **證明一致性 (Proving Consistency)**：構造一個解釋（或有限模型展開式賦值），使集合中的所有語句**同時為真 (T)**。
- **為什麼不能用「窮舉解釋法」來證明 PL 論證的有效性？—— 邱奇不可判定性定理 (Church's Undecidability Result)**（原文書 Ch.12 核心補充）：
  - 在只含一元述詞（Monadic Predicates，共 $n$ 個述詞）的述詞邏輯中，可以證明：若一個論證在擁有 $2^n$ 個個體的模型論域中找不到反例，則它在任何更大或無限的論域中也找不到反例（因此**一元述詞邏輯是可判定的 Decidable**）。
  - 然而，阿隆佐·邱奇（Alonzo Church, 1936）證明了：**包含二元以上關係述詞的一階述詞邏輯（Full First-Order Predicate Logic）是不可判定的 (Undecidable)**！不存在任何通用的機械演算法能在有限步內判定任意關係述詞邏輯論證是否有效（某些無效論證只在無限論域中才存在反例，其真值樹會無限生長 Infinitely Growing Tree）。
  - 這正是為什麼我們必須在 [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]] 中建立**述詞邏輯自然演繹證明法**來證明有效性與不一致性！

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **承接前章** | [[Ch03 真值表 (Truth Tables)]] | 將 Ch.3 的簡短真值表逆向賦值法升級為 Ch.8 的「有限模型展開式 + 簡短真值表反例法」 |
| **承接前章** | [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] | 運用 Ch.7 的模型論域展開式規則（$(x)$ 展開為連言、$(\exists x)$ 展開為選言）進行語意賦值 |
| **深化方法** | [[述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)]] | 詳列三種無效性反例法的操作SOP與算術/展開式實例 |
| **向後延伸** | [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]] | Ch.8 用語意反例法證明「無效與一致」，Ch.9 則用語法推論規則證明「有效與不一致」 |
| **綜合比較** | [[語句邏輯與述詞邏輯的演進與比較 (Evolution from Sentential to Predicate and Identity Logic)]] | 對比 SL 的可判定性（$2^n$ 真值表）與一階關係 PL 的邱奇不可判定性定理 |
| **實戰練習** | [[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]] | 對應 Ex 8-1 ~ Ex 8-3、邏輯小考 8 及 Ch.10 關係述詞 Ex 10-8 之自然數算術反例與 $D=\{a,b\}$ 展開式反例全解 |
