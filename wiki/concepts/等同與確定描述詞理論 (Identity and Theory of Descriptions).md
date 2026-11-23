---
title: "等同與確定描述詞理論 (Identity and Theory of Descriptions)"
category: concepts
chapters: ["Ch. 11 (Textbook Ch. 13)"]
tags: [logic, concept, identity, definite-descriptions, russell, numerical-quantifiers, relations]
updated: 2026-11-22
---

# 等同與確定描述詞理論 (Identity and Theory of Descriptions)

> **所屬章節**：[[Ch11 等同與確定描述詞 (Identity and Definite Descriptions)]]
> **對應方法**：[[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]（含 ID 與 IR 規則）
> **對應練習**：[[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]]、[[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]

一階述詞邏輯加上**等同關係 (Identity, `=`)** 後，成為完整的**一階等同述詞邏輯 (First-Order Logic with Identity)**。它不僅解決了自然語言中「是 (is)」的歧義與精確數量計數問題，更催生了伯特蘭·羅素（Bertrand Russell）著名的**確定描述詞理論 (Theory of Definite Descriptions)**，被譽為二十世紀分析哲學的典範（Paradigm of Philosophy）。

---

## 1. 「是 (Be)」的兩種邏輯功能與萊布尼茲定律

在自然語言中，「是 (is)」至少承載了兩種截然不同的邏輯結構（此外還有「所有人是動物」的類別包含關係 $\supset$）：

| 邏輯功能 | 意義說明 | 講義範例 | 符號化形式 | 邏輯性質 |
| :--- | :--- | :--- | :---: | :--- |
| **1. 斷言屬性功能**<br>(Predicating Function) | 將某種普遍性質（Property）歸屬於某個特定個體 | 「金庸是小說家」<br>「蘇格拉底是聰明的」 | **$Nj$**<br>**$Ws$** | 不具對稱性（不能反過來說「小說家是金庸」） |
| **2. 等同功能**<br>(Identity Function) | 斷言兩個專名或描述詞指稱**論域中的同一個對象** | 「金庸是查良鏞」<br>「晨星就是暮星」 | **$j = c$**<br>**$m = e$** | 具**全反身性** ($x=x$)、**對稱性** ($x=y \supset y=x$) 與**遞移性** |

- **不可辨識者的同一性 / 萊布尼茲定律 (Leibniz's Law)**：
  - 若 $u = w$（$u$ 與 $w$ 是同一個對象），則 $u$ 所擁有的任何性質，$w$ 也必然擁有。這正是自然演繹法中**等同規則 (Rule of Identity, ID)** 與**等同反身性規則 (IR)** 的哲學基礎。

---

## 2. 數量詞 (Numerical Quantifiers) 的構造邏輯

在純述詞邏輯中，$(\exists x)(\exists y)(Fx \cdot Fy)$ **並不能**保證至少有兩個 $F$，因為當論域中只有一個個體 $a$ 具有性質 $F$ 時，令 $x=a$ 且 $y=a$，$Fa \cdot Fa$ 依然為真！因此，**計數的關鍵在於利用 $x \neq y$ 區分相異個體，以及利用 $x = y$ 限制個體數量上限**：

### (1) 「至少 $n$ 個」(At least $n$) —— 用存在量詞 $(\exists)$ + 不等同 $(x \neq y)$
- **至少 1 個 $F$**：$(\exists x)Fx$
- **至少 2 個 $F$**：$(\exists x)(\exists y)[(Fx \cdot Fy) \cdot (x \neq y)]$
- **至少 3 個 $F$**：$(\exists x)(\exists y)(\exists z)[(Fx \cdot Fy \cdot Fz) \cdot (x \neq y) \cdot (x \neq z) \cdot (y \neq z)]$

### (2) 「至多 $n$ 個」(At most $n$) —— 用全稱量詞 $(x)$ + 等同 $(x = y)$
> 💡 **為什麼「至多 1 個」不能用存在量詞 $(\exists x)$ 開頭？**
> 因為當論域中**有 0 個 $F$** 時，「至多有 1 個 $F$」在邏輯上是**真 (True)** 的！若用 $(\exists x)Fx$ 開頭，0 個 $F$ 時就會變成假。
- **至多 1 個 $F$**：
  $$(x)[Fx \supset (y)(Fy \supset (x = y))] \quad \text{或} \quad (x)(y)[(Fx \cdot Fy) \supset (x = y)]$$
  *(直譯：如果 $x$ 是 $F$ 且 $y$ 也是 $F$，那麼 $x$ 跟 $y$ 必定是同一個東西！)*
- **至多 2 個 $F$**：
  $$(x)(y)(z)\{[(Fx \cdot Fy) \cdot Fz] \supset [(x = y) \lor (x = z) \lor (y = z)]\}$$
  *(直譯：任取三個是 $F$ 的東西，其中至少有兩個必定是同一個東西！)*

### (3) 「恰好 $n$ 個」(Exactly $n$) —— 「至少 $n$ 個」$\cdot$「至多 $n$ 個」的連言濃縮
- **恰好 1 個 $F$ (Exactly one $F$)**：
  $$(\exists x)[Fx \cdot (y)(Fy \supset (x = y))] \quad \text{或等價寫為} \quad (\exists x)\{Fx \cdot (y)[(x \neq y) \supset \sim Fy]\}$$
  *(直譯：存在一個 $x$ 是 $F$，而且任何是 $F$ 的 $y$ 都等於這個 $x$ [或者：任何不等於 $x$ 的 $y$ 都不是 $F$]。)*

---

## 3. 羅素的確定描述詞理論 (Russell's Theory of Definite Descriptions)

### (1) 哲學難題：空指稱確定描述詞 (Non-referring Definite Descriptions)
- 考慮句子：「**現任法國國王是禿頭 (The present King of France is bald)**」。
- 如果按照表面文法，把「現任法國國王」當作一個個體常元 $k$，符號化為 $Bk$：
  - 因為 1905 年（及今日）法國是共和國，根本沒有國王，常元 $k$ 指稱不到任何對象！
  - 更糟的是，根據排中律 $Bk \lor \sim Bk$，「現任法國國王是禿頭」與「現任法國國王不是禿頭」必有一真，難道我們要在禿頭名單或不禿頭名單裡找到現任法國國王嗎？（邁農 Meinong 甚至因此被迫承認「不存在的對象也有某種存有」）。

### (2) 羅素的消解方案：確定描述詞不是常元，而是隱藏的量化複合主張！
羅素在 1905 年名篇〈論指稱 (*On Denoting*)〉中指出，任何包含確定描述詞「那位唯一的 $F$ 是 $G$（The $F$ is $G$）」的語句，其真實邏輯形式都由**三個連言條件**構成：

$$\underbrace{(\exists x)\Big\{ \big[ Fx}_{\text{(1) 存在性：至少有一個 } F} \cdot \underbrace{(y)(Fy \supset (x = y)) \big]}_{\text{(2) 唯一性：至多只有一個 } F} \cdot \underbrace{Gx}_{\text{(3) 屬性：該個體是 } G} \Big\}$$

- 以此檢驗「現任法國國王是禿頭」：因為第 (1) 項「存在至少一位現任法國國王」為**假 (F)**，整個存在連言句直接判定為**假 (False)**！完全不需要假設某個虛幻的法國國王存在。

### (3) 否定句的範圍歧義：內部否定 vs. 外部否定
那麼「**現任法國國王不是禿頭 (The present King of France is not bald)**」是真還是假？羅素指出這句日常語言有**否定號管轄範圍 (Scope of Negation)** 的歧義：

| 否定類型 | 羅素術語 | 符號化公式 | 白話真值條件 | 真假值判定 |
| :--- | :--- | :--- | :--- | :---: |
| **1. 狹義範圍否定**<br>(內部否定 / 否定述詞) | 確定描述詞具**主要出現**<br>(Primary Occurrence) | **$(\exists x)\{[Kx \cdot (y)(Ky \supset (x = y))] \cdot \sim Bx\}$** | **存在**一位唯一的現任法國國王，而且他**不是禿頭**（有頭髮） | **假 (False)**<br>*(因為根本沒有法國國王)* |
| **2. 廣義範圍否定**<br>(外部否定 / 否定整句) | 確定描述詞具**次要出現**<br>(Secondary Occurrence) | **$\sim(\exists x)\{[Kx \cdot (y)(Ky \supset (x = y))] \cdot Bx\}$** | **並非**（存在一位唯一的現任法國國王且他是禿頭） | **真 (True)**<br>*(因為「現任法國國王是禿頭」為假，其否定必為真！)* |

> **哲學洞見**：在廣義範圍否定（外部否定）下，「現任法國國王是禿頭 ($\phi$)」為 **F**，而「並非：現任法國國王是禿頭 ($\sim \phi$)」為 **T**，排中律 $\phi \lor \sim \phi$ 完全不會被違反！

---

## 4. 相關概念與方法連結

- **前導概念**：[[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]]
- **推論規則應用**：在自然演繹法中使用等同規則 **ID** 與 **IR** $\implies$ [[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]
- **三階段邏輯系統比較**：[[語句邏輯與述詞邏輯的演進與比較 (Evolution from Sentential to Predicate and Identity Logic)]]
- **實戰演練**：[[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]]、[[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]
