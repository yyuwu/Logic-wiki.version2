---
title: "習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)"
category: exercises
chapters: ["Ch. 7", "Ch. 10 (Relational Predicate Logic)", "Ch. 11 (Textbook Ch. 13)"]
source: "Ex_Ch07_習題解答.docx, Ex_Ch10_關係述詞習題解答.docx, Quiz5_Ch07_邏輯小考5解答_20241205_述詞符號化.docx, Supp_Ch07_補充一/二_部分否定與全部否定.docx, Supp_Ch07_Ch09_Ex10-6_複雜關係述詞符號化與定理Q17補充.docx"
tags: [logic, exercise, predicate-logic, symbolization, quantifiers, partial-negation, relational-predicates, numerical-quantifiers, definite-descriptions, russell]
updated: 2026-11-23
---

# 習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)

> **涵蓋章節**：[[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]]、[[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]]（含原文書 Ch. 10 多量詞關係述詞）、[[Ch11 等同與確定描述詞 (Identity and Definite Descriptions)]]
> **對應原始題庫檔案**：`raw/Ex_Ch07_習題解答.docx`（Ex 7-3 ~ Ex 7-11 全解）、`raw/Quiz5_Ch07_邏輯小考5解答_20241205_述詞符號化.docx`、`raw/Ex_Ch10_關係述詞習題解答.docx`（Ex 10-1 ~ Ex 10-6 關係述詞符號化與展開式）、`raw/Supp_Ch07_補充一_部份否定與全部否定.docx`、`raw/Supp_Ch07_補充二_部分否定全部否定和雙重否定的翻譯.docx`、`raw/Supp_Ch07_Ch09_Ex10-6_複雜關係述詞符號化與定理Q17補充.docx`
> **對應概念**：[[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]]、[[等同與確定描述詞理論 (Identity and Theory of Descriptions)]]、[[述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)]]

本頁完整收錄並解析 Ch. 7 一元述詞符號化（Ex 7-3 至 Ex 7-11 及邏輯小考 5）、Ch. 10 多元關係述詞與時間/空間多重量詞符號化（Ex 10-1 至 Ex 10-6）、以及 Ch. 11 等同、數量詞與羅素確定描述詞題庫。

---

## 第一部分：Ch. 7 一元述詞邏輯符號化題庫全解（Ex 7-3 ~ Ex 7-11 & 邏輯小考 5）

### 1. Exercise 7-3、7-4、7-5 標準符號化解答（對應 `raw/Ex_Ch07_習題解答.docx`）

```text
【Exercise 7-3 全稱與否定】                    【Exercise 7-4 全稱與複合條件句】
(1) (x)(Ex ⊃ Cx)                               (1) (x)(Px ⊃ Ix)
(3) ~(x)(Ex ⊃ Cx)                              (3) ~(x)(Px ⊃ Ix)
(5) (x)[(Nx · Ex) ⊃ Cx]                        (5) Ib ⊃ ~(x)(Px ⊃ ~Ix)
(7) (x)[(~Nx · Ex) ⊃ ~Cx]                      (7) (x)(Sx ⊃ Lx)
    或 ~(∃x)[(~Nx · Ex) · Cx]                  (9) ~(x)(Sx ⊃ Lx)
(9) (x)[(Nx · Ex) ⊃ Cx]                        (11) (x)(Sx ⊃ Lx) ⊃ (x)(Sx ⊃ ~Px)
    或 ~(∃x)[(Nx · Ex) · ~Cx]                       或 (x)(Sx ⊃ Lx) ⊃ ~(∃x)(Sx · Px)
(11) (x)[Mx ⊃ (~Nx · Ex)]                      (13) ~(x)(~Px ⊃ ~Lx)
(13) ~(∃x)(~Cx · Ex) · (∃x)(Ex · Mx)           (15) ~La ⊃ ~[(x)(Sx ⊃ Lx) ∨ (x)(~Px ⊃ Lx)]
     或 (x)(Ex ⊃ Cx) · ~(x)(Ex ⊃ ~Mx)

【Exercise 7-5 存在量詞與複合連言】
(1) (∃x)(Ax · Ox)                              (9) (∃x)(Ax · ~Px) · (∃x)(Ax · ~Tx)
(3) ~(∃x)(Ax · Ox)                             (11) (∃x)(Rx · Dx)
(5) (∃x)(Ex · ~Ox)                             (13) (x)[(Rx · Dx) ⊃ ~Fx] 或 ~(∃x)[Rx · (Dx · Fx)]
(7) (∃x)[Ax · (Px · Tx)]                       (15) (∃x){Rx · [(Sx · Dx) · ~Fx]} · {(∃x)[Rx · (Fx · ~Dx)] · (∃x)(Rx · ~Sx)}
```

