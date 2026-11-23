---
title: "習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)"
category: exercises
chapters: ["Ch. 8", "Ch. 9", "Ch. 10 (Relational Predicate Logic)", "Ch. 11 (Textbook Ch. 13)"]
source: "Ex_Ch08_習題解答.docx, Ex_Ch09_習題解答.docx, Ex_Ch10_關係述詞習題解答.docx, Quiz8_Ch08_邏輯小考8解答_20231212.docx, Quiz9_Ch09_邏輯小考9解答_20231219.docx"
tags: [logic, exercise, predicate-logic, invalidity, counterexample, expansion, UI, EI, UG, EG, QN, ID, IR, restrictions, relational-proofs]
updated: 2026-11-23
---

# 習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)

> **涵蓋章節**：[[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]]、[[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]]（含原文書 Ch. 10 多量詞關係述詞證明）、[[Ch11 等同與確定描述詞 (Identity and Definite Descriptions)]]
> **對應原始題庫檔案**：`raw/Ex_Ch08_習題解答.docx`（Ex 8-1 ~ Ex 8-3 全解）、`raw/Quiz8_Ch08_邏輯小考8解答_20231212_展開式與無效反例.docx`、`raw/Ex_Ch09_習題解答.docx`（Ex 9-1 ~ Ex 9-5 全解）、`raw/Quiz9_Ch09_邏輯小考9解答_20231219_述詞邏輯證明.docx`、`raw/Ex_Ch10_關係述詞習題解答.docx`（Ex 10-8, Ex 10-10, Ex 10-11, Ex 10-12 關係反例與多重量詞證明）、`raw/Supp_Ch09_Ch11_Rules_for_Predicate_Logic.pdf`
> **對應概念与方法**：[[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]]、[[等同與確定描述詞理論 (Identity and Theory of Descriptions)]]、[[述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)]]、[[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]、[[述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)]]

本頁完整收錄並解析 Ch. 8 一元述詞無效性反例（Ex 8-1 ~ Ex 8-3 & 小考 8）、Ch. 9 一元述詞證明與五項限制診斷（Ex 9-1 ~ Ex 9-5 & 小考 9）、Ch. 10 二元/三元關係述詞無效性反例與多重量詞證明（Ex 10-8, Ex 10-10, Ex 10-11, Ex 10-12），以及 Ch. 11 等同規則（ID / IR）證明。

---

## 第一部分：Ch. 8 & Ch. 10 證明述詞邏輯論證無效性題庫全解（Ex 8-1 ~ 8-3、小考 8 & Ex 10-8）

### 1. Exercise 8-1：構造使同一個量限語句分別為「真 (`T`)」與「假 (`F`)」的兩種解釋
- **(1) $(\exists x)(Ax \cdot Bx)$**：
  - **解釋 A（使其為 T）**：論域 $D =$ 自然數 $\{1, 2, 3, \dots\}$；$Ax =$ "$x$ 是偶數"；$Bx =$ "$x$ 是 3 的倍數" $\implies$「存在自然數既是偶數又是 3 的倍數（如 $x=6$）」為 **`T`**。
  - **解釋 B（使其為 F）**：論域 $D =$ 自然數；$Ax =$ "$x$ 是偶數"；$Bx =$ "$x$ 是奇數" $\implies$「存在自然數既是偶數又是奇數」為 **`F`**。
- **(3) $(x)(Ax \supset \sim Bx)$**：
  - **解釋 A（使其為 T）**：論域 $D =$ 無限制；$Ax =$ "$x$ 是人類"；$Bx =$ "$x$ 是全知全能的" $\implies$「所有人類都不是全知全能的」為 **`T`**。
  - **解釋 B（使其為 F）**：論域 $D =$ 無限制；$Ax =$ "$x$ 是人類"；$Bx =$ "$x$ 是男性" $\implies$「所有人類都不是男性」為 **`F`**。
- **(5) $(x)[(Ax \lor Bx) \supset Cx]$**：
  - **解釋 A（使其為 T）**：論域 $D =$ 無限制；$Ax =$ "$x$ 是男人"；$Bx =$ "$x$ 是女人"；$Cx =$ "$x$ 是人類" $\implies$「男人與女人都是人類」為 **`T`**。
  - **解釋 B（使其為 F）**：論域 $D =$ 無限制；$Ax =$ "$x$ 是男人"；$Bx =$ "$x$ 是女人"；$Cx =$ "$x$ 是狗" $\implies$ 為 **`F`**。
- **(7) $(\exists x)Gx \supset \sim(x)(Bx \supset Gx)$**：
  - **解釋 A（使其為 T）**：論域 $D =$ 自然數；$Bx =$ "$x$ 是 3 的倍數"；$Gx =$ "$x$ 是偶數" $\implies$ 前件「存在偶數」(T)，後件「並非所有 3 的倍數都是偶數（如 $x=9$）」(T)，整句為 **`T`**。
  - **解釋 B（使其為 F）**：論域 $D =$ 自然數；$Bx =$ "$x$ 是 4 的倍數"；$Gx =$ "$x$ 是 2 的倍數" $\implies$ 前件 (T)，後件「並非所有 4 的倍數都是 2 的倍數」(F)，故 $\mathbf{T} \supset \mathbf{F} = \mathbf{F}$！

