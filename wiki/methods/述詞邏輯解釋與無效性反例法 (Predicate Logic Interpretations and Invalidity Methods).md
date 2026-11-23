---
title: "述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)"
category: methods
chapters: ["Ch. 7", "Ch. 8"]
tags: [logic, method, predicate-logic, interpretation, invalidity, counterexample, expansion, short-truth-table]
updated: 2026-11-22
---

# 述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)

> **所屬章節**：[[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]]、[[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]]
> **理論基礎**：[[有效性與健全性 (Validity and Soundness)]]、[[一致性與反例集 (Consistency and Counterexample Set)]]、[[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]]
> **前置方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]
> **對應練習**：[[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]

在述詞邏輯（PL）中，自然演繹法只能證明論證**有效**，不能證明論證**無效**。要證明一個述詞邏輯論證**無效 (Invalid)**（或證明一組述詞邏輯語句**一致 Consistent**），我們必須在語意學層次構造一個**反例解釋 (Counterexample Interpretation)**，使得在這個解釋下**所有前提皆為真 (`T`)，而結論為假 (`F`)**。

---

## 1. 構造一個完整「解釋 (Interpretation)」的 5 個標準步驟

在述詞邏輯中，一個形式公式（如 $(x)(Fx \supset Gx)$）本身沒有確定的真假值，直到我們給予它一個**解釋 (Interpretation)**：
1. **指定非空論域 (Domain of Discourse, $D$)**：規定量詞 $(x)$ 與 $(\exists x)$ 所涵蓋的個體集合（例如：$D =$ 所有正整數，或有限模型 $D = \{a, b\}$）。
2. **指派個體常元 (Individual Constants)**：為式中出現的每個常元 $a, b, c \dots$ 指派論域 $D$ 中的一個具體對象。
3. **解釋性質/關係述詞 (Predicates)**：
   - **內涵法 (Intensional)**：賦予每個述詞 $F, G, R$ 一個具體屬性或關係定義（如 $Fx$：$x$ 是偶數）。
   - **外延法 (Extensional)**：直接對論域中的每個個體指派原子語句真值（如 $V(Fa)=T, V(Fb)=F$）。
4. **指派獨立語句常元 (Sentence Constants)**：若式中有零元語句常元 $A, B$，指派其 T/F 值。
5. **核算量限語句真值**：確認所有前提皆為 `T` 且結論為 `F`。

---

## 2. 證明述詞邏輯無效性的三大實戰方法比較

| 方法名稱 | 核心作法 | 優點 | 缺點與限制 | 適用題型 |
| :--- | :--- | :--- | :--- | :--- |
| **方法一：日常經驗事實反例法** | 以現實世界事物（人、狗、動物、哲學家）定義論域與述詞 | 直覺好懂，符合日常語感 | 有時現實事實是否有例外會引發爭議；複雜關係式不易湊出日常例子 | 傳統亞里斯多德三段論、簡單的一元述詞論證 |
| **方法二：正整數 / 自然數算術反例法** | 固定令 $D =$ **所有正整數 $\{1, 2, 3, \dots\}$**，以奇偶數、倍數、大小關係定義述詞 | **真假值 100% 客觀明確、毫無經驗爭議**！且擁有無限個體可用 | 需熟悉基本算術性質湊出條件 | 含常元、一元或二元關係述詞的各類無效論證 |
| **方法三：有限模型展開式 + 簡短真值表法** | 在 $D=\{a\}$ 或 $D=\{a, b\}$ 將量詞展開為 SL 連言/選言式，再用簡短真值表逆向賦值 | **完全機械化、系統化**！不需任何想像力即可按步算出反例賦值 | 當所需論域超過 3 個個體或含複雜多元關係時，展開式會變得很長 | 絕大多數一元述詞論證與小型二元關係論證 |

---

## 3. 方法二詳解：正整數算術反例法 (Mathematical Counterexamples)

### 操作秘訣
1. 固定宣告：**論域 $D =$ 所有正整數 ($\{1, 2, 3, \dots\}$)**。
2. 常用算術述詞積木庫：
   - **互斥分類**：$x$ 是偶數 vs. $x$ 是奇數。
   - **真子集包含關係**（滿足 $(x)(Ax \supset Bx)$ 但 $\sim(x)(Bx \supset Ax)$）：
     - $Ax$：$x$ 是 4 的倍數（$\{4, 8, 12 \dots\}$） $\subset$ $Bx$：$x$ 是偶數（$\{2, 4, 6 \dots\}$）。
   - **單一特定數字**（適合讓 $(\exists x)Fx$ 為真，或針對常元 $a=1, a=2$ 微調）：
     - $x = 1$、$x = 2$、$x > 1$、$x < 10$、$x$ 是質數且為偶數（唯一解 $x=2$）。

### 💡 講義經典實戰範例（正整數反例法）
> **證明以下論證無效**：
> 1. $(x)[(Fx \cdot Gx) \supset Hx]$
> 2. $Fa \cdot \sim Ha$ / $\therefore \sim Ga$
>
> **構造反例思考過程**：
> - 我們要讓前提 1、2 皆為 **T**，且結論 $\sim Ga$ 為 **F**（即 **$Ga$ 必須為 T**！）。
> - 由前提 2 為 T，可知 **$Fa$ 為 T** 且 **$Ha$ 為 F**。
> - 咦？如果 $Fa=\mathbf{T}$ 且 $Ga=\mathbf{T}$ 且 $Ha=\mathbf{F}$，那在 $x=a$ 時，$(Fa \cdot Ga) \supset Ha$ 不就會變成 $(\mathbf{T} \cdot \mathbf{T}) \supset \mathbf{F} = \mathbf{F}$，導致前提 1 變成 F 嗎？！
> - **一秒看穿關鍵**：原來這題在語意上是**有效的**（由前提 1 UI 得 $(Fa \cdot Ga) \supset Ha$，結合 $Fa$ 與 $\sim Ha$ 必然推出 $\sim Ga$）！
>
> **對比真正的無效論證（修改前提 1 為存在量詞或改變結構）**：
> 證明：1. $(x)(Fx \supset Hx)$，2. $(\exists x)(Gx \cdot Hx)$ / $\therefore (\exists x)(Fx \cdot Gx)$ 無效：
> - **正整數反例解釋**：
>   - 論域 $D =$ 所有正整數 $\{1, 2, 3, \dots\}$
>   - $Fx$：$x$ 是 4 的倍數（$\{4, 8, 12 \dots\}$）
>   - $Hx$：$x$ 是偶數（$\{2, 4, 6 \dots\}$）
>   - $Gx$：$x = 2$
> - **驗證**：
>   - 前提 1 $(x)(Fx \supset Hx)$：「所有 4 的倍數都是偶數」$\implies$ **T**！
>   - 前提 2 $(\exists x)(Gx \cdot Hx)$：「存在一個正整數等於 2 且是偶數（即 $x=2$）」$\implies$ **T**！
>   - 結論 $(\exists x)(Fx \cdot Gx)$：「存在一個正整數既是 4 的倍數又等於 2」$\implies$ **F**！
> - 前提皆真而結論為假，**成功證明該論證無效**！

---

## 4. 方法三詳解：有限模型展開式 + 簡短真值表法 (Expansion Method)

### 展開規則回顧（以 2 個個體的論域 $D = \{a, b\}$ 為例）
1. **全稱量詞 $(x)\Phi x$ 展開為連言 `$\cdot$`**：
   $$(x)\Phi x \implies \Phi a \cdot \Phi b$$
2. **存在量詞 $(\exists x)\Phi x$ 展開為選言 `$\lor$`**：
   $$(\exists x)\Phi x \implies \Phi a \lor \Phi b$$
3. **雙層量詞逐步由外而內展開**（如 $(x)(\exists y)Rxy$ 在 $D=\{a, b\}$）：
   - 先展開外層 $(x)$：$(\exists y)Ray \cdot (\exists y)Rby$
   - 再展開內層 $(\exists y)$：**$(Raa \lor Rab) \cdot (Rba \lor Rbb)$**

### 💡 講義經典實戰範例（2 個個體展開式 + 簡短真值表證無效）
> **證明以下論證無效**：
> 1. $(\exists x)(Ax \cdot Bx)$
> 2. $(\exists x)(Cx \cdot Bx)$ / $\therefore (\exists x)(Ax \cdot Cx)$
>
> **Step 1：為何 1 個個體的論域 $D_1 = \{a\}$ 不夠？**
> - 在 $D_1 = \{a\}$ 中，前提 1 為 $Aa \cdot Ba$ (T)，前提 2 為 $Ca \cdot Ba$ (T)，此時 $Aa, Ba, Ca$ 全部被迫為 T，導致結論 $Aa \cdot Ca$ 也變成 T，找不出反例（因為要讓「有些 A 是 B」和「有些 C 是 B」成立、但「沒有 A 是 C」，至少需要**兩個不同的個體**分別擔任 A 和 C！）。
>
> **Step 2：在 2 個個體的論域 $D_2 = \{a, b\}$ 中展開**：
> - 前提 1：$(Aa \cdot Ba) \lor (Ab \cdot Bb)$
> - 前提 2：$(Ca \cdot Ba) \lor (Cb \cdot Bb)$
> - 結　論：$(Aa \cdot Ca) \lor (Ab \cdot Cb)$
>
> **Step 3：簡短真值表逆向賦值（令結論 = F，前提 1 = T，前提 2 = T）**：
> 1. 為使前提 1 的左選言支 $(Aa \cdot Ba) = \mathbf{T}$，指派 **$Aa = \mathbf{T}, Ba = \mathbf{T}$**（並令 $Ab = \mathbf{F}$）。
> 2. 為使結論的左選言支 $(Aa \cdot Ca) = \mathbf{F}$，因為 $Aa=\mathbf{T}$，強制指派 **$Ca = \mathbf{F}$**！
> 3. 又因為我們已令 $Ab = \mathbf{F}$，所以結論的右選言支 $(Ab \cdot Cb)$ 自動為 $\mathbf{F}$，確保整個結論為 **F**！
> 4. 最後看前提 2 $(Ca \cdot Ba) \lor (Cb \cdot Bb) = \mathbf{T}$：因為 $Ca = \mathbf{F}$，左選言支為 F，故右選言支 $(Cb \cdot Bb)$ 必須為 **T** $\implies$ 指派 **$Cb = \mathbf{T}, Bb = \mathbf{T}$**！
>
> **Step 4：彙整反例解釋賦值表**：
> - 論域 $D = \{a, b\}$
> - **$V(Aa) = \mathbf{T}, \ V(Ba) = \mathbf{T}, \ V(Ca) = \mathbf{F}$**
> - **$V(Ab) = \mathbf{F}, \ V(Bb) = \mathbf{T}, \ V(Cb) = \mathbf{T}$**
> - 在此解釋下，前提 1 為 `T`、前提 2 為 `T`、結論為 `F`，**證明原論證無效**！

---

## 5. 相關概念與方法連結

- **當論證有效時如何證明？** $\implies$ [[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]
- **可判定性與不可判定性的理論邊界** $\implies$ [[語句邏輯與述詞邏輯的演進與比較 (Evolution from Sentential to Predicate and Identity Logic)]]
- **實戰演練**：[[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]