---

### 2. Exercise 7-6：自然語言主詞分類、聯集選言與形容詞拆解限制
- **(1)** *"All marsupials have pouches."* ($Mx =$ "$x$ is a marsupial", $Px =$ "$x$ has a pouch") $\implies$ **$(x)(Mx \supset Px)$**
- **(3)** *"Not all marsupials have pouches."*（部分否定） $\implies$ **$\sim(x)(Mx \supset Px)$**
- **(5)** *"Kangaroos and opossums are marsupials."*（袋鼠和負鼠都是有袋動物 —— 主詞中的 `and` 表兩類聯集 $\lor$！） $\implies$ **$(x)[(Kx \lor Ox) \supset Mx]$** 或 **$(x)(Kx \supset Mx) \cdot (x)(Ox \supset Mx)$**
- **(7)** *"Koala bears are not bears."*（無尾熊不是熊 —— 全部否定 E 命題） $\implies$ **$(x)(Kx \supset \sim Bx)$**
- **(9)** *"Some marsupials inhabit their natural habitats in Australia and North America."*（有些有袋動物棲息在澳洲，且有些棲息在北美） $\implies$ **$(\exists x)(Mx \cdot Ax) \cdot (\exists x)(Mx \cdot Nx)$**
- **(11)** *"Female marsupials have pouches, but male marsupials do not."* $\implies$ **$(x)[(Mx \cdot Fx) \supset Px] \cdot (x)[(Mx \cdot Yx) \supset \sim Px]$**
- **(13)** *"Patient physicians have plenty of patients."* ($Fx =$ "$x$ is a physician", $Px =$ "$x$ is patient [有耐心的]", $Hx =$ "$x$ has plenty of patients [有很多病人]") $\implies$ **$(x)[(Fx \cdot Px) \supset Hx]$**
- **(15)** *"Anyone who cheats feels guilty, or should feel guilty."* $\implies$ **$(x)[Cx \supset (Gx \lor Sx)]$**
- **(17)** *"Girl Scouts and Boy Scouts are to be congratulated by President Obama."* $\implies$ **$(x)[(Gx \lor Bx) \supset Cx]$** 或 **$(x)(Gx \supset Cx) \cdot (x)(Bx \supset Cx)$**
- **(19)** *"Dignitaries from China and Japan will meet with President Obama."* $\implies$ **$(\exists x)(Ox \cdot Cx) \cdot (\exists x)(Ox \cdot Jx)$**

---

### 3. Exercise 7-7 & Exercise 7-8：公式回譯中文與有限論域 $D=\{a, b\}$ 展開式
- **Exercise 7-7（將述詞邏輯公式精準翻譯回自然語言）**：
  - **(1)** 有些電視主播有優雅的人格。
  - **(3)** 沒有電視主播是政治專家。
  - **(5)** 並非所有電視主播都是政治專家。
  - **(7)** 有些電視主播並非既是有優雅的人格也是政治專家。（或：有些電視主播不具有優雅的人格，或者有些電視主播不是政治專家。）
  - **(9)** 如果所有電視主播都是政治專家，則 Barbara Walters 不是電視主播。
  - **(11)** 如果 John Madden 有優雅的人格但不是政治專家，則他不是電視主播。