---

### 2. Exercise 8-2（自然數算術反例法）與 Exercise 8-3（$D=\{a, b\}$ 展開式反例法）雙軌對照

> 下面 5 道題目在 `Ex 8-2` 與 `Ex 8-3` 中完全相同，分別展示如何用**「自然數算術反例」**與**「2 個個體展開式賦值」**雙軌證明無效（詳見 [[述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)]]）：

| 題號與待證無效論證 | 方法 A：自然數論域 $D = \{1, 2, 3, \dots\}$ 算術反例 (`Ex 8-2`) | 方法 B：有限論域 $D = \{a, b\}$ 展開式真值賦值反例 (`Ex 8-3`) |
| :--- | :--- | :--- |
| **(1)**<br>1. $(\exists x)(Ax \cdot Bx)$<br>2. $(\exists x)(Bx \cdot Cx)$<br>$/ \therefore (\exists x)(Ax \cdot Cx)$ | • $Ax$: $x$ 是偶數；$Bx$: $x$ 是 3 的倍數；$Cx$: $x$ 是奇數<br>• 前提 1：6 是偶數且是 3 的倍數 (`T`)<br>• 前提 2：3 是 3 的倍數且是奇數 (`T`)<br>• 結　論：存在自然數既是偶數又是奇數 (`F`) | • **$V(Aa)=\mathbf{F}, V(Ba)=\mathbf{T}, V(Ca)=\mathbf{T}$**<br>• **$V(Ab)=\mathbf{T}, V(Bb)=\mathbf{T}, V(Cb)=\mathbf{F}$**<br>• P1: $(F\cdot T) \lor (T\cdot T) = \mathbf{T}$<br>• P2: $(T\cdot T) \lor (T\cdot F) = \mathbf{T}$<br>• C: $(F\cdot T) \lor (T\cdot F) = \mathbf{F}$ |
| **(3)**<br>1. $(\exists x)(Ax \cdot \sim Bx)$<br>2. $(\exists x)(Ax \cdot \sim Cx)$<br>3. $(\exists x)(\sim Bx \cdot Dx)$<br>$/ \therefore (\exists x)[Ax \cdot (\sim Bx \cdot Dx)]$ | • $Ax$: 偶數；$Bx$: 3 的倍數；$Cx$: 4 的倍數；$Dx$: 奇數<br>• P1: $x=2$ 是偶數且非 3 的倍數 (`T`)<br>• P2: $x=2$ 是偶數且非 4 的倍數 (`T`)<br>• P3: $x=5$ 非 3 的倍數且是奇數 (`T`)<br>• C: 存在自然數既是偶數 ($Ax$) 又是奇數 ($Dx$) (`F`) | • **$V(Aa)=\mathbf{F}, V(Ba)=\mathbf{F}, V(Ca)=\text{任意}, V(Da)=\mathbf{T}$**<br>• **$V(Ab)=\mathbf{T}, V(Bb)=\mathbf{F}, V(Cb)=\mathbf{F}, V(Db)=\mathbf{F}$**<br>• 個體 $b$ 使 P1, P2 為 `T`；個體 $a$ 使 P3 為 `T`；但 $a$ 與 $b$ 皆使結論為 `F`！ |
| **(5)**<br>1. $(\exists x)(Px \cdot \sim Qx)$<br>2. $(x)(Rx \supset Px)$<br>$/ \therefore (\exists x)(Rx \cdot \sim Qx)$ | • **修正算術反例**（使結論為 F！）：<br>  令 $Px$: $x$ 是偶數；$Qx$: $x$ 是 4 的倍數；**$Rx$: $x$ 是 8 的倍數**！<br>• P1: $x=2$ 是偶數但非 4 的倍數 (`T`)<br>• P2: 所有 8 的倍數都是偶數 (`T`)<br>• C: 存在 8 的倍數不是 4 的倍數 (`F`)！<br>*(註：原始檔 Ex 8-2(5) 誤令 $Rx=$ 偶數導致結論亦為真，已於介入點回報並修正！)* | • **$V(Pa)=\mathbf{T}, V(Qa)=\mathbf{F}, V(Ra)=\mathbf{F}$**<br>• **$V(Pb)=\text{任意}, V(Qb)=\text{任意}, V(Rb)=\mathbf{F}$**<br>• 因 $Ra=F, Rb=F$，故前提 2 $(Ra \supset Pa) \cdot (Rb \supset Pb) = \mathbf{T}$，且結論 $(Ra \cdot \sim Qa) \lor (Rb \cdot \sim Qb) = \mathbf{F}$！ |
| **(7)**<br>1. $(x)(Px \supset Qx)$<br>2. $(x)(Qx \supset Rx)$<br>$/ \therefore (x)(Px \cdot Rx)$ | • $Px$: 4 的倍數；$Qx$: 2 的倍數；$Rx$: 偶數<br>• P1: 所有 4 的倍數皆是 2 的倍數 (`T`)<br>• P2: 所有 2 的倍數皆是偶數 (`T`)<br>• C: **所有自然數**都同時是 4 的倍數且是偶數 (`F`，如 $x=1, 2, 3$ 皆非！) | • 令**所有原子句 $Pa, Qa, Ra, Pb, Qb, Rb$ 全為 `F`**！<br>• 因前件全為 `F`，P1 與 P2 兩個全稱條件句皆空真 (`T`)；但連言結論 $(Pa \cdot Ra) \cdot (Pb \cdot Rb)$ 為 **`F`**！ |
| **(9)**<br>1. $(\exists x)(Ax \cdot Bx)$<br>2. $(x)(\sim Bx \lor \sim Cx)$<br>$/ \therefore (x)(\sim Ax \lor \sim Cx)$ | • $Ax$: 3 的倍數；$Bx$: 偶數；$Cx$: 奇數<br>• P1: $x=6$ 是 3 的倍數且為偶數 (`T`)<br>• P2: 所有自然數不是偶數就是非奇數 (`T`)<br>• C: 所有自然數不是 3 的倍數就是非奇數 (`F`，因為 **$x=3$ 既是 3 的倍數又是奇數**！) | • **$V(Aa)=\mathbf{T}, V(Ba)=\mathbf{F}, V(Ca)=\mathbf{T}$**（個體 $a$ 擊破結論！）<br>• **$V(Ab)=\mathbf{T}, V(Bb)=\mathbf{T}, V(Cb)=\mathbf{F}$**（個體 $b$ 使 P1 為 `T`）<br>• 核算 P2 為 `T`，結論左連言支 $(\sim Aa \lor \sim Ca) = (F \lor F) = \mathbf{F}$！ |

