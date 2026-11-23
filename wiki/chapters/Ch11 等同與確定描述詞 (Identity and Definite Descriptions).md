---
title: "Ch11 等同與確定描述詞 (Identity and Definite Descriptions)"
category: chapters
chapter: "Ch. 11 (Textbook Ch. 13)"
source: "Ch_11_等同與確定描述詞.docx / Hausman Ch. 13"
tags: [logic, chapter, identity, numerical-quantifiers, definite-descriptions, russell, relations]
updated: 2026-11-22
---

# Ch11 等同與確定描述詞 (Identity and Definite Descriptions)

> **對應原始講義**：`raw/Ch_11_等同與確定描述詞.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 13)（輔）

在純粹的一階述詞邏輯（[[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] ~ [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]]）中，我們只有「所有 $(x)$」與「存在至少一個 $(\exists x)$」，無法區分兩個名稱或變元指稱的是「同一個個體」還是「兩個不同的個體」。本章引入**等同關係 (Identity, `=`)**，使述詞邏輯得以精確表達「除了……之外」、「至少 $n$ 個」、「至多 $n$ 個」、「恰好 $n$ 個」，並呈現二十世紀分析哲學最著名的里程碑——**羅素（Bertrand Russell）的確定描述詞理論 (Theory of Definite Descriptions)**。

---

## 1. 核心架構與知識節點

### 11-1 等同關係 (`=`) 與兩條等同推論規則
- **[[等同與確定描述詞理論 (Identity and Theory of Descriptions)]]**
  - **「是 (is / be)」的兩種邏輯功能區分**：
    1. **斷言屬性功能 (Predicating Function)**：將某個性質歸屬於某個體，使用「一元述詞 + 個體常元」符號化。
       - 例：「金庸是小說家」$\implies Nj$。
    2. **等同功能 (Identity Function)**：斷言兩個名稱或描述詞指稱**論域中同一個對象 (Co-referential)**，使用二元關係符號 **`=`** 符號化。
       - 例：「金庸是查良鏞」$\implies j = c$；「金庸不是古龍」$\implies \sim(j = g)$ 或 $j \neq g$。
  - **兩條等同推論規則（加入自然演繹系統）**：
    1. **等同規則 (Rule of Identity, ID)**（又稱不可辨識者的同一性 / 萊布尼茲定律 Leibniz's Law 的推論形式）：
       $$\frac{(\dots u \dots), \quad u = w \text{ (或 } w = u \text{)}}{\therefore (\dots w \dots)}$$
       - 若 $u$ 與 $w$ 等同（不論前提順序是 $u=w$ 或 $w=u$，因為等同具對稱性），則可將另一列中**一或多個**自由出現的 $u$ 替換為 $w$。
    2. **等同反身性規則 (Identity Reflexivity, IR)**：
       $$\vdash (x)(x = x) \quad \text{或直接引進} \quad u = u$$
       - 任何東西皆與自身等同。這是一條**零前提規則**，可在證明的任何一步直接引進 $(x)(x = x)$（再由 UI 得 $a = a$），確保等同邏輯系統具有完備性。

### 11-2 數量詞的符號化 (Numerical Quantifiers)
- 為什麼在沒有 `=` 時，$(\exists x)(\exists y)(Sx \cdot Sy)$ **不能**表達「至少有兩個學生」？因為不同的變元 $x$ 與 $y$ 在論域中完全可以指稱**同一個個體**！必須明確加上 **$(x \neq y)$** 才能保證是兩個相異個體。

| 數量命題類型 | 例句（$Sx$：$x$ 是學生） | 標準符號化公式 | 邏輯結構與注意事項 |
| :--- | :--- | :--- | :--- |
| **至少一個**<br>(At least one) | 至少有一個學生 | **$(\exists x)Sx$** | 標準存在量詞 |
| **至少兩個**<br>(At least two) | 至少有兩個學生 | **$(\exists x)(\exists y)[(Sx \cdot Sy) \cdot (x \neq y)]$** | 必須加上 $x \neq y$；至少三個則需 $x \neq y \cdot x \neq z \cdot y \neq z$ |
| **至多一個**<br>(At most one) | 至多有一個學生 | **$(x)[Sx \supset (y)(Sy \supset (x = y))]$**<br>或 $(x)(y)[(Sx \cdot Sy) \supset (x = y)]$ | **使用全稱量詞**！因為當論域中「有 0 個學生」時，「至多一個學生」亦為**真** |
| **恰好一個**<br>(Exactly one) | 恰好有一個學生 | **$(\exists x)[Sx \cdot (y)(Sy \supset (x = y))]$** | 結合「至少一個 ($Sx$)」與「至多一個 ($(y)(Sy \supset x=y)$)」 |
| **恰好兩個**<br>(Exactly two) | 恰好有兩個學生 | **$(\exists x)(\exists y)\{(Sx \cdot Sy) \cdot (x \neq y) \cdot (z)[Sz \supset ((z=x) \lor (z=y))]\}$** | 存在相異兩個 $x, y$，且任何學生 $z$ 都必等於 $x$ 或 $y$ |
| **除外命題**<br>(Only / Everyone but) | 班上除了 George 之外都及格（只有 George 不及格） | **$Sg \cdot \sim Pg \cdot (x)[(Sx \cdot (x \neq g)) \supset Px]$** | (1) $g$ 是學生且不及格；(2) 所有**不等於 $g$** 的學生都及格 |

### 11-3 確定描述詞 (Definite Descriptions —— Russell's Theory of Descriptions)
- **什麼是確定描述詞 (Definite Description)**？
  - 以定冠詞「The...」開頭、旨在唯一指稱某個特定個體的詞組（例如：「現任美國總統」、「《射鵰英雄傳》的作者」、「現任法國國王」）。
- **羅素（Bertrand Russell, 1905〈論指稱 *On Denoting*〉）的經典三合一分析**：
  - 表面文法看似簡單的「主詞—述詞」語句，如「現任美國總統有宗教信仰」（或「現任法國國王是禿頭 The present King of France is bald」），在深層邏輯形式上**並不是單純的 $Ba$**，而是同時斷言了**三個連言主張**：
    1. **存在性 (Existence)**：存在至少一位現任法國國王；
    2. **唯一性 (Uniqueness)**：至多只有一位現任法國國王；
    3. **屬性斷言 (Predication)**：這個唯一的人是禿頭。
  - **羅素確定描述詞標準公式**：
    $$(\exists x)\{[Kx \cdot (y)(Ky \supset (x = y))] \cdot Bx\}$$
- **否定確定描述詞的範圍歧義（Primary vs. Secondary Occurrence）**：
  - 當我們說「現任法國國王不是禿頭 (The present King of France is not bald)」時，因為現實中法國已無國王（$Kx$ 為空），這句話是真還是假？羅素指出它有兩種不同邏輯形式：
    1. **狹義範圍否定 / 內部否定（確定描述詞具主要出現 Primary Occurrence）**：
       $$(\exists x)\{[Kx \cdot (y)(Ky \supset (x = y))] \cdot \sim Bx\}$$
       - 斷言「**存在**一位唯一的現任法國國王，而且他不是禿頭」$\implies$ 因為法國沒有國王，此句為**假 (False)**！
    2. **廣義範圍否定 / 外部否定（確定描述詞具次要出現 Secondary Occurrence）**：
       $$\sim(\exists x)\{[Kx \cdot (y)(Ky \supset (x = y))] \cdot Bx\}$$
       - 斷言「**並非**（存在一位唯一的現任法國國王且他是禿頭）」$\implies$ 因為確實不存在禿頭的法國國王，此句為**真 (True)**！
  - 羅素藉此完美解決了困擾哲學界長達兩千年的「空指稱詞項（Non-referring terms）與排中律」難題。

### 13-3 二元關係的形式性質 (Properties of Two-Place Relations)（原文書 Ch.13 補充）
- 設 $Rxy$ 為二元關係述詞（等同關係 `=` 即是同時具備對稱性、遞移性與全反身性的等價關係）：
  1. **對稱性 (Symmetry)**：
     - **對稱 (Symmetrical)**：$(x)(y)(Rxy \supset Ryx)$（例：「與……是同學」、「等於」）
     - **非對稱 (Asymmetrical)**：$(x)(y)(Rxy \supset \sim Ryx)$（例：「比……年長」、「是……的父親」）
     - **不對稱 (Nonsymmetrical)**：既非對稱亦非非對稱（例：「愛 $Lxy$」）
  2. **遞移性 (Transitivity)**：
     - **遞移 (Transitive)**：$(x)(y)(z)[(Rxy \cdot Ryz) \supset Rxz]$（例：「大於」、「在……之北」）
     - **反遞移 (Intransitive)**：$(x)(y)(z)[(Rxy \cdot Ryz) \supset \sim Rxz]$（例：「是……的親生母親」）
     - **不遞移 (Nontransitive)**：既非遞移亦非反遞移（例：「是……的朋友」）
  3. **反身性 (Reflexivity)**：
     - **全反身 (Totally Reflexive)**：$(x)Rxx$（例：「等於 $x=x$」）
     - **反身 (Reflexive)**：$(x)(y)(Rxy \supset [Rxx \cdot Ryy])$
     - **反反身 (Irreflexive)**：$(x)\sim Rxx$（任何非對稱關係必然是反反身的！）

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **承接與擴充** | [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] | 在 $(x)$ 與 $(\exists x)$ 之上加入 `=`，使量詞能精確計數並表達唯一性 |
| **承接與擴充** | [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]] | 在 18 條 SL 規則 + CP/IP + 4 條量詞規則 + QN 之上，加入 **ID** 與 **IR** 完成一階等同邏輯系統 |
| **深化概念** | [[等同與確定描述詞理論 (Identity and Theory of Descriptions)]] | 深入剖析羅素確定描述詞三要素、內外部否定歧義、數量詞模板與關係性質 |
| **綜合比較** | [[語句邏輯與述詞邏輯的演進與比較 (Evolution from Sentential to Predicate and Identity Logic)]] | 總結從「語句邏輯 (SL) $\rightarrow$ 一階述詞邏輯 (PL) $\rightarrow$ 等同與描述詞邏輯 (PL+=)」的三階段表達力躍遷 |
| **實戰練習** | [[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]] | 對應數量詞（至少/至多/恰好）、除外句與確定描述詞符號化習題 |
| **實戰練習** | [[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]] | 對應運用 ID 與 IR 進行等同邏輯形式證明之習題 |