- **Exercise 7-8（在有限論域 $D = \{a, b\}$ 中的展開式 Expansion）**：
  - **(1)** $(x)(Fx \cdot Gx) \implies$ **$(Fa \cdot Ga) \cdot (Fb \cdot Gb)$**
  - **(3)** $(x)[Fx \supset (Gx \lor Hx)] \implies$ **$[Fa \supset (Ga \lor Ha)] \cdot [Fb \supset (Gb \lor Hb)]$**
  - **(5)** $(x)\sim(Fx \supset Gx) \implies$ **$\sim(Fa \supset Ga) \cdot \sim(Fb \supset Gb)$**
  - **(7)** $\sim(x)(Fx \supset Gx) \implies$ **$\sim[(Fa \supset Ga) \cdot (Fb \supset Gb)]$** *(注意 (5) 與 (7) 否定號位置對展開式的決定性影響！)*
  - **(9)** $(x)[Fx \supset (Gx \equiv Hx)] \implies$ **$[Fa \supset (Ga \equiv Ha)] \cdot [Fb \supset (Gb \equiv Hb)]$**
  - **(11)** $(\exists x)[(Fx \cdot Gx) \supset (Hx \cdot Kx)] \implies$ **$[(Fa \cdot Ga) \supset (Ha \cdot Ka)] \lor [(Fb \cdot Gb) \supset (Hb \cdot Kb)]$**
  - **(13)** $(\exists x)\sim[(Fx \lor Gx) \supset (Fx \lor Hx)] \implies$ **$\sim[(Fa \lor Ga) \supset (Fa \lor Ha)] \lor \sim[(Fb \lor Gb) \supset (Fb \lor Hb)]$**

---

### 4. Exercise 7-9、7-10、7-11：Only / Unless、諺語翻譯、「大多數 (Most)」的限制與大象部分否定辨析

- **Exercise 7-9（Only / Unless 進階題）**：
  - **(1)** *"No student who studies regularly flunks logic."* $\implies$ **$(x)[(Sx \cdot Fx) \supset \sim Rx]$**（或 $(x)[(Sx \cdot Rx) \supset \sim Fx]$）
  - **(3)** *"The gate of heaven is open only to the poor."* (`Only P are H`) $\implies$ **$(x)(Hx \supset Px)$**
  - **(5)** *"Only people who smoke tobacco die of lung cancer."* (`Only S are D`) $\implies$ **$(x)(Dx \supset Sx)$**
  - **(7)** *"Not only people who smoke tobacco die of lung cancer."*（並非只有抽菸的人才會死於肺癌） $\implies$ **$\sim(x)(Dx \supset Sx)$**
  - **(9)** *"Unless all elephants are protected, all elephants are doomed."* $\implies$ **$\sim(x)(Ex \supset Px) \supset (x)(Ex \supset Dx)$** 或 **$(x)(Ex \supset Px) \lor (x)(Ex \supset Dx)$**
  - **(11)** *"A rhinoceros charges only if it feels threatened."* $\implies$ **$(x)[(Rx \cdot Cx) \supset Tx]$**（若原句為 *"if it feels threatened"* 則為 $(x)[(Rx \cdot Tx) \supset Cx] \equiv (x)[Rx \supset (Tx \supset Cx)]$）