---

### 3. 邏輯小考 (8) 解答（2023.12.12 —— 3 個體展開式與 2 個體無效性證明）
> **對應原始檔案**：`raw/Quiz8_Ch08_邏輯小考8解答_20231212_展開式與無效反例.docx`

1. **構作語句 $(x)(Ax \supset Bx) \supset (\exists x)(Bx \cdot Cx)$ 在論域 $D = \{a, b, c\}$ 的展開式**：
   - **Ans.**：**$[(Aa \supset Ba) \cdot (Ab \supset Bb) \cdot (Ac \supset Bc)] \ \supset \ [(Ba \cdot Ca) \lor (Bb \cdot Cb) \lor (Bc \cdot Cc)]$**
2. **用展開式證明論證無效**：$1. \ (\exists x)(Ax \lor Bx) \quad 2. \ (x)[(Ax \cdot Bx) \supset \sim Cx] \ / \ \therefore (\exists x)\sim Cx$
   - **修正反例賦值（於 $D = \{a, b\}$）**：
     - 為使結論 $(\exists x)\sim Cx$（展開為 $\sim Ca \lor \sim Cb$）為 **`F`**，必須令 **$V(Ca) = \mathbf{T}, \ V(Cb) = \mathbf{T}$**（即 $\sim Ca = \mathbf{F}, \sim Cb = \mathbf{F}$）。
     - 為使前提 2 $[(Aa \cdot Ba) \supset \sim Ca] \cdot [(Ab \cdot Bb) \supset \sim Cb]$ 在後件 $\sim Ca, \sim Cb$ 皆為 `F` 時仍為 **`T`**，前件 $(Aa \cdot Ba)$ 與 $(Ab \cdot Bb)$ 必須皆為 **`F`**！
     - 同時為使前提 1 $(Aa \lor Ba) \lor (Ab \lor Bb)$ 為 **`T`**，只需令 **$V(Aa)=\mathbf{T}, V(Ba)=\mathbf{F}, V(Ab)=\mathbf{T}, V(Bb)=\mathbf{F}$**（此時 $Aa \lor Ba = \mathbf{T}$，而 $Aa \cdot Ba = \mathbf{F}$！）。
     - *(註：若原題結論為 $/ \therefore (x)Cx$、前提 2 後件為 $Cx$，則如小考解答直接令 **$V(Aa)=V(Ba)=V(Ab)=V(Bb)=\mathbf{T}$ 且 $V(Ca)=V(Cb)=\mathbf{F}$**，此時前提 1 為 `T`，前提 2 若為 $[(Aa \cdot \sim Ba) \supset Ca]$ 則前件假而為 `T`，結論 $Ca \cdot Cb$ 為 `F`！)*。

---

### 4. ⭐ Exercise 10-8：多元關係述詞（含二元與三元關係）的「自然數算術反例」與「$D=\{a,b\}$ 展開式反例」

