---
title: "Ch09 述詞邏輯的證明 (Predicate Logic Proofs)"
category: chapters
chapter: "Ch. 9"
source: "Ch_09_述詞邏輯的證明.docx / Hausman Ch. 9 & Ch. 11"
tags: [logic, chapter, predicate-logic, proof, UI, EI, UG, EG, QN, quasivariables, restrictions]
updated: 2026-11-22
---

# Ch09 述詞邏輯的證明 (Predicate Logic Proofs)

> **對應原始講義**：`raw/Ch_09_述詞邏輯的證明.docx`（主）｜*Logic and Philosophy: A Modern Introduction* (13th Ed., Ch. 9 & Ch. 11)（輔）

本章建立述詞邏輯（PL）的自然演繹證明系統。由於量詞管轄下的式子（如 $(x)\sim(Fx \cdot Gx)$ 中的 $\sim(Fx \cdot Gx)$）含有變元而非獨立的真值函應成分語句，**語句邏輯（SL）的 18 條規則絕對不能直接穿透量詞套用在量詞內部**！因此，我們必須建立「先用 **UI / EI** 脫去量詞 $\rightarrow$ 套用 **SL 18 條規則與 CP/IP** $\rightarrow$ 再用 **UG / EG** 加回量詞」的三階段推論引擎，並嚴格遵守防止無效推論的**五項主要限制**與**量詞否定規則 (QN)**。

---

## 1. 核心架構與知識節點