- **Exercise 7-10（日常格言與複雜量詞符號化）**：
  - **(1)** *"There is no such thing as a free lunch."*（天下沒有白吃的午餐） $\implies$ **$\sim(\exists x)(Lx \cdot Fx)$** 或 **$(x)(Lx \supset \sim Fx)$**
  - **(3)** *"Anything worth doing is worth doing badly."* $\implies$ **$(x)(Wx \supset Bx)$**
  - **(5)** ***"All that glitters is not gold."***（發光的並非全是金子 —— **經典部分否定**！詳見 [[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]] 第 5 節） $\implies$ **$\sim(x)(Lx \supset Gx)$**（若以 $Gx$ 為前件則為 $\sim(x)(Gx \supset Lx)$）
  - **(7)** *"Those who can, do; those who can't, teach."* $\implies$ **$(x)[(Px \cdot Cx) \supset Dx] \cdot (x)[(Px \cdot \sim Cx) \supset Tx]$**
  - **(9)** *"Only people over 30 enjoy Proust."* $\implies$ **$(x)[(Px \cdot Ex) \supset Ox]$**
  - **(11)** *"Some brilliant people are complete scoundrels."* $\implies$ **$(\exists x)[(Px \cdot Bx) \cdot Sx]$**
  - ⭐ **(13) 「大多數 (Most)」在純一階述詞邏輯中的不可表達性**：
    - 原句：*"Fortunately, most brilliant scoundrels are not very charismatic."*（幸運地，**大多數**技藝高超的惡棍並非很具領袖魅力）。
    - 在未引進等同號 `=`（甚至在一般一階邏輯無基數量詞時），我們**無法完全精確翻譯「大多數 (most)」**，只能退而求其次近似表達為「並非所有技藝高超的惡棍都具魅力（有些不具魅力，且有些具魅力）」：
      **$\sim(x)[(Bx \cdot Sx) \supset Cx]$** 或 **$(\exists x)[(Bx \cdot Sx) \cdot \sim Cx]$** 或 **$(\exists x)[(Bx \cdot Sx) \cdot \sim Cx] \cdot (\exists x)[(Bx \cdot Sx) \cdot Cx]$**。
  - **(15)** *"No scoundrel who is neither brilliant nor charismatic succeeds in life."* $\implies$ **$(x)\{[Sx \cdot (\sim Bx \cdot \sim Cx)] \supset \sim Lx\}$**（若為 *"not both"* 則為 $(x)\{[Sx \cdot (\sim Bx \lor \sim Cx)] \supset \sim Lx\}$）
  - **(17)** *"If no brilliant person is a scoundrel, then all brilliant people succeed in life."* $\implies$ **$\sim(\exists x)[(Px \cdot Bx) \cdot Sx] \supset \sim(\exists x)[(Px \cdot Bx) \cdot \sim Lx]$** 或 **$(x)[(Px \cdot Bx) \supset \sim Sx] \supset (x)[(Px \cdot Bx) \supset Lx]$**
  - **(19)** *"If everyone is a scoundrel, then no one succeeds in life."* $\implies$ **$(x)(Px \supset Sx) \supset (x)(Px \supset \sim Lx)$**

- **⭐ Exercise 7-11（課本 7-9 第 10 題大象保育句之「部分否定 vs. 全部否定」深度哲學辨析）**：
  - 題目：*"If all elephants are not protected, all elephants are doomed."*
  - 為什麼必須譯為 **$\sim(x)(Ex \supset Px) \supset (x)(Ex \supset Dx)$**（前件為**部分否定**：「並非所有大象都受保護」），而**不是** $(x)(Ex \supset \sim Px) \supset (x)(Ex \supset Dx)$（前件為**全部否定**：「所有大象都沒有受保護」）？
  - **兩大決定性理由**：
    1. **語法與真值條件**：“All elephants are not protected” 在英文慣用法中是**部分否定**（等同於 “Not all elephants are protected”，即 $\sim(x)(Ex \supset Px) \equiv (\exists x)(Ex \cdot \sim Px)$，這在現實中為真的可能性很大）。反之，全部否定 $(x)(Ex \supset \sim Px)$（「世上沒有半隻大象受保護」）在現實中明顯為**假 (`F`)**；如果前件為假，整個實質條件句就會變成**瑣碎地真（Trivially / Vacuously True，即廢話真理）**！
    2. **語用立意**：說話者的立意是呼籲「只要還有大象沒受到保護（並非所有大象都受保護），大象全體就會面臨滅絕」，故應譯為 **$\sim(x)(Ex \supset Px) \supset (x)(Ex \supset Dx)$**。

---

### 5. 邏輯小考 (5) 解答（2024.12.05 —— Ch. 7 述詞邏輯符號化 5 題）
> **對應原始檔案**：`raw/Quiz5_Ch07_邏輯小考5解答_20241205_述詞符號化.docx`