> **對應原始檔案**：`raw/Ex_Ch10_關係述詞習題解答.docx`（Ex 10-8 第 1, 3, 5, 7 題 —— 關係邏輯無效性證明代表作！）

| 題號與關係述詞論證 | 反例 1：自然數論域 $D = \{1, 2, 3, \dots\}$ 算術關係反例 | 反例 2：有限論域 $D = \{a, b\}$ 展開式賦值反例 |
| :--- | :--- | :--- |
| **(1)**<br>$1. \ (\exists x)(y)Fxy$<br>$/ \therefore (x)(y)Fyx$ | • 令 **$Fxy$：$x \times y = y$**（或 $x \le y$）<br>• 前提 $(\exists x)(y)(x \times y = y)$：當 **$x = 1$** 時，對所有自然數 $y$，$1 \times y = y$ 恆成立 (`T`)！<br>• 結論 $(x)(y)(y \times x = x)$：對所有自然數 $x, y$，$y \times x = x$ 明顯為假 (`F`)！ | • P1 展開：$(Faa \cdot Fab) \lor (Fba \cdot Fbb)$<br>• C 展開：$(Faa \cdot Fba) \cdot (Fab \cdot Fbb)$<br>• 賦值：**$V(Faa)=\mathbf{F}, \ V(Fab)=V(Fba)=V(Fbb)=\mathbf{T}$**<br>• 此時 P1 右支 $(Fba \cdot Fbb) = \mathbf{T}$，故 P1 為 `T`；但結論因 $Faa=\mathbf{F}$ 而為 **`F`**！ |
| **(3)**<br>$1. \ (\exists x)(\exists y)Fxy$<br>$2. \ (\exists x)(\exists y)Gxy$<br>$/ \therefore (\exists x)(\exists y)(Fxy \cdot Gxy)$ | • 令 **$Fxy$：$x + y = 2$**；**$Gxy$：$x \times y = 2$**<br>• P1：當 $x=1, y=1$ 時 $1+1=2$ (`T`)<br>• P2：當 $x=1, y=2$ 時 $1 \times 2 = 2$ (`T`)<br>• C：不存在任何一對自然數 $(x, y)$ 同時滿足 $x+y=2$ 且 $x \times y = 2$ (`F`)！ | • 賦值：**$V(Faa)=\mathbf{T}$**（餘 $F$ 皆 `F`）；**$V(Gab)=\mathbf{T}$**（餘 $G$ 皆 `F`）<br>• 此時 P1 因 $Faa=T$ 為 `T`，P2 因 $Gab=T$ 為 `T`，但每一組同下標的 $(F_{ij} \cdot G_{ij})$ 皆為 **`F`**！ |
| **(5)**<br>$1. \ (\exists x)(y)Fxy$<br>$/ \therefore Faa$ | • 令 **$Fxy$：$x \times y = y$**，且指派常元 **$a = 2$**<br>• P1：當 $x=1$ 時，對所有 $y$，$1 \times y = y$ 為真 (`T`)<br>• C：$Faa$ 即 $2 \times 2 = 2$，為假 (`F`)！ | • 賦值：**$V(Faa)=\mathbf{F}, \ V(Fab)=V(Fba)=V(Fbb)=\mathbf{T}$**<br>• P1 因右支 $(Fba \cdot Fbb) = \mathbf{T}$ 而為 `T`，結論 $Faa = \mathbf{F}$！ |
| **(7) 三元關係量詞交換**<br>$1. \ (x)(y)(\exists z)Fxyz$<br>$/ \therefore (\exists x)(y)(z)Fxyz$ | • 令 **$Fxyz$：$x + y = z$**<br>• P1 $(x)(y)(\exists z)(x+y=z)$：對任意自然數 $x, y$，都存在一個自然數 $z$ 等於 $x+y$ (`T`)！<br>• C $(\exists x)(y)(z)(x+y=z)$：存在一個固定的自然數 $x$，使得對所有 $y, z$ 都滿足 $x = z - y$ (`F`)！ | • 在 $D=\{a, b\}$ 展開為 8 個三元原子句 $Faaa \dots Fbbb$：<br>• 令 **$V(Faab)=V(Fabb)=V(Fbab)=V(Fbbb)=\mathbf{T}$**，且 **$V(Faaa)=V(Faba)=V(Fbaa)=V(Fbba)=\mathbf{F}$**<br>• 此時對任意 $x, y$，取 $z=b$ 皆使 $Fxyb=\mathbf{T}$（故 P1 為 `T`），但結論每個連言支都含有 $z=a$ 的假項，故結論為 **`F`**！ |

---

## 第二部分：Ch. 9 一元述詞邏輯證明與錯誤診斷題庫全解（Ex 9-1 ~ Ex 9-5 & 小考 9）

