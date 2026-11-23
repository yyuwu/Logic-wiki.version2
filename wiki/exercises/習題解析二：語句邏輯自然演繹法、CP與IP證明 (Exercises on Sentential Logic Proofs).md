---
title: "習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)"
category: exercises
chapters: ["Ch. 4", "Ch. 5"]
source: "Ex_Ch04_習題解答.docx, Ex_Ch05_習題解答.docx"
tags: [logic, exercise, natural-deduction, proof, CP, IP, theorem, distribution, expressive-completeness, DNF]
updated: 2026-11-23
---

# 習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)

> **涵蓋章節**：[[Ch04 自然演繹法證明 (Natural Deduction Proofs)]]、[[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]]
> **對應原始題庫檔案**：`raw/Ex_Ch04_習題解答.docx`（Ex 4-1 ~ Ex 4-14 全解）、`raw/Ex_Ch05_習題解答.docx`（Ex 5-1 ~ Ex 5-8 全解）
> **對應概念**：[[一致性與反例集 (Consistency and Counterexample Set)]]、[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]、[[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]
> **對應方法**：[[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]、[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]、[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]
> **延伸期中考真題**：[[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]]

本頁完整收錄並解析 `Ex_Ch04_習題解答.docx`（Ex 4-1 至 Ex 4-14）與 `Ex_Ch05_習題解答.docx`（Ex 5-1 至 Ex 5-8）中的所有重要證明題、一題多解對照，以及 **Ex 4-14 語句邏輯表達完備性（Expressive Completeness & DNF 選言範式）** 與 **Ex 5-8 新推論規則有效性檢驗**。

---

## 第一部分：Ch. 4 自然演繹法分段進階題庫（Ex 4-1 ~ Ex 4-13）

### 1. Ex 4-1 ~ Ex 4-5：8 條單向蘊含規則實戰（MP, MT, DS, HS, Simp, Conj, Add, CD）

```text
【Ex 4-1 (7) — MT 與 DS 連鎖】              【Ex 4-3 (11) — Simp, MP, DS, Conj 組合】
  1. A ⊃ (B ⊃ C)           p                  1. (H · K) ⊃ L           p
  2. H ⊃ A                 p                  2. ~R · K                p
  3. H ∨ (A ∨ B)           p                  3. K ⊃ (H ∨ R)           p
  4. ~(B ⊃ C)              p  / ∴ B           4. K                     2 Simp
  5. ~A                    1, 4 MT            5. H ∨ R                 3, 4 MP
  6. ~H                    2, 5 MT            6. ~R                    2 Simp
  7. A ∨ B                 3, 6 DS            7. H                     5, 6 DS
  8. B                     5, 7 DS            8. H · K                 4, 7 Conj
                                              9. L                     1, 8 MP

【Ex 4-5 (11) — 建設性兩難律 CD】           【Ex 4-5 (15) — 兩次使用添加律 Add！】
  1. R ∨ ~W                p                  1. ~A                    p
  2. ~W ⊃ L                p                  2. (C ∨ A) ⊃ L           p
  3. R ⊃ T                 p  / ∴ T ∨ L       3. A ∨ D                 p
  4. T ∨ L                 1, 2, 3 CD         4. (D ∨ U) ⊃ C           p  / ∴ L
                                              5. D                     1, 3 DS
                                              6. D ∨ U                 5 Add
                                              7. C                     4, 6 MP
                                              8. C ∨ A                 7 Add
                                              9. L                     2, 8 MP
```

---

### 2. Ex 4-6 ~ Ex 4-11：加入 10 條雙向等值置換規則（DeM, Dist, Contra, Impl, Exp, Taut, Equiv）

#### (A) Ex 4-7 (1) & Ex 4-11 (1), (9), (11)：分配律 (Dist) 的「正向展開割離」與「逆向提公因式」！
- **正向展開割離多餘字母（Ex 4-7 (1) & Ex 4-11 (1) 雙解法）**：
```text
【Ex 4-11 (1) 解法 A：用 Add + DeM + DS】    【Ex 4-11 (1) 解法 B：用 Dist + Simp + DS】
  1. A ∨ (B · C)           p                  1. A ∨ (B · C)           p
  2. ~C                    p  / ∴ A           2. ~C                    p  / ∴ A
  3. ~C ∨ ~B               2 Add              3. (A ∨ B) · (A ∨ C)     1 Dist
  4. ~B ∨ ~C               3 Comm             4. A ∨ C                 3 Simp
  5. ~(B · C)              4 DeM              5. A                     2, 4 DS
  6. A                     1, 5 DS
```
- **逆向分配律（提公因式 Factoring Out，Ex 4-11 (9) & (11) 高階技巧！）**：
  - 當選言句的兩邊含有**共同的連言因子**（如 $(A \cdot X) \lor (A \cdot Y)$）時，可逆向使用 **Dist** 提出公因式 $A$ 變成 **$A \cdot (X \lor Y)$**，接著直接用 **Simp** 取出 $A$！
```text
【Ex 4-11 (9) — 逆向 Dist 提公因式 A】       【Ex 4-11 (11) — 逆向 Dist + 正向 Dist 連環技】
  1. [(A · B) · D] ∨ (C · A)   p  / ∴ A       1. [(A ∨ B) · (D · F)] ∨ [(A ∨ B) · C]   p  / ∴ C ∨ F
  2. [A · (B · D)] ∨ (C · A)   1 Assoc        2. (A ∨ B) · [(D · F) ∨ C]               1 Dist (逆向提 A∨B)
  3. [A · (B · D)] ∨ (A · C)   2 Comm         3. (D · F) ∨ C                           2 Simp
  4. A · [(B · D) ∨ C]         3 Dist (逆向!) 4. C ∨ (D · F)                           3 Comm
  5. A                         4 Simp         5. (C ∨ D) · (C ∨ F)                     4 Dist (正向展開)
                                              6. C ∨ F                                 5 Simp
```

#### (B) Ex 4-8 (1), (5), (9), (15)：輸出律 (Exp)、重言律 (Taut) 與一題雙解
```text
【Ex 4-8 (1) 雙解法：Impl+Assoc vs. Exp】    【Ex 4-8 (9) — Impl + Taut 秒殺 A ⊃ ~A】
  1. (A · B) ⊃ C           p                  1. A ⊃ ~A                p
  2. A                     p  / ∴ B ⊃ C       2. (~A ∨ ~B) ⊃ C         p  / ∴ ~A · C
  3. A ⊃ (B ⊃ C)           1 Exp              3. ~A ∨ ~A               1 Impl
  4. B ⊃ C                 2, 3 MP            4. ~A                    3 Taut
  *(另證：1 Impl ➔ 3 DeM ➔ 4 Assoc ➔ 6 DS)*   5. ~A ∨ ~B               4 Add
                                              6. C                     2, 5 MP
                                              7. ~A · C                4, 6 Conj
```

#### (C) Ex 4-10 (7)：爆炸原理 (Ex Falso Quodlibet) 4 步標準證明
```text
  1. A                     p
  2. ~A                    p  / ∴ B   (從矛盾前提 A 與 ~A 推出任意結論 B！)
  3. A ∨ B                 1 Add      (在真前提 A 後面用 Add 加上任意結論 B)
  4. B                     2, 3 DS    (用 ~A 把 A 消掉，直接得出 B！)
```

---

### 3. Ex 4-12 & Ex 4-13：高難度綜合長證明與多重證法（精選代表題）

#### (A) Ex 4-13 (5)：23 步 vs. 15 步（三種不同證明路徑對比！）
> **題目**：$1. \ P \supset [(Q \cdot R) \lor S] \quad 2. \ (Q \cdot R) \supset \sim P \quad 3. \ T \supset \sim S \ / \ \therefore P \supset \sim T$

```text
【最簡潔證法（第三種另證，15 步，善用 Exp 與 Taut）】：
  1. P ⊃ [(Q · R) ∨ S]     p
  2. (Q · R) ⊃ ~P          p
  3. T ⊃ ~S                p          / ∴ P ⊃ ~T
  4. P ⊃ [S ∨ (Q · R)]     1 Comm
  5. P ⊃ [~~S ∨ (Q · R)]   4 DN
  6. P ⊃ [~S ⊃ (Q · R)]    5 Impl     (在後件內部把選言轉為條件句！)
  7. (P · ~S) ⊃ (Q · R)    6 Exp      (用 Exp 將 P 與 ~S 合併至前件)
  8. (P · ~S) ⊃ ~P         2, 7 HS    (與前提 2 串聯消去 Q · R！)
  9. (~S · P) ⊃ ~P         8 Comm
 10. ~S ⊃ (P ⊃ ~P)         9 Exp      (用 Exp 將 P 移回後件，湊出 P ⊃ ~P！)
 11. T ⊃ (P ⊃ ~P)          3, 10 HS   (與前提 3 串聯得 T ⊃ (P ⊃ ~P))
 12. T ⊃ (~P ∨ ~P)         11 Impl
 13. T ⊃ ~P                12 Taut    (由 Taut 把 ~P ∨ ~P 化簡為 ~P！)
 14. ~~T ⊃ ~P              13 DN
 15. P ⊃ ~T                14 Contra  (由逆否命題得出 P ⊃ ~T！ Q.E.D.)
```

#### (B) Ex 4-13 (7)：雙解法證明 $1. \ A \supset B \quad 2. \ A \lor (B \cdot C) \ / \ \therefore B$
```text
  1. A ⊃ B                 p
  2. A ∨ (B · C)           p          / ∴ B
  3. (A ∨ B) · (A ∨ C)     2 Dist     (先用 Dist 割離多餘的 C)
  4. A ∨ B                 3 Simp
  5. B ∨ A                 4 Comm
  6. ~~B ∨ A               5 DN
  7. ~B ⊃ A                6 Impl     (轉為條件句 ~B ⊃ A)
  8. ~B ⊃ B                1, 7 HS    (與 A ⊃ B 串聯得出 ~B ⊃ B！)
  9. ~~B ∨ B               8 Impl
 10. B ∨ B                 9 DN
 11. B                     10 Taut    (Q.E.D.)
```

---

### 4. ⭐ Ex 4-14：後設邏輯深度問答與「語句邏輯的表達完備性 (Expressive Completeness & DNF)」

> **對應原始檔案**：`raw/Ex_Ch04_習題解答.docx` 末尾 Ex 4-14 第 1, 3, 5, 7, 9 題詳解

#### (1) Why can't implicational argument forms be used on parts of lines in a proof? (Give an example.)
- **標準解答**：單向的（蘊含的）推論規則不能運用在部分句式（子句）上，只能運用在整個句式上。因為**若允許單向推論規則運用在部分子句上，會使推論變成一個無效的論證形式**！
  - **反例**：對前提 $(A \cdot B) \supset C$ 的前件局部誤用 Simp 推得 $/ \therefore A \supset C$。
  - **真值驗證**：當 $V(A)=\mathbf{T}, \ V(B)=\mathbf{F}, \ V(C)=\mathbf{F}$ 時，前提 $V((A \cdot B) \supset C) = (\mathbf{F} \supset \mathbf{F}) = \mathbf{T}$，但結論 $V(A \supset C) = (\mathbf{T} \supset \mathbf{F}) = \mathbf{F}$！故論證無效。

#### (3) Why are all substitution instances of a valid argument form valid arguments?
- **標準解答**：因為根據[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]的定義，一個有效論證形式的一切取代實例都具有相同的有效論證形式，而該有效論證形式在真值表上確保了它的所有取代實例都不可能出現「前提都真但結論卻為假」的情況。

#### (5) 為什麼不把所有由真值表檢驗為恆真的有效論證形式，全部都加進自然演繹法當作推論規則？（公設法 vs. Kahane 20 條規則系統 vs. Int-Elim 11 條規則系統的比較）
- **標準解答**（見 [[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]）：
  - 邏輯上，任何有效論證形式（其相應條件句為恆真句）都*可以*作為推論規則。但選取推論規則需兼顧**邏輯考量**與**實用／美學考量**：
    1. **邏輯考量**：系統必須滿足**健全性／一致性 (Soundness / Consistency)**（不會導出矛盾）與**完備性 (Completeness)**（所有有效論證與恆真句皆可證）。
    2. **實用考量**：為了貼近日常推論直覺，我們不採歐幾里得《幾何原本》式的「公設法系統 (Axiomatic System)」，而採「自然演繹法 (Natural Deduction)」。
    3. **美學（經濟性／簡單性）與實用的權衡**：
       - 課本 5-8 節（p.146）介紹的**引進與消去規則系統 (Int-Elim System，共 11 條規則)** 在規則數量上比本課程教授的 **Kahane 系統（18 條規則 + CP/IP = 20 條規則）** 更簡單經濟。
       - 但 **Kahane 系統在實用上具有明顯優越性**：因為推論規則較豐富，實際證明步驟遠較簡短直覺。
       - 反之，若把無限多個有效論證形式全部列為推論規則，系統將完全喪失**經濟性與實用性**（人類根本無法記憶與查找無限條規則）。

#### (7) Show how all our operators can be expressed in terms of the tilde ($\sim$) and the wedge ($\lor$).（證明 $\{\sim, \lor\}$ 具有表達完備性）
- **標準解答**：僅使用否定號 `~`（tilde）與選言號 `∨`（wedge），即可定義出其餘三個連詞：
  1. **連言 ($\cdot$)**：$p \cdot q \ := \ \sim(\sim p \lor \sim q)$ （由 DeM 與 DN）
  2. **條件句 ($\supset$)**：$p \supset q \ := \ \sim p \lor q$ （由 Impl）
  3. **雙條件句 ($\equiv$)**：$p \equiv q \ := \ \sim(\sim p \lor \sim q) \lor \sim(p \lor q)$ $\quad [\text{即 } (p \cdot q) \lor (\sim p \cdot \sim q)]$

#### ⭐ (9) 語句邏輯的表達完備性 (Expressive Completeness) 與選言範式 (Disjunctive Normal Form, DNF)
- **問題 1：含有 2 個（或 $n$ 個）語句變元的完構式 (wff)，總共有多少種不同的可能真值表？**
  - **解答**：2 個變元的真值表有 $2^2 = 4$ 列；在每一列中，句式 $X$ 的真值都有 `T` 或 `F` 兩種選擇，因此共有 **$2^4 = 16$ 種不同的真值表**！（$(p \cdot q), (p \lor q), (p \supset q), (p \equiv q)$ 只是這 16 種真值表中的 4 種）。
  - **一般化公式**：含有 $n$ 個語句變元的句式，共有 **$2^{(2^n)}$ 種**不同的真值表！
- **問題 2：如何用「選言範式 (Disjunctive Normal Form, DNF)」證明語句邏輯 $\{\sim, \cdot, \lor\}$ 具有表達完備性（能構造出任何可能的真值表）？**
  - **DNF 構造演算法**：
    1. 觀察目標真值表中，句式 $X$ 在哪幾列的值為 **`T`**。
    2. 針對每一個為 `T` 的列，寫出一個**狀態描述連言式**：若該列中變元為 `T` 就寫該變元本身（如 $p$），若該列中變元為 `F` 就寫該變元的否定（如 $\sim p$），並用 `$\cdot$` 連起來（使該連言式**只在這一列為 T，在其他所有列皆為 F**）。
    3. 將所有為 `T` 之列的連言式用選言號 **`$\lor$`** 串聯起來，即得到 $X$ 的**選言範式 (DNF)**！（若 $X$ 在所有列皆為 `F`，即矛盾句，則直接用 $p \cdot \sim p$ 表示）。
  - **講義實例 1**：若 $X$ 在第 1 列 ($T, T$) 與第 3 列 ($F, T$) 為 **`T`**，在第 2、4 列為 `F`：
    $$\implies X \text{ 的 DNF 為：} (p \cdot q) \lor (\sim p \cdot q)$$
  - **講義實例 2**：若 $X$ 在第 1 列 ($T, T$)、第 3 列 ($F, T$)、第 4 列 ($F, F$) 為 **`T`**，僅在第 2 列 ($T, F$) 為 `F`：
    $$\begin{aligned} X \text{ 的 DNF} &= (p \cdot q) \lor (\sim p \cdot q) \lor (\sim p \cdot \sim q) \\ &= (p \cdot q) \lor [\sim p \cdot (q \lor \sim q)] \\ &= (p \cdot q) \lor \sim p \\ &= (\sim p \lor p) \cdot (\sim p \lor q) \\ &= \sim p \lor q \ \equiv \ p \supset q \end{aligned}$$

---

## 第二部分：Ch. 5 條件證法 (CP)、間接證法 (IP)、定理與不一致題庫（Ex 5-1 ~ Ex 5-8）

### 1. Ex 5-1：條件證法 (CP) 搭配 Contra, Exp, Equiv 實戰（對應 `raw/Ex_Ch05_習題解答.docx`）

```text
【Ex 5-1 (9) — 先用 CP 證 R ⊃ P，再用 Contra 得 ~P ⊃ ~R】
  1. R ⊃ (L · S)           p
  2. (L ∨ M) ⊃ P           p          / ∴ ~P ⊃ ~R
     | 3. R                AP         (不直接假設 ~P，改假設逆否命題的前件 R！)
     | 4. L · S            1, 3 MP
     | 5. L                4 Simp
     | 6. L ∨ M            5 Add
     | 7. P                2, 6 MP
  8. R ⊃ P                 3–7 CP
  9. ~P ⊃ ~R               8 Contra   (由逆否命題一步到位！)

【Ex 5-1 (15) — 用兩段平行 CP 證明雙條件句結論 (N ⊃ R) ≡ (P ⊃ R)】
  1. N ≡ P                 p          / ∴ (N ⊃ R) ≡ (P ⊃ R)
  2. (N ⊃ P) · (P ⊃ N)     1 Equiv
     | 3. N ⊃ R            AP         (第一段 CP：證左至右)
     | 4. P ⊃ N            2 Simp
     | 5. P ⊃ R            3, 4 HS
  6. (N ⊃ R) ⊃ (P ⊃ R)     3–5 CP
     | 7. P ⊃ R            AP         (第二段 CP：證右至左)
     | 8. N ⊃ P            2 Simp
     | 9. N ⊃ R            7, 8 HS
 10. (P ⊃ R) ⊃ (N ⊃ R)     7–9 CP
 11. [(N ⊃ R) ⊃ (P ⊃ R)] · [(P ⊃ R) ⊃ (N ⊃ R)]  6, 10 Conj
 12. (N ⊃ R) ≡ (P ⊃ R)     11 Equiv   (Q.E.D.)
```

---

### 2. Ex 5-3 & Ex 5-4：間接證法 (IP) vs. 不使用 IP/CP 雙軌對照（對應 `raw/Ex_Ch05_習題解答.docx`）

- **Ex 5-4 (5) 經典對比：不用 IP 需 20 步 vs. 使用 IP 僅需 15 步直線拆解！**
  > **題目**：$1. \ H \supset (A \cdot B) \quad 2. \ B \supset (M \lor \sim A) \quad 3. \ M \supset (\sim H \lor \sim B) \ / \ \therefore \sim H$

```text
【(b) 使用 IP（直覺順暢，15 步）】：           【(a) 不使用 IP 或 CP（需 Exp + Dist + Taut，20 步）】：
  1. H ⊃ (A · B)           p                  1. H ⊃ (A · B)           p
  2. B ⊃ (M ∨ ~A)          p                  2. B ⊃ (M ∨ ~A)          p
  3. M ⊃ (~H ∨ ~B)         p  / ∴ ~H          3. M ⊃ (~H ∨ ~B)         p  / ∴ ~H
     | 4.  H               AP (假設 H 為真)    4. B ⊃ (~A ∨ M)          2 Comm
     | 5.  A · B           1, 4 MP            5. B ⊃ (A ⊃ M)           4 Impl
     | 6.  B               5 Simp             6. (B · A) ⊃ M           5 Exp
     | 7.  M ∨ ~A          2, 6 MP            7. (A · B) ⊃ M           6 Comm
     | 8.  A               5 Simp             8. H ⊃ M                 1, 7 HS
     | 9.  ~~A             8 DN               9. H ⊃ (~H ∨ ~B)         3, 8 HS
     | 10. M               7, 9 DS           10. H ⊃ (H ⊃ ~B)          9 Impl
     | 11. ~H ∨ ~B         3, 10 MP          11. (H · H) ⊃ ~B          10 Exp
     | 12. ~~B             6 DN              12. H ⊃ ~B                11 Taut
     | 13. ~H              11, 12 DS         13. ~H ∨ (A · B)          1 Impl
     | 14. H · ~H          4, 13 Conj        14. (~H ∨ A) · (~H ∨ B)   13 Dist
 15. ~H                    4–14 IP           15. ~H ∨ B                14 Simp
                                             16. H ⊃ B                 15 Impl
                                             17. ~B ⊃ ~H               16 Contra
                                             18. H ⊃ ~H                12, 17 HS
                                             19. ~H ∨ ~H               18 Impl
                                             20. ~H                    19 Taut
```

---

### 3. Ex 5-6、Ex 5-7 & Ex 5-8：無前提定理、前提集不一致證明與新推論規則評估

#### (A) Ex 5-6 (7)：無前提證明「條件句連通性定理」$\vdash (A \lor B) \supset [(A \supset B) \lor (B \supset A)]$
```text
【雙層 CP 最簡潔證法】
  | 1. A ∨ B               AP         (外層 CP：假設 A ∨ B)
  | | 2. ~(A ⊃ B)          AP         (內層 CP：為證選言後件，假設左選言支的否定 ~(A ⊃ B)！)
  | | 3. ~(~A ∨ B)         2 Impl
  | | 4. ~~A · ~B          3 DeM
  | | 5. ~B                4 Simp
  | | 6. ~B ∨ A            5 Add      (有了 ~B，用 Add 加上 ∨ A 即變出 B ⊃ A！)
  | | 7. B ⊃ A             6 Impl
  | 8. ~(A ⊃ B) ⊃ (B ⊃ A)  2–7 CP
  | 9. ~~(A ⊃ B) ∨ (B ⊃ A) 8 Impl
  | 10. (A ⊃ B) ∨ (B ⊃ A)  9 DN
 11. (A ∨ B) ⊃ [(A ⊃ B) ∨ (B ⊃ A)]  1–10 CP  (Q.E.D. 事實上連第 1 列的 A ∨ B 都無須用到，[(A ⊃ B) ∨ (B ⊃ A)] 本身就是恆真定理！)
```

#### (B) Ex 5-7 (5), (7), (9)：用自然演繹規則證明前提集不一致（導出 $q \cdot \sim q$）
```text
【Ex 5-7 (5)】                                【Ex 5-7 (7)】
  1. A ⊃ (B ∨ C)           p                  1. K ⊃ (L ⊃ M)           p
  2. ~(~A ∨ C)             p                  2. N ∨ K                 p
  3. ~B                    p                  3. ~(~L ∨ M)             p
  4. ~~A · ~C              2 DeM              4. ~N                    p
  5. A · ~C                4 DN               5. K                     2, 4 DS
  6. A                     5 Simp             6. L ⊃ M                 1, 5 MP
  7. B ∨ C                 1, 6 MP            7. ~(L ⊃ M)              3 Impl
  8. ~C                    5 Simp             8. (L ⊃ M) · ~(L ⊃ M)    6, 7 Conj (不一致！)
  9. B                     7, 8 DS
 10. B · ~B                3, 9 Conj (不一致！)
```

#### (C) ⭐ Ex 5-8 (1), (3), (5)：如何評估一條候選規則能否加入我們的自然演繹系統？
- **判準**：
  - 若要加入一條**雙向等值規則 $X :: Y$**，必須能在現有系統中**無前提證明出雙條件句定理 $\vdash X \equiv Y$**（或用真值表證明 $X \equiv Y$ 恆真）；若存在任何一組賦值使一邊為 `T`、另一邊為 `F`，則該規則**無效，不可加入**（否則會破壞系統健全性 Soundness！）。
  - **Ex 5-8 (1)**：檢驗 $p \lor (q \lor r) \ :: \ r \lor (q \lor p)$ $\implies$ **可以添加**！因為可利用兩段 CP（結合 Assoc 與兩次 Comm）在 12 步內無前提證明 $\vdash [P \lor (Q \lor R)] \equiv [R \lor (Q \lor P)]$ 為定理。
  - **Ex 5-8 (3)**：檢驗 $p \supset (q \supset r) \ :: \ r \supset (q \supset p)$ $\implies$ **不可以添加（無效規則）**！
    - **反例賦值**：當 **$V(P)=\mathbf{F}, \ V(Q)=\mathbf{T}, \ V(R)=\mathbf{T}$** 時，左式 $V(P \supset (Q \supset R)) = (\mathbf{F} \supset \mathbf{T}) = \mathbf{T}$，但右式 $V(R \supset (Q \supset P)) = \mathbf{T} \supset (\mathbf{T} \supset \mathbf{F}) = \mathbf{F}$！
  - **Ex 5-8 (5)**：檢驗單向規則 $p \supset q \ / \ \therefore \sim(\sim q \supset p)$ $\implies$ **不可以添加（無效規則）**！
    - **反例賦值**：當 **$V(P)=\mathbf{T}, \ V(Q)=\mathbf{T}$** 時，前提 $V(P \supset Q) = \mathbf{T}$，但結論 $V(\sim(\sim Q \supset P)) = \sim(\mathbf{F} \supset \mathbf{T}) = \sim\mathbf{T} = \mathbf{F}$！