1. **「如果所有人都會死 ($Mx$)，則有些東西不是人 ($Hx$)。」**
   - **Ans.**：**$(x)(Hx \supset Mx) \supset (\exists x)\sim Hx$**
2. **「任何不怕死 ($Fx$) 的人 ($Px$) 都不是誠實的 ($Hx$)。」**
   - **Ans.**：**$(x)[(Px \cdot \sim Fx) \supset \sim Hx]$** 或 **$\sim(\exists x)[(Px \cdot \sim Fx) \cdot Hx]$**
3. **「並非每個人 ($Hx$) 都是聰明的 ($Ix$)，或者每個人都不是聰明的。」**（部分否定 $\lor$ 全部否定！）
   - **Ans.**：**$\sim(x)(Hx \supset Ix) \lor (x)(Hx \supset \sim Ix)$**
4. **「男孩 ($Bx$) 和女孩 ($Gx$) 都不是成人 ($Ax$)。」**（主詞中的「和」表聯集選言 $\lor$！）
   - **Ans.**：**$(x)[(Bx \lor Gx) \supset \sim Ax]$** 或 **$(x)(Bx \supset \sim Ax) \cdot (x)(Gx \supset \sim Ax)$**
5. **「有些人 ($Px$) 既是騙子 ($Lx$) 又是小偷 ($Tx$)。」**
   - **Ans.**：**$(\exists x)[Px \cdot (Lx \cdot Tx)]$**

---

## 第二部分：Ch. 10 多元關係述詞與多重量詞符號化題庫全解（Ex 10-1 ~ Ex 10-6）

> **對應原始檔案**：`raw/Ex_Ch10_關係述詞習題解答.docx`、`raw/Supp_Ch07_Ch09_Ex10-6_複雜關係述詞符號化與定理Q17補充.docx`

### 1. Exercise 10-1 & Exercise 10-2：二元/三元關係符號化與雙量詞展開式

- **Exercise 10-1（含常元與二元/三元關係述詞）**：
  - **(1)** $\sim Mcb$ \quad **(3)** $Mb \supset \sim Mbj$ \quad **(5)** $\sim Sbk$ \quad **(7)** $(x)(Bxd \supset \sim Idx)$
  - **(9)** $\sim Pbf \supset \sim(\exists x)(Px \cdot Pxf)$ 或 $\sim Pbf \supset (x)(Px \supset \sim Pxf)$
  - **(11)** $(\exists x)(Px \cdot Sxjh) \cdot \sim(\exists x)(Px \cdot Sxab)$ \quad **(13)** $(x)(Wxb \supset Rhx)$
  - **(15)** $(\exists x)(Mxa \cdot Lmx) \cdot (\exists x)(Mxa \cdot \sim Lmx)$ \quad **(17)** $(\exists x)(Px \cdot Txca) \cdot (\exists x)(Px \cdot \sim Txca)$
  - **(19)** $\sim Hca \supset (\exists x)(Sxah \cdot \sim Tx)$

- **Exercise 10-2（雙量詞關係句在 $D = \{a, b\}$ 中的展開式 Expansion —— 必考基本功！）**：

| 題號 | 雙量詞關係語句 | 在論域 $D = \{a, b\}$ 中的完整展開式 | 展開邏輯解析 |
| :-: | :--- | :--- | :--- |
| **(1)** | **$(x)(y)Sxy$** | **$(Saa \cdot Sab) \cdot (Sba \cdot Sbb)$** | 外層 $(x)$ 與內層 $(y)$ 皆展開為連言 `$\cdot$` |
| **(3)** | **$(\exists x)(y)Sxy$** | **$(Saa \cdot Sab) \lor (Sba \cdot Sbb)$** | 外層 $(\exists x)$ 先展開為選言 `$\lor$`，內層 $(y)$ 展開為連言 `$\cdot$` |
| **(5)** | **$\sim(x)(\exists y)Sxy$** | **$\sim[(Saa \lor Sab) \cdot (Sba \lor Sbb)]$** | 否定號留在最外層，內部先展開 $(x)$ 為 `$\cdot$`，再展開 $(\exists y)$ 為 `$\lor$` |
| **(7)** | **$(x)(y)\sim Sxy$** | **$(\sim Saa \cdot \sim Sab) \cdot (\sim Sba \cdot \sim Sbb)$** | 每個原子關係前皆帶否定號 $\sim$，全部以 `$\cdot$` 連接 |
| **(9)** | **$\sim[(x)(y)\sim Sxy]$** | **$\sim[(\sim Saa \cdot \sim Sab) \cdot (\sim Sba \cdot \sim Sbb)]$** | 即第 (7) 題的整句否定（等值於 $(\exists x)(\exists y)Sxy$） |
| **(11)** | **$\sim(\exists x)Sxx$** | **$\sim(Saa \lor Sbb)$** | 反身關係 $Sxx$ 只有一個變元 $x$，故僅含 $Saa$ 與 $Sbb$ 兩項！ |