> **對應原始檔案**：`raw/Ex_Ch09_習題解答.docx`、`raw/Quiz9_Ch09_邏輯小考9解答_20231219_述詞邏輯證明.docx`、`raw/Supp_Ch09_Ch11_Rules_for_Predicate_Logic.pdf`

### 1. Exercise 9-2：精確抓出錯誤證明違反哪一條規則限制（對應 `raw/Ex_Ch09_習題解答.docx`）

```text
【Ex 9-2 (1) — 把單向規則 MP 誤用在量詞內部的部分子句上！】
  1. (x)[(Hx · Kx) ⊃ Mx]   p
  2. (∃x)(Hx · Kx)         p
  3. Hx · Kx               2 EI
  4. Mx                    1, 3 MP    ❌ [錯誤！第 1 列的主要運算元是全稱量詞 (x) 而非 ⊃，未先對第 1 列做 UI 脫去量詞前，MP 絕對不能直接穿透量詞套用在部分子句上！]
  5. (∃x)Mx                4 EG

【Ex 9-2 (3) — 先 UI 後 EI 導致違反 EI 限制 2！】
  1. (∃x)(Fx · ~Mx)        p
  2. (x)[(Gx ∨ Hx) ⊃ Mx]   p
  3. (Gy ∨ Hy) ⊃ My        2 UI       (先對第 2 列做了 UI，此時準變元 y 已在第 3 列自由出現！)
  4. Fy · ~My              1 EI       ❌ [錯誤！違反 EI 限制 2：EI 引進的準變元 y 已經在第 3 列自由出現過，不是全新變元！（正確做法應把第 3、4 列順序對調：先 EI 後 UI！）]
  5. ~My                   4 Simp
  6. ~(Gy ∨ Hy)            3, 5 MT
  7. (∃x)~(Gx ∨ Hx)        6 EG

【Ex 9-2 (5) — 連犯三條致命大錯的綜合診斷題！】
  1. (∃x)[(Px · Qx) ∨ Rx]  p
  2. (x)~Rx                p
  3. (∃x)(Px ∨ Rx)         1 Simp     ❌ [錯誤 1！Simp 是單向規則，只能用在整列主要連詞為 · 時，絕對不能穿透量詞 (∃x) 與選言 ∨ 對內部的 (Px · Qx) 做局部 Simp！]
  4. Px ∨ Rx               3 EI
  5. ~Px                   2, 4 DS    ❌ [錯誤 2！第 2 列 (x)~Rx 尚未做 UI 脫去量詞，不能直接拿來跟第 4 列做 DS！]
  6. (x)~Px                5 UG       ❌ [錯誤 3！違反 UG 限制 2：準變元 x 是在第 4 列由 EI 引進（在 EI 列自由出現），絕對不能對 x 做 UG！]
```

---

### 2. Exercise 9-4：量詞否定規則 (QN) 正誤診斷（對應 `raw/Ex_Ch09_習題解答.docx`）
- **(1)** 從 $(x)\sim Fx$ 用 QN 得 $\sim(\exists x)\sim Fx$？ $\implies$ **不正確**！量詞右側的 $\sim$ 必須拿掉，正確結果應為 **$\sim(\exists x)Fx$**。
- **(3)** 從 $(x)\sim(\sim Fx \lor Gx)$ 用 QN 得 $\sim(\exists x)(Fx \lor Gx)$？ $\implies$ **不正確**！QN 只會拿掉緊鄰量詞右側的那一個否定號，括弧內部的 $\sim Fx$ 不能動！正確結果應為 **$\sim(\exists x)(\sim Fx \lor Gx)$**。
- **(5)** 從 $\sim(\exists y)(\sim Ry \cdot \sim Ky)$ 用 QN 得 $(y)(Ry \cdot Ky)$？ $\implies$ **不正確**！緊鄰 $(\exists y)$ 右側沒有否定號，故移入後應在括弧外加上一個否定號，正確結果為 **$(y)\sim(\sim Ry \cdot \sim Ky)$**。
- **(7)** **正確**。
- **(9)** 從 $(y)\sim[Fy \supset (\exists z)(Gz \cdot Hz)]$ 用 QN：只針對最外層量詞 $(y)$ 做 QN，正確結果為 **$\sim(\exists y)[Fy \supset (\exists z)(Gz \cdot Hz)]$**。

---

### 3. Exercise 9-1、9-3、9-5 & 邏輯小考 (9) 一元述詞證明精選

