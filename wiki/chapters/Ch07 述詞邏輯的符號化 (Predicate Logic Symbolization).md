---
title: "Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)"
category: chapters
chapter: "Ch. 7"
source: "Ch_07_述詞邏輯_述詞邏輯的符號化.docx / Hausman Ch. 7"
tags: [logic, chapter, predicate-logic, quantifiers, square-of-opposition, existential-import, expansion]
updated: 2026-11-22
---

# Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)

> **對應原始講義**：`raw/Ch_07_述詞邏輯_述詞邏輯的符號化.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 7 & Ch. 10)（輔）

在語句邏輯（SL）中，經典亞里斯多德三段論「所有人都會死，孔子是人 $\therefore$ 孔子會死」只能被符號化為三個毫無關聯的原子語句 $A, B / \therefore C$，被判定為在 SL 無效！這顯示 SL 的解析度不足。本章進入**述詞邏輯 / 量詞邏輯 (Predicate Logic / Quantifier Logic, PL)**，深入拆解原子語句內部的「個體 (Individuals)」、「性質/關係 (Properties/Relations)」與「量詞 (Quantifiers)」。

---

## 1. 核心架構與知識節點

### 7-1 ~ 7-4 個體、述詞、量詞、論域與變元拘束
- **[[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]]**
  - **個體常元 (Individual Constants, $a, b, c \dots t$)**：指稱論域中特定的具體個體（如 $c =$ 孔子）。
  - **個體變元 (Individual Variables, $u, v, w, x, y, z$)**：代表任意個體的變元空位。
  - **性質常元 / 述詞 (Property Constants / Predicates, $F, G, H \dots$)**：
    - **一元述詞 (Monadic Predicate)**：表單一個體的屬性（如 $Hx$：$x$ 是人）。
    - **多元關係述詞 (Relational Predicate)**：表兩個以上個體間的關係（如二元關係 $Lxy$：$x$ 愛 $y$；三元關係 $Bxyz$：$x$ 在 $y$ 與 $z$ 之間）。注意個體順序不可隨意對調（$Lab \neq Lba$）。
  - **兩大量詞 (Quantifiers)** 與 **論域 (Domain of Discourse, $D$)**：
    1. **全稱量詞 (Universal Quantifier)**：記為 **$(x)$**（或 $\forall x$），意為「對論域中所有的 $x$ 而言」。
    2. **存在量詞 (Existential Quantifier)**：記為 **$(\exists x)$**，意為「在論域中存在至少一個 $x$ 使得」。
  - **自由變元 (Free Variable)** vs. **拘束變元 (Bound Variable)**：
    - 在同名量詞管轄範圍（Scope）內的變元為**拘束變元**；不在任何同名量詞管轄範圍內的變元為**自由變元**。
    - **含有自由變元的式子（如 $Fx \supset Gx$）只是「語句形式 / 開語句 (Open Sentence)」，沒有真假值**；唯有所有變元皆被拘束或皆為常元，才是完整的**語句 (Sentence)**。

### 7-5 & 7-6 四大定言命題 (A, E, I, O) 與對當方陣 (Square of Opposition)

| 命題代號 | 日常語言標準型 | 述詞邏輯標準符號化 | 量詞否定 (QN) 等值式 | 范恩圖 (Venn Diagram) 表達 |
| :---: | :--- | :---: | :---: | :--- |
| **A 命題** (全稱肯定) | 所有 $S$ 都是 $P$<br>(All $S$ are $P$) | **$(x)(Sx \supset Px)$** | $\sim(\exists x)(Sx \cdot \sim Px)$ | 將 $S \setminus P$ 區域塗黑（代表空集 $\emptyset$） |
| **E 命題** (全稱否定) | 沒有 $S$ 是 $P$<br>(No $S$ are $P$) | **$(x)(Sx \supset \sim Px)$** | $\sim(\exists x)(Sx \cdot Px)$ | 將 $S \cap P$ 交集區域塗黑（代表空集 $\emptyset$） |
| **I 命題** (特稱肯定) | 有些 $S$ 是 $P$<br>(Some $S$ are $P$) | **$(\exists x)(Sx \cdot Px)$** | $\sim(x)(Sx \supset \sim Px)$ | 在 $S \cap P$ 交集區域畫上 **$X$**（代表非空） |
| **O 命題** (特稱否定) | 有些 $S$ 不是 $P$<br>(Some $S$ are not $P$) | **$(\exists x)(Sx \cdot \sim Px)$** | $\sim(x)(Sx \supset Px)$ | 在 $S \setminus P$ 區域畫上 **$X$**（代表非空） |

- **兩大初學必考鐵律**：
  1. **全稱量詞 $(x)$ 永遠搭配條件句 $\supset$，存在量詞 $(\exists x)$ 永遠搭配連言 $\cdot$**！
     - 絕不可將「所有人都是會死的」譯為 $(x)(Hx \cdot Mx)$（這會荒謬地斷言「宇宙中萬事萬物都是人而且都會死」）。
     - 絕不可將「有些人是聰明的」譯為 $(\exists x)(Hx \supset Sx)$（只要世上有一顆石頭不是人，前件 $Ha$ 為假，該式就會無條件為真！）。
  2. **全部否定 (No $S$ are $P$)** vs. **部分否定 (Not all $S$ are $P$)**：
     - 「沒有人怕死」是 **E 命題**：$(x)(Px \supset \sim Fx)$。
     - 「並非每個人都怕死」是 **O 命題**：$\sim(x)(Px \supset Fx) \equiv (\exists x)(Px \cdot \sim Fx)$。
- **存在意涵 (Existential Import) 與現代對當方陣的崩解**：
  - **傳統亞里斯多德邏輯**預設主詞集合 $S$ 非空（具有存在意涵），因此 A 與 E 具有反對關係（不可同真）、I 與 O 具有下反對關係（不可同假）、A 可推導 I、E 可推導 O（差等關係）。
  - **現代形式邏輯不預設全稱命題具有存在意涵**！若論域中根本沒有任何 $S$（例如 $Sx$：$x$ 是獨角獸 / 恐龍），則對於所有 $x$，$Sx$ 皆為 **F**，導致 **A 命題 $(x)(Sx \supset Px)$ 與 E 命題 $(x)(Sx \supset \sim Px)$ 因前件為假而同時為真 (Vacuously True)，且 I 命題與 O 命題同時為假**！
  - 因此，在現代述詞邏輯的對當方陣中，**只剩下兩條對角線的「矛盾關係 (Contradictories)」（A 與 O 矛盾、E 與 I 矛盾）依然成立**，反對、下反對、差等關係全部失效！

### 7-7 ~ 7-9 模型論域展開式與進階翻譯陷阱
- **有限模型論域展開式 (Model Universe Expansion)**：
  - 在有限論域 $D = \{a, b, c\}$ 中：
    - 全稱語句 $(x)Fx$ 的展開式為連言：**$(Fa \cdot Fb) \cdot Fc$**
    - 存在語句 $(\exists x)Fx$ 的展開式為選言：**$(Fa \lor Fb) \lor Fc$**
  - **哲學洞見**：量限語句與其展開式在邏輯上**不等值**（因為展開式並未聲明「$a, b, c$ 已經窮盡所有個體」，且無限論域無法寫出有限展開式），但展開式提供了檢驗複雜翻譯是否正確的極佳工具！
  - **經典檢驗案例：「若任何人移動，橋就會倒」vs.「若所有人都移動，橋才會倒」**：
    - 「若任何人（有人）移動，橋就會倒」：只要 $a$ 或 $b$ 其中一人移動橋就倒 $\implies (Ma \supset B) \cdot (Mb \supset B)$，對應 **$(x)(Mx \supset B)$**，邏輯等值於 **$(\exists x)Mx \supset B$**（**定理 Q17**：量詞從前件移出括弧外時，$(x)$ 與 $(\exists x)$ 必須互換！）。
    - 「若所有人都移動，橋才會倒」：必須所有人同時移動橋才倒 $\implies (Ma \cdot Mb) \supset B \equiv (Ma \supset B) \lor (Mb \supset B)$，對應 **$(x)Mx \supset B$**，邏輯等值於 **$(\exists x)(Mx \supset B)$**（**定理 Q18**）。
- **主詞中的「和 (and)」常代表聯集選言 $\lor$**：
  - 「婦女和兒童可免兵役」意思是「凡是婦女**或**兒童皆免役」：**$(x)[(Wx \lor Cx) \supset Ex] \equiv (x)(Wx \supset Ex) \cdot (x)(Cx \supset Ex)$**。若誤譯為 $(x)[(Wx \cdot Cx) \supset Ex]$，會變成「同時既是婦女又是兒童的人才能免役」！
- **Only / None but / Unless 在述詞邏輯中的符號化**：
  - 「**只有 A 是 B (Only A's are B's)**」=「**除了 A 之外沒有東西是 B (None but A's are B's)**」=「**除非是 A，否則不是 B (Nothing is B unless it is A)**」：
  - 全部翻譯為：**$(x)(Bx \supset Ax)$**（A 是 B 的必要條件！例如「只有用功的學生才會及格」譯為 $(x)(Px \supset Sx)$）。

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **承接與突破** | [[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]] | 突破 SL 無法剖析原子語句內部主述結構的限制，引入個體、述詞與量詞 |
| **深化概念** | [[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]] | 完整圖解 A/E/I/O、范恩圖、現代對當方陣崩解與定理 Q17/Q18 |
| **向後延伸** | [[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]] | 利用本章 7-8 的有限論域展開式，在 Ch.8 發展出證明 PL 無效性的展開式反例法 |
| **向後延伸** | [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]] | 將 A/E/I/O 的對角線矛盾關係正式化為雙向等值的量詞否定規則 (QN) |
| **向後延伸** | [[Ch11 等同與確定描述詞 (Identity and Definite Descriptions)]] | 在 $(x)$ 與 $(\exists x)$ 基礎上加入等同號 `=`，以表達「至少兩個、至多一個、恰好一個」與羅素確定描述詞 |
| **綜合定理** | [[述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)]] | 統整量詞對連詞分配律（Q1~Q10）、量詞進出括弧定理（Q11~Q22，含橋倒定理 Q17/Q18）與多重量詞交換定理（Q34~Q55） |
| **實戰練習** | [[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]] | 對應 Ex 7-3 ~ Ex 7-11、邏輯小考 5、部分否定 vs. 全部否定補充、以及 Ch.10 多元關係述詞 Ex 10-1 ~ Ex 10-6 符號化全解 |