---

### 2. Exercise 10-3：多重量詞交錯符號化（老師、學生、課程與考試經典題組）
```text
(1)  (∃x)[Sx · (y)~Kxy]
(3)  (∃x){Sx · (y)[(Qy · Txy) ⊃ Pxy]}
(5)  (x){Gx ⊃ (y)[(Cy · Txy) ⊃ Pxy]}
(7)  Gm · ~(x)[(Ex · Tmx) ⊃ Pmx]
(9)  (x)[(Cx · Pmx) ⊃ Tjx]
(11) ~(∃x)[Cx · (y)(Py ⊃ Tyx)]  或  (x)[Cx ⊃ ~(y)(Py ⊃ Tyx)]  或  (x)[Cx ⊃ (∃y)(Py · ~Tyx)]
(13) (x)[Qx ⊃ (y)(Ey ⊃ Ixy)]
(15) ~(∃x)(Px · Ixj)  或  (x)(Px ⊃ ~Ixj)
(17) (∃x){Sx · (y){{Cy · (z)[(Cz · Tjz) ⊃ Iyz]} ⊃ ~Txy}}
(19) ~(∃x){Px · (y)[(Ey · Tjy) ⊃ Pxy]}  或  (x){Px ⊃ (∃y)[(Ey · Tjy) · ~Pxy]}
(21) (∃x){Sx · (y)[(Cy · ~Dy) ⊃ Txy]}
(23) (x){(y)[(Cy · Dy) ⊃ Txy] ⊃ Gx}
(25) (x){(Cx · Tmx) ⊃ (y)[(Cy · Tjy) ⊃ Hxy]}
(27) (x){(y)[(Cy · Txy) ⊃ Pxy] ⊃ Gx}
(29) (x)[(Cx · Tjx) ⊃ Tmx]  或  (x)[(Cx · ~Tmx) ⊃ ~Tjx]
```

---

### 3. Exercise 10-4：將「時間 ($Tx$)」與「空間地點 ($Px$)」顯性量化之經典格言符號化
在日常語言中，「總是 (always)」、「有時 (sometimes)」、「無處不在 (everywhere)」、「從不 (never)」常隱藏了對**時間 ($Tx$)** 與**地點 ($Px$)** 的量詞！必須先進行**邏輯改寫 (Paraphrase)** 再符號化：

1. **(1) "There are cheaters somewhere."**（某處有騙子）
   - 字典：$Px =$ "$x$ is a place", $Cx =$ "$x$ is a cheater", $Axy =$ "$x$ is at $y$"
   - **Ans.**：**$(\exists x)(\exists y)[(Px \cdot Cy) \cdot Ayx]$**
2. **(3) "There are cheaters everywhere."**（到處都有騙子 $\implies$ 改寫："In every place there are cheaters"）
   - **Ans.**：**$(x)[Px \supset (\exists y)(Cy \cdot Ayx)]$** *(注意順序：對每一個地點 $x$，都存在至少一個騙子 $y$ 在 $x$！)*