```text
【Ex 9-1 (1) 雙解法：9 步標準解 vs. 6 步神級觀察（連前提 1, 2 都不用！）】
  1. (x)Fx ∨ (x)~Gx        p                  [6 步另證：直接由前提 3 推出結論！]
  2. ~(x)Fx                p                  4. Dx ⊃ Gx               3 UI
  3. (x)(Dx ⊃ Gx)          p /∴ (∃x)(~Dx ∨ Gx) 5. ~Dx ∨ Gx              4 Impl
  4. (x)~Gx                1, 2 DS            6. (∃x)(~Dx ∨ Gx)        5 EG (Q.E.D.!)
  5. ~Gx                   4 UI
  6. Dx ⊃ Gx               3 UI
  7. ~Dx                   5, 6 MT
  8. ~Dx ∨ Gx              7 Add
  9. (∃x)(~Dx ∨ Gx)        8 EG

【Ex 9-5 (15) 雙解法：使用 IP 證明 1. (x)(Hx ⊃ Kx)  2. (∃x)Hx ∨ (∃x)Kx / ∴ (∃x)Kx】
[證法一：在個體層級導出 Kx · ~Kx]             [證法二：在量詞層級導出 (∃x)Hx · ~(∃x)Hx]
  | 3. ~(∃x)Kx             AP                 | 3. ~(∃x)Kx             AP
  | 4. (∃x)Hx              2, 3 DS            | 4. (∃x)Hx              2, 3 DS
  | 5. (x)~Kx              3 QN               | 5. (x)~Kx              3 QN
  | 6. Hx                  4 EI (先做 EI!)    | 6. ~Kx                 5 UI (完全不用 EI!)
  | 7. Hx ⊃ Kx             1 UI (後做 UI!)    | 7. Hx ⊃ Kx             1 UI
  | 8. Kx                  6, 7 MP            | 8. ~Hx                 6, 7 MT
  | 9. ~Kx                 5 UI               | 9. (x)~Hx              8 UG (x 由 UI 產生，合法 UG!)
  | 10. Kx · ~Kx           8, 9 Conj          | 10. ~(∃x)Hx            9 QN
 11. (∃x)Kx                3–10 IP            | 11. (∃x)Hx · ~(∃x)Hx   4, 10 Conj
                                             12. (∃x)Kx                3–11 IP

【邏輯小考 (9) (2023.12.19) 第 1 題：EG 換變元避免與 EI 衝突的高階技巧！】
證明：1. (∃x)Fx ⊃ (∃x)(Gx · Hx)   2. (∃x)(Hx ∨ Kx) ⊃ (x)Lx  / ∴ (x)(Fx ⊃ Lx)
  | 3. Fx                  AP         (為證全稱條件句，先開 CP 假設 Fx；注意 x 在 AP 中自由出現！)
  | 4. (∃x)Fx              3 EG       (立刻對 Fx 做 EG 湊出前提 1 的前件！)
  | 5. (∃x)(Gx · Hx)       1, 4 MP
  | 6. Gy · Hy             5 EI       (⚠️ 關鍵！因為 x 已經在第 3 列自由出現，此處做 EI 必須換新變元 y！)
  | 7. Hy                  6 Simp
  | 8. Hy ∨ Ky             7 Add
  | 9. (∃x)(Hx ∨ Kx)       8 EG       (用 EG 把自由變元 y 重新拘束為 (∃x)！)
  | 10. (x)Lx              2, 9 MP    (拆下後件 (x)Lx)
  | 11. Lx                 10 UI      (用 UI 將 (x)Lx 代入我們在第 3 列假設的那個 x！)
 12. Fx ⊃ Lx               3–11 CP    (關閉封閉線消去 AP！x 成功解毒，且 x 從未在 EI 列出現過！)
 13. (x)(Fx ⊃ Lx)          12 UG      (合法對 x 做 UG！ Q.E.D.)

【邏輯小考 (9) (2023.12.19) 第 2 題：結合常元 EG、QN、MT、DeM 與 Impl】
證明：1. (∃x)(Ax · ~Bx) ⊃ (y)Cy   2. ~Ca  / ∴ (x)(Ax ⊃ Bx)
  3. (∃y)~Cy               2 EG       (對常元 ~Ca 做 EG 得 (∃y)~Cy)
  4. ~(y)Cy                3 QN       (由 QN 得前提 1 後件的否定 ~(y)Cy)
  5. ~(∃x)(Ax · ~Bx)       1, 4 MT
  6. (x)~(Ax · ~Bx)        5 QN
  7. ~(Ax · ~Bx)           6 UI
  8. ~Ax ∨ ~~Bx            7 DeM
  9. ~Ax ∨ Bx              8 DN
 10. Ax ⊃ Bx               9 Impl
 11. (x)(Ax ⊃ Bx)          10 UG      (Q.E.D.)
```

---

## 第三部分：Ch. 10 多元關係述詞與多重量詞證明題庫全解（Ex 10-10 & Ex 10-11）

> **對應原始檔案**：`raw/Ex_Ch10_關係述詞習題解答.docx`（Ex 10-10 第 1~13 奇數題 & Ex 10-11 第 1~13 奇數題；Ex 10-12 定理證明已完整收錄於 [[述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)]]）