### 9-1 ~ 9-2 四條單向量詞推論規則與準變元 (The Four Quantifier Rules & Quasivariables)
- **[[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]**
  - **準變元 (Quasivariables) 的哲學意義**：
    - 在 [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] 中，含有自由變元的開語句 $Fx$ 沒有真假值。那為什麼在證明中可以從真前提 $(x)Fx$ 推導出 $Fx$？
    - 因為在證明步驟中，脫去量詞後留下的 $x, y$ 並非真正的自由變元，而是**準變元 (Quasivariables)**（或稱臨時名稱 Temporary Names）：
      - **由 UI 引進的準變元**：代表論域中「任意挑出的一個個體之普遍代稱」（如英文的 "John Doe" 或「任一某甲」）。
      - **由 EI 引進的準變元**：代表論域中「已知存在且具有該性質、但不知其具體身分的某個特定個體代稱」（如「某個不知名的兇手 X 先生」）。
  - **四條量詞規則總覽（皆為單向蘊含規則，只能套用在整個列 Whole Line 上！）**：

| 規則名稱 | 英文與縮寫 | 推論形式 | 核心操作說明 |
| :--- | :--- | :---: | :--- |
| **全稱引例規則** | Universal Instantiation (**UI**) | $\frac{(u)(\dots u \dots)}{\therefore (\dots w \dots)}$ | 脫去最外層全稱量詞 $(u)$，將所有被 $(u)$ 拘束的 $u$ **一致取代**為常元或自由準變元 $w$ |
| **存在引例規則** | Existential Instantiation (**EI**) | $\frac{(\exists u)(\dots u \dots)}{\therefore (\dots w \dots)}$ | 脫去最外層存在量詞 $(\exists u)$，將所有被 $(\exists u)$ 拘束的 $u$ **一致取代**為**全新的自由準變元** $w$ |
| **全稱一般化規則** | Universal Generalization (**UG**) | $\frac{(\dots u \dots)}{\therefore (w)(\dots w \dots)}$ | 將該列中**所有出現**的自由準變元 $u$ **一致拘束**為全稱量詞 $(w)$ |
| **存在一般化規則** | Existential Generalization (**EG**) | $\frac{(\dots u \dots)}{\therefore (\exists w)(\dots w \dots)}$ | 將該列中**至少一個**個體常元或自由準變元 $u$ 取代並拘束為存在量詞 $(\exists w)$ |

### 9-3 述詞邏輯證明的「五項主要限制」(The Five Main Restrictions) —— 全書最核心必考防呆機制！
- 為什麼要有這五項限制？因為一旦違反其中任何一項，就會立刻推導出荒謬的無效論證（詳見 [[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]] 與 [[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]）：

1. **【EI 限制 1】EI 絕對不能引進個體常元 (Constant)**：
   - ❌ 錯誤示範：從 $(\exists x)Hx$（有人是兇手）用 EI 推得 $Ha$（亞當是兇手）。
2. **【EI 限制 2】EI 引進的準變元，絕對不能在先前的證明列中自由出現過（必須是全新的自由變元！）**：
   - ❌ 錯誤示範：從 1. $(\exists x)Fx$（有東西是狐狸）與 2. $(\exists x)Gx$（有東西是鵝），先對第 1 列做 EI 得 3. $Fx$，又對第 2 列做 EI 用同一個 $x$ 得 4. $Gx$，再用 Conj 與 EG 得 $(\exists x)(Fx \cdot Gx)$（有東西同時既是狐狸又是鵝！）。
   - 💡 **黃金解題鐵律：「先 EI，後 UI」**！當證明中同時有存在前提 $(\exists x)$ 與全稱前提 $(x)$ 時，務必**先對存在前提做 EI** 引進新變元 $x$，接著**再對全稱前提做 UI**（因為 UI 沒有新變元限制，可以合法代入剛剛 EI 引進的 $x$！）。
3. **【UG 限制 1】UG 絕對不能對個體常元 (Constant) 做全稱一般化**：
   - ❌ 錯誤示範：從 $Fa$（蘇格拉底是哲學家）用 UG 推得 $(x)Fx$（所有人都是哲學家）。
4. **【UG 限制 2】UG 絕對不能對「在任何 EI 列中曾自由出現過的準變元」做全稱一般化（EI 下毒 / 汙染規則 Tainting Rule）**：
   - **直接下毒**：由 EI 直接引進的準變元 $x$（只代表某個特定未知個體，不具任意性），絕對不能做 UG。
   - **間接沾染下毒（多量詞關係句最易錯陷阱！）**：在多量詞句如 1. $(x)(\exists y)Lxy$（每個人都愛某個人）中，先用 UI 得 2. $(\exists y)Lxy$，接著用 EI 脫去 $(\exists y)$ 得 3. $Lxy$。請注意：**在第 3 列（EI 列）中，$x$ 雖然原本是由 UI 產生的，但它現在與 EI 引進的 $y$ 同處於一個 EI 列中（$y$ 的身分依賴於 $x$ 的選擇！），因此 $x$ 也在 EI 列中自由出現而被「下毒汙染」了**！後續步驟絕對不能對 $x$ 做 UG！否則若對第 3 列做 UG 得 $(x)Lxy$ 再做 EG 得 $(\exists y)(x)Lxy$，就會從「每個人都有愛人」荒謬地推導出「有某一個人被全世界所有人愛」！
5. **【UG 限制 3】在尚未消去的自行假設前提 (Undischarged AP) 控制範圍（封閉線）內，絕對不能對該 AP 中自由出現的準變元做 UG**：
   - ❌ 錯誤示範：在封閉線內假設 1. $Ax$ [AP]，立刻在封閉線內對第 1 列做 UG 得 2. $(x)Ax$，然後用 CP 消去 AP 得 $Ax \supset (x)Ax$，再做 UG 得 $(x)[Ax \supset (x)Ax]$（荒謬斷言：只要有一個人是運動員，所有人就都是運動員！）。
   - 💡 **AP 消去後的「解毒」機制**：雖然在 AP 的封閉線**內部**不能對 $x$ 做 UG，但一旦用 **CP 或 IP 將該 AP 消去（走出封閉線外）**，該變元 $x$ 就不再受未消去 AP 的限制（已解毒），此時**在封閉線外可以合法對 $x$ 做 UG**！
     - 標準證明模板：假設 $Ax$ [AP] $\rightarrow \dots \rightarrow Bx \rightarrow$ 關閉封閉線由 CP 得 $Ax \supset Bx \rightarrow$ 在封閉線外合法由 **UG** 得 **$(x)(Ax \supset Bx)$**！

- **附加第 4 組精確語法限制（原文書 Ch.11 多量詞防意外拘束限制）**：
  - **禁止意外拘束 (No Accidental Binding)**：做 UI 或 EI 代入變元 $w$ 時，$w$ 不可被式子內部已有的其他同名量詞 $(w)$ 或 $(\exists w)$ 意外拘束。
  - **UG 必須全部拘束**：做 UG 時，必須將該列中**所有自由出現**的目標變元 $u$ **全部**拘束為 $w$（不可像 EG 一樣只拘束其中一個而留下另一個，否則從 $(x)Ixx \Rightarrow Ixx$ 會錯誤用 UG 推得 $(y)Ixy \Rightarrow (x)(y)Ixy$）。
  - **禁止跨變元同時拘束**：UG 或 EG 不可一次把原本就自由出現的 $w$ 與新取代的 $u$ 混在一起拘束（例如不可從 $Lxy$ 用 EG 得 $(\exists x)Lxx$）。

### 9-6 量詞否定規則 (Quantifier Negation, QN)
- **本質**：唯一一套專門處理量詞的**雙向等值置換規則 (`::`)**！因此 **QN 可以雙向使用，且可以直接套用在語句內部的部分子句上**！
- **轉換口訣**：「**量詞互換 $(u) \leftrightarrow (\exists u)$；量詞左右兩側原本有 $\sim$ 就拿掉，原本沒 $\sim$ 就加上**」：
  1. $(u)(\dots u \dots) :: \sim(\exists u)\sim(\dots u \dots)$
  2. $(\exists u)(\dots u \dots) :: \sim(u)\sim(\dots u \dots)$
  3. $(u)\sim(\dots u \dots) :: \sim(\exists u)(\dots u \dots)$
  4. $(\exists u)\sim(\dots u \dots) :: \sim(u)(\dots u \dots)$

---

## 2. 跨章節演進與概念連結 (Cross-Chapter Connections)

| 關聯方向 | 目標章節 / 概念頁面 | 邏輯演進與比較關係 |
| :--- | :--- | :--- |
| **承接前章** | [[Ch04 自然演繹法證明 (Natural Deduction Proofs)]] | 將 SL 的 18 條規則擴充加上 4 條單向量詞規則 (UI/EI/UG/EG) 與雙向等值規則 QN |
| **承接前章** | [[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]] | CP 與 IP 與 UG 第 3 條限制（AP 封閉線內禁用 UG、消去 AP 後解毒可用 UG）緊密結合 |
| **承接前章** | [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] | Ch.7 對當方陣中的 A-O 矛盾、E-I 矛盾關係，在 Ch.9 正式化為量詞否定規則 (QN) |
| **深化方法** | [[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]] | 深入剖析準變元、五項限制違規案例、EI 下毒傳染機制與「先 EI 後 UI」策略 |
| **向後延伸** | [[Ch11 等同與確定描述詞 (Identity and Definite Descriptions)]] | 在 Ch.9 量詞證明基礎上，進一步加入等同推論規則 **ID** 與 **IR** |
| **綜合比較** | [[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]] | 橫向對比 Ch.4 整列限制、Ch.5 封閉線限制與 Ch.9 量詞五項限制 |
| **綜合定理** | [[述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)]] | 完整收錄林正弘《邏輯》附錄二之 55 條述詞邏輯定理（Q1~Q55）與課本 Ex 10-12 無前提定理證明 |
| **實戰練習** | [[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]] | 對應 Ex 9-1 ~ Ex 9-5（含 Ex 9-2 抓錯與 Ex 9-4 QN 診斷）、邏輯小考 9 及 Ch.10 多重量詞關係證明 Ex 10-10 ~ 10-11 全解 |