3. **(5) 「人的工作永遠做不完。」 (A person's work is never done.)**
   - 改寫：「對每個人 $x$ 在任何時間 $y$，都存在某件屬於 $x$ 的工作 $z$ 是 $x$ 在時間 $y$ 沒做完的。」
   - 字典：$Px =$ "$x$ is a person", $Tx =$ "$x$ is a time", $Wxy =$ "$x$ is a work of $y$", $Dxyz =$ "$x$ is done by $y$ at time $z$"
   - **Ans.**：**$(x)\{Px \supset (y)[Ty \supset (\exists z)(Wzx \cdot \sim Dzxy)]\}$**
4. **(7) "You can fool all of the people some of the time."**（林肯名言前半：你能在某些時候欺騙所有的人）
   - 改寫："There is some time $x$ such that for all people $y$, you can fool $y$ at time $x$."
   - 字典：$Tx =$ "$x$ is a time", $Px =$ "$x$ is a person", $Fxy =$ "you can fool $x$ at time $y$"
   - **Ans.**：**$(\exists x)[Tx \cdot (y)(Py \supset Fyx)]$**
5. **(9) "You cannot fool all of the people all of the time."**（林肯名言後半：你不能在所有時候欺騙所有的人）
   - **Ans.**：**$(x)[Tx \supset \sim(y)(Py \supset Fyx)]$** 或 **$(x)[Tx \supset (\exists y)(Py \cdot \sim Fyx)]$**（或整句否定 $\sim(x)[Tx \supset (y)(Py \supset Fyx)]$）
6. **(11) 「會叫的狗不咬人。」 (Barking dogs don't bite.)**
   - 改寫：「每一隻會叫的狗，在任何時間都不咬人（不存在任何時間牠會咬人）。」
   - 字典：$Dx =$ "$x$ is a dog", $Kx =$ "$x$ barks", $Tx =$ "$x$ is a time", $Bxy =$ "$x$ bites at time $y$"
   - **Ans.**：**$(x)[(Dx \cdot Kx) \supset \sim(\exists y)(Ty \cdot Bxy)]$** 或 **$(x)\{(Dx \cdot Kx) \supset (y)[Ty \supset \sim Bxy]\}$**
7. **(13) 「罪惡無時不有、無所不在。」 (Sin is always everywhere.)**
   - 字典：$Tx =$ "$x$ is a time", $Px =$ "$x$ is a place", $Sx =$ "$x$ is a sin", $Axyz =$ "$x$ is at time $y$ in place $z$"
   - **Ans.**：**$(x)(y)[(Tx \cdot Py) \supset (\exists z)(Sz \cdot Azxy)]$**
8. **(15) "There's a sucker born every minute."**（每分鐘都有傻瓜誕生 $\implies$ 改寫："Given any time $x$, some sucker $y$ is born at $x$"）
   - **Ans.**：**$(x)[Tx \supset (\exists y)(Sy \cdot Byx)]$**

---

### 4. Exercise 10-6（全套奇數題 1, 3, 5, 7, 9, 11, 13 詳解）
- **(1)** 「任何破產的公司都應該結束營業。」 ($Cx =$ 公司, $Bx =$ 破產, $Dx =$ 應結束營業)
  - **Ans.**：**$(x)[(Cx \cdot Bx) \supset Dx]$**
- **(3)** *"If any frontrunners don't cater to all potential voters, then some longshots are going to win."*（結合**定理 Q17** $(x)(Fx \supset P) \equiv [(\exists x)Fx \supset P]$，三種等價寫法）：
  - **Ans. 1**：**$(\exists x)[Fx \cdot \sim(y)(Vy \supset Cxy)] \ \supset \ (\exists x)(Lx \cdot Wx)$**
  - **Ans. 2**：**$(x)\{[Fx \cdot \sim(y)(Vy \supset Cxy)] \ \supset \ (\exists x)(Lx \cdot Wx)\}$**
  - **Ans. 3**：**$(x)\{[Fx \cdot (\exists y)(Vy \cdot \sim Cxy)] \ \supset \ (\exists x)(Lx \cdot Wx)\}$**
- **(5)** 「凡信仰上帝 ($g$) 的人 ($Px$)，都會遵守上帝的所有戒律 ($Cyg$：y 是上帝的戒律)。」
  - **Ans.**：**$(x)[(Px \cdot Bxg) \supset (y)(Cyg \supset Oxy)]$**
- **(7)** 「任何受益於某項科學發現 ($Dy$) 的人 ($Px$)，都應該付錢 ($Oxz$) 給某位科學家 ($Sz$)。」
  - **Ans.**：**$(x)\{[Px \cdot (\exists y)(Dy \cdot Bxy)] \supset (\exists z)(Sz \cdot Oxz)\}$**
- **(9)** 「如果每個人都受益於某項科學發現，那麼有些人就無法付清他的所有帳單 ($Kyx$)。」
  - **Ans.**：**$(x)[Px \supset (\exists y)(Dy \cdot Bxy)] \ \supset \ (\exists x)[Px \cdot \sim(y)(Kyx \supset Pxy)]$**
- **(11)** 「沒有任何精神病醫師 ($Px$) 能夠幫助 ($Hxy$) 依占星術行事的人 ($Ay$)。」
  - **Ans.**：**$(x)[Px \supset (y)(Ay \supset \sim Hxy)]$** 或 **$\sim(\exists x)[Px \cdot (\exists y)(Ay \cdot Hxy)]$**
- **(13)** *"If some of us owe money to Isaac Newton ($n$), then there will come a time ($Tx$) when we should pay him what we owe."*（三種由輸出律 **Exp** 與量詞移入等價的修正標準式）：
  - **Ans. 1**：**$(\exists x)[Px \cdot (\exists y)(My \cdot Oxyn)] \ \supset \ (\exists x)\{Tx \cdot (y)(z)\{[Py \cdot (Mz \cdot Oyzn)] \supset Byznx\}\}$**
  - **Ans. 2**：**$(\exists x)[Px \cdot (\exists y)(My \cdot Oxyn)] \ \supset \ (\exists x)\{Tx \cdot (y)(z)\{Py \supset [(Mz \cdot Oyzn) \supset Byznx]\}\}$**
  - **Ans. 3**：**$(\exists x)[Px \cdot (\exists y)(My \cdot Oxyn)] \ \supset \ (\exists x)\{Tx \cdot (y)\{Py \supset (z)[(Mz \cdot Oyzn) \supset Byznx]\}\}$**

---

## 第三部分：Ch. 11 (13) 等同、數量詞與羅素確定描述詞符號化

### 1. 除外命題 (Everyone but / Only individual $a$) 與最高級比較
- **「班上除了 George ($g$) 之外，每個人都及格了 ($Px$)。」**：**$\sim Pg \cdot (x)[(x \neq g) \supset Px]$**
- **「班上只有 George 一個人及格。」**：**$Pg \cdot (x)[Px \supset (x = g)]$**
- **「玉山 ($j$) 比其他任何一座山 ($Mx$) 都高 ($Txy$)。」**：**$Mj \cdot (x)\{[Mx \cdot (x \neq j)] \supset Tjx\}$**（必須加 $x \neq j$ 排除玉山比自己高！）。

### 2. 數量詞（至少、至多、恰好 $n$ 個）與羅素確定描述詞
- **至少兩顆蘋果**：**$(\exists x)(\exists y)[(Ax \cdot Ay) \cdot (x \neq y)]$**
- **至多一顆蘋果**：**$(x)[Ax \supset (y)(Ay \supset (x = y))]$**
- **恰好一顆蘋果**：**$(\exists x)[Ax \cdot (y)(Ay \supset (x = y))]$**
- **羅素確定描述詞（「《射鵰英雄傳》的作者不是武俠小說家」兩種否定範圍）**：
  - **(a) 狹義範圍（內部否定 / 主要出現）**：**$(\exists x)\{[Ax \cdot (y)(Ay \supset (x = y))] \cdot \sim Nx\}$**
  - **(b) 廣義範圍（外部否定 / 次要出現）**：**$\sim(\exists x)\{[Ax \cdot (y)(Ay \supset (x = y))] \cdot Nx\}$**