### 1. Exercise 10-10（多量詞關係述詞基礎與進階證明）
```text
【Ex 10-10 (7) — 三量詞順序調換：用 IP + 3 次 QN + 3 次 EI + 2 次 UI】
  1. (∃x)(y)(z)Azyx        p          / ∴ (x)(y)(∃z)Axyz
     | 2. ~(x)(y)(∃z)Axyz  AP         (開啟 IP)
     | 3. (∃x)~(y)(∃z)Axyz 2 QN
     | 4. (∃x)(∃y)~(∃z)Axyz 3 QN
     | 5. (∃x)(∃y)(z)~Axyz 4 QN
     | 6. (∃y)(z)~Axyz     5 EI       (脫去 (∃x) 引進全新變元 x)
     | 7. (z)~Axyz         6 EI       (脫去 (∃y) 引進全新變元 y)
     | 8. (y)(z)Azyu       1 EI       (對前提 1 做 EI：因 x, y 已用過，必須引進全新變元 u！)
     | 9. (z)Azyu          8 UI       (將內層全稱量詞 (y) 代入 y)
     | 10. Axyu            9 UI       (將全稱量詞 (z) 代入 x！得出 Axyu)
     | 11. ~Axyu           7 UI       (對第 7 列將全稱量詞 (z) 代入 u！得出 ~Axyu)
     | 12. Axyu · ~Axyu    10, 11 Conj (完美湊出矛盾！)
 13. (x)(y)(∃z)Axyz        2–12 IP    (Q.E.D.)

【Ex 10-10 (9) — 利用 UI 同變元代入與 Taut 證明反身存在句】
  1. ~(y)(∃x)~(Bxy · Byx)  p          / ∴ (∃x)Bxx
  2. (∃y)~(∃x)~(Bxy · Byx) 1 QN
  3. (∃y)(x)(Bxy · Byx)    2 QN
  4. (x)(Bxy · Byx)        3 EI       (先對外層 (∃y) 做 EI 得 y)
  5. Byy · Byy             4 UI       (關鍵：對全稱量詞 (x) 選擇代入同一個變元 y！)
  6. Byy                   5 Taut     (由重言律化簡為 Byy)
  7. (∃x)Bxx               6 EG       (對兩個 y 同時做 EG 拘束為 (∃x)Bxx！ Q.E.D.)

【Ex 10-10 (13) — 雙 EI 避免變元衝突】
  1. (∃x)(y)Axy            p
  2. (x)(∃y)(Axy ⊃ ~Bxx)   p          / ∴ ~(y)Byy
  3. (y)Axy                1 EI       (先對前提 1 做 EI 引進 x)
  4. (∃y)(Axy ⊃ ~Bxx)      2 UI       (對前提 2 做 UI 代入剛剛的 x)
  5. Axy ⊃ ~Bxx            4 EI       (對第 4 列做 EI 引進全新變元 y)
  6. Axy                   3 UI       (對第 3 列做 UI 代入 y)
  7. ~Bxx                  5, 6 MP
  8. (∃y)~Byy              7 EG
  9. ~(y)Byy               8 QN       (Q.E.D.)
```

---

### 2. Exercise 10-11（結合 CP + EI 換新變元防汙染 + UG 解毒的高階關係證明）

```text
【Ex 10-11 (1) — 在 CP 封閉線內做 EI 必須避開 AP 變元 x，確保 x 不中毒！】
  1. (∃x)[Ax · (y)(Qy ⊃ Lxy)]    p
  2. (x)[Ax ⊃ (y)(Ey ⊃ ~Lxy)]    p    / ∴ (x)(Qx ⊃ ~Ex)
     | 3. Qx                     AP   (假設前件 Qx，準備最後消去 AP 後對 x 做 UG)
     | 4. Az · (y)(Qy ⊃ Lzy)     1 EI (⚠️ 關鍵：x 已在 AP 出現，故對前提 1 做 EI 必須引進新變元 z！如此一來，x 完全沒有在任何 EI 列出現，不會被 EI 下毒！)
     | 5. (y)(Qy ⊃ Lzy)          4 Simp
     | 6. Qx ⊃ Lzx               5 UI (將全稱量詞 y 代入 x)
     | 7. Lzx                    3, 6 MP
     | 8. Az ⊃ (y)(Ey ⊃ ~Lzy)    2 UI (將前提 2 的全稱量詞 x 代入 z)
     | 9. Az                     4 Simp
     | 10. (y)(Ey ⊃ ~Lzy)        8, 9 MP
     | 11. Ex ⊃ ~Lzx             10 UI (將全稱量詞 y 代入 x)
     | 12. ~~Lzx                 7 DN
     | 13. ~Ex                   11, 12 MT
 14. Qx ⊃ ~Ex                    3–13 CP (關閉封閉線消去 AP！x 解毒且從未出現在第 4 列 EI 中！)
 15. (x)(Qx ⊃ ~Ex)               14 UG   (合法對 x 做 UG！ Q.E.D.)

【Ex 10-11 (7) — 含選言、QN 與二元關係的 18 步 CP + UG 證明】
  1. (x)(Ex ∨ Gx)                p
  2. (x)(y)[(~Lx ∨ Mx) ⊃ Nyx]    p    / ∴ (x)[~(∃y)(Gy ∨ Lx) ⊃ (∃z)(Ez · Nzx)]
     | 3. ~(∃y)(Gy ∨ Lx)         AP   (假設前件，自由變元為 x)
     | 4. (y)~(Gy ∨ Lx)          3 QN
     | 5. ~(Gy ∨ Lx)             4 UI (代入新準變元 y，注意此為 UI 而非 EI，故 x 與 y 皆未中毒！)
     | 6. ~Gy · ~Lx              5 DeM
     | 7. (y)[(~Lx ∨ Mx) ⊃ Nyx]  2 UI
     | 8. (~Lx ∨ Mx) ⊃ Nyx       7 UI
     | 9. ~Lx                    6 Simp
     | 10. ~Lx ∨ Mx              9 Add
     | 11. Nyx                   8, 10 MP
     | 12. Ey ∨ Gy               1 UI (將前提 1 的 x 代入 y)
     | 13. ~Gy                   6 Simp
     | 14. Ey                    12, 13 DS
     | 15. Ey · Nyx              14, 11 Conj
     | 16. (∃z)(Ez · Nzx)        15 EG (將 y 存在一般化為 (∃z)！此時第 16 列只剩自由變元 x！)
 17. ~(∃y)(Gy ∨ Lx) ⊃ (∃z)(Ez · Nzx)  3–16 CP (消去 AP，x 解毒！)
 18. (x)[~(∃y)(Gy ∨ Lx) ⊃ (∃z)(Ez · Nzx)]  17 UG (合法對 x 做 UG！ Q.E.D.)

【Ex 10-11 (11) & (13) — 量詞條件句內部帶存在量詞的 CP + EI + EG + UG 標準型】
[Ex 10-11 (11)]                               [Ex 10-11 (13)]
  1. (x)(Ax ⊃ Bx)  p /∴ (x)[(∃y)(Ay·Cxy)⊃(∃z)(Bz·Cxz)]  1. (∃x)Fx ⊃ (x)[Px ⊃ (∃y)Qxy]  p
     | 2. (∃y)(Ay · Cxy)  AP                     2. (x)(y)(Qxy ⊃ Gx)  p /∴ (x)[(Fx·Px)⊃(∃y)Gy]
     | 3. Ay · Cxy        2 EI (⚠️ 注意：x 在第 3 列 EI 列自由出現了嗎？是的！若直接對第 2 列做 EI，x 會在第 3 列被 y 汙染！)
```
> 💡 **【人類介入點 A 重要教學提醒 — Ex 10-11 (11) 與 (13) 的防汙染細節】**：
> 在 `Ex 10-11 (11)` 的第 2 列假設 `(∃y)(Ay · Cxy) [AP]` 後，第 3 列對第 2 列做 `EI` 得 `Ay · Cxy` 時，請注意：**變元 `x` 在第 3 列（這是一個 EI 列！）中自由出現了**！如果按照最嚴格的【UG 限制 2（字面規定：不可對在任何 EI 列中自由出現過的變元做 UG）】，第 11 列對 `x` 做 UG 會有爭議（因為在第 3 列中，`y` 的選擇確實依賴於 `x`）。
> - **為什麼這題在邏輯語意上其實 100% 有效、且第 10 列之後 `x` 不再依賴於 `y`？**
>   因為在第 9 列我們已經用 **EG** 把 `y` 重新拘束進 `(∃z)(Bz · Cxz)` 裡面（把臨時名稱 `y` 消除了），且第 10 列用 **CP** 消去了第 2 列的 AP！在進階自然演繹系統中，只要 EI 引進的變元 `y` 已經被 EG 重新包起來且不留在子結論中，原本只是在 AP 中帶入的 `x` 就不會造成無效推論（或者更無爭議的做法是：在 AP 中先用一個臨時常元或配合 QN + IP 來證）。這一點是理解【UG 限制 2】字面語法規則與語意依賴關係的絕佳進階案例！

---

## 第四部分：Ch. 11 (13) 等同邏輯 (ID 與 IR) 證明實戰

### 運用等同規則 (ID) 與等同反身性 (IR) 的形式證明
- **等同對稱性定理**：$\vdash (x)(y)[(x = y) \supset (y = x)]$
  - `1. x = y [AP]` $\rightarrow$ `2. (z)(z = z) [IR]` $\rightarrow$ `3. x = x [2 UI]` $\rightarrow$ `4. y = x [1, 3 ID]` $\rightarrow$ `5. (x=y) ⊃ (y=x) [1-4 CP]` $\rightarrow$ `6. (y)[(x=y) ⊃ (y=x)] [5 UG]` $\rightarrow$ `7. (x)(y)[(x=y) ⊃ (y=x)] [6 UG]`。
