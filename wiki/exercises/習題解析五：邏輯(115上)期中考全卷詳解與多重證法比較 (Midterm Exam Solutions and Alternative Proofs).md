---
title: "習題解析五：邏輯(115上)期中考與歷屆小考(1)~(6)全卷詳解 (Midterm Exam and Quizzes Solutions)"
category: exercises
chapters: ["Ch. 1", "Ch. 2", "Ch. 3", "Ch. 4", "Ch. 5"]
source: "Exam_Ch01_to_Ch05_邏輯115上期中考解答.doc, Quiz1~Quiz6 (2023/2024 邏輯小考 1~6 解答共 7 份)"
tags: [logic, exercise, midterm-exam, quiz, true-false, multiple-choice, consistency, short-truth-table, natural-deduction, theorem, CP, IP]
updated: 2026-11-23
---

# 習題解析五：邏輯(115上)期中考與歷屆小考(1)~(6)全卷詳解 (Midterm Exam and Quizzes Solutions)

> **對應原始檔案**：
> - 期中考卷：`raw/Exam_Ch01_to_Ch05_邏輯115上期中考解答.doc`（2026/10/29 邏輯 115 上期中考解答，共 8 頁）
> - 7 份歷屆小考解答：`raw/Quiz1_Ch01_邏輯小考1解答_20240919.docx`、`raw/Quiz2_Ch02_邏輯小考2解答_20240926.docx`、`raw/Quiz3_Ch03_邏輯小考3解答_20241003.docx`、`raw/Quiz3_Ch01_to_Ch03_邏輯小考3解答_20231024_選擇題.docx`、`raw/Quiz4_Ch04_邏輯小考4解答_20241024.docx`、`raw/Quiz5_Ch04_邏輯小考5解答_20231107.docx`、`raw/Quiz6_Ch05_邏輯小考6解答_20231114.docx`
> **跨章節考核範圍**：[[Ch01 邏輯導論 (Introduction to Logic)]]、[[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]]、[[Ch03 真值表 (Truth Tables)]]、[[Ch04 自然演繹法證明 (Natural Deduction Proofs)]]、[[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]]
> **關聯核心概念**：[[有效性與健全性 (Validity and Soundness)]]、[[一致性與反例集 (Consistency and Counterexample Set)]]、[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]、[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]、[[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]
> **關聯推論方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]、[[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]、[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]、[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]

本頁完整收錄並解析「邏輯（115 上）期中考解答」全部五大題，以及 **7 份歷屆邏輯小考（小考 1 至小考 6，含是非題、單選題、符號化、真值表與一題四解定理證明）**。

---

## 第一大題：觀念是非題與舉例證明／反例否證（30%，共 10 題）

### (1) 「如果太陽從西邊升起來，我就請你吃飯。」這句話可以恰當地翻譯為實質條件句 (material conditional)。
- **解答**：**`F`（假）**。
- **理由與解析**（對應 [[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]）：
  - 「如果太陽從西邊升起來，我就請你吃飯」在日常語用（pragmatic）上是**反事實條件句 (Counterfactual Conditional)**，說話者真正要表達的意思是：**「我絕不會請你吃飯！」**（因為太陽不可能從西邊升起）。
  - 但若將它翻譯成邏輯上的實質條件句 $S \supset E$，由於前件 $S$（「太陽從西邊升起」）為**假 (F)**，根據實質條件句真值表第 3、4 列，不論後件 $E$ 真假，整句 $S \supset E$ 都會自動變成**真 (T)**！因此，反事實條件句根據其語用意義，不可以恰當地翻譯為實質條件句。

### (2) 「小明不在家」的否定句是「小明在家」。
- **解答**：**`F`（假）**。
- **理由與解析**（對應 [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]）：
  - 設 $A =$「小明在家」，則「小明不在家」為否定句 $\sim A$。
  - 在嚴格語法形式上，$\sim A$ 的否定句必須在前面再加一個否定號，即**「並非小明不在家」($\sim\sim A$)**！
  - 雖然根據雙重否定律（**DN**），「小明在家」($A$) 在語意上與「並非小明不在家」($\sim\sim A$) **邏輯等值**，但在語法分類上，$A$ 是**肯定句（原子語句）**，而 $\sim\sim A$ 才是 $\sim A$ 的**否定句**！

### (3) $p \supset \sim(q \cdot r)$ 是 $\sim B \supset \sim(\sim B \cdot B)$ 的一個語句形式。
- **解答**：**`T`（真）**。
- **理由與解析**（對應 [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]）：
  - 檢查一致取代規則：將語句形式 $p \supset \sim(q \cdot r)$ 中所有出現的 $p$ 代入 $\sim B$、所有出現的 $q$ 代入 $\sim B$、所有出現的 $r$ 代入 $B$，所得結果正是 $\sim B \supset \sim(\sim B \cdot B)$！
  - Remember：**不同的變元（如 $p$ 與 $q$）允許代入相同的語句（如 $\sim B$）**！因此 $\sim B \supset \sim(\sim B \cdot B)$ 確實是 $p \supset \sim(q \cdot r)$ 的一個合法取代實例。

### (4) 若一個語句集中的所有語句都同時為假，則此語句集是不一致的。
- **解答**：**`F`（假）**。
- **理由與解析**（對應 [[一致性與反例集 (Consistency and Counterexample Set)]]）：
  - 一個語句集在現實中（或某組特定賦值下）所有語句同時為假，它**有可能是一致的，也有可能是不一致的**：
    1. **一致的例子**：語句集 $\{A, B\}$（其形式為 $\{p, q\}$），若令 $A =$「清華大學在巴黎」(F)，$B =$「台灣大學在柏林」(F)，兩句在事實上同時為假；但因為在邏輯上**有可能**同時為真（例如對應真值表 $V(p)=V(q)=T$ 的那一列），所以 $\{A, B\}$ 仍然是**一致的 (Consistent)**！
    2. **不一致的例子**：兩個矛盾句的集合 $\{A \cdot \sim A, \ B \cdot \sim B\}$，它們同時為假且不可能同時為真。
  - **核心觀念**：不一致的定義是「邏輯上**不可能同時為真**」，但並不排除它們可以同時為假；而一致的語句集不僅在某情況下可以同時為真，在另一情況下也可以同時為假！

### (5) 若一個論證具有一致的前提集且結論為假，則此論證必然是無效的。
- **解答**：**`F`（假）**。
- **理由與解析**（對應 [[有效性與健全性 (Validity and Soundness)]] 及 Ex 3-13 (7)）：
  - 一個具有一致前提集且結論在事實上為假的論證，**有可能是有效的**！
  - **反例**：
    1. 若清華大學在金門，則台灣大學在澎湖。（$A \supset B$，前件假故為 T）
    2. 清華大學在金門。（$A$，事實上為 F）
    $\therefore$ 台灣大學在澎湖。（$B$，事實上為 F）
  - 此論證具有肯定前件律（**MP**：$p \supset q, p / \therefore q$）的有效形式，故為**有效論證**；且其前提集 $\{A \supset B, A\}$ 是**一致的**（因為當 $V(A)=V(B)=T$ 時兩前提可同時為真），但因前提 2 在現實中為假，導致結論 $B$ 在現實中為假。「前提集一致」只代表前提*有可能*同時為真，不代表前提*事實上*已經同時為真！

### (6) 無效的論證形式之取代實例都是無效的論證。
- **解答**：**`F`（假）**。
- **理由與解析**（對應 [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]）：
  - **有效**論證形式的任何取代實例必然有效；但**無效**論證形式的取代實例**卻有可能是有效論證**！
  - **反例**：$p, q / \therefore r$ 顯然是一個**無效的論證形式**；但若我們將 $p$ 代入 $A \supset B$、$q$ 代入 $A$、$r$ 代入 $B$，所得的取代實例 $A \supset B, A / \therefore B$ 卻是一個**有效的論證**（因為它的具體一對一形式是 $p \supset q, p / \therefore q$）！

### (7) 一個恆真句的語句形式之取代實例必然也是恆真句。
- **解答**：**`F`（假）**。
- **理由與解析**（對應 [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]）：
  - 注意題目文字陷阱：「一個恆真句的語句形式（a statement form of a tautology）」vs. 「一個恆真的語句形式（a tautological statement form）」！
  - 任何恆真句（例如 $B \lor \sim B$）都是**原子形式 $p$** 的取代實例，因此 **$p$ 是該恆真句的一個語句形式**！
  - 但是，原子語句 $A$ 也是語句形式 $p$ 的一個取代實例，而 $A$ 是適真句，**並不是恆真句**！（唯有「恆真語句形式」的取代實例才必然是恆真句）。

### (8) 若一個有效論證的結論為恆真句，則此論證是健全的 (sound)。
- **解答**：**`F`（假）**。
- **理由與解析**（對應 [[有效性與健全性 (Validity and Soundness)]]）：
  - 以恆真句為結論的論證必然是**有效的**（特殊有效論證 II），但它的前提**不一定在事實上為真**！
  - **反例**：「清華大學在金門 ($A$) / $\therefore$ 清華大學在金門或清華大學不在金門 ($A \lor \sim A$)」。此論證有效且結論為恆真句，但因前提「清華大學在金門」在事實上為假，故此論證**不健全 (Unsound)**！

### (9) 若在有效論證的前提集中添加新的前提，則由此構成的新論證還是有效的。
- **解答**：**`T`（真）**。（演繹邏輯的**單調性 Monotonicity**）
- **雙軌證明（語法進路 + 語意進路）**（對應 [[語法學與語意學的雙軌對稱架構 (Syntactic vs Semantic Dual Architecture in Logic)]]）：
  1. **語法的進路**：既然原先的論證是有效的，則由原先的前提集根據推論規則已能必然導出結論；因此在此前提集中添加任何新前提，原本的推導步驟依然完全有效，還是必然能導出結論。
  2. **語意的進路**：既然原先的論證是有效的，則其**反例集** $\{P_1, \dots, P_n, \sim C\}$ 是**不一致的**（不可能同時為真）；而在一個已經不一致的語句集中再添加新的語句 $P_{n+1}$，新語句集 $\{P_1, \dots, P_n, P_{n+1}, \sim C\}$ 當然還是不一致的！故新論證依然有效。

### (10) 若 $A_1 \cdot A_2 \cdot \dots \cdot A_n$ 邏輯地蘊含 (logically imply) $C$，則 $A_1, A_2, \dots, A_n / \therefore C$ 是一個有效論證。
- **解答**：**`T`（真）**。
- **理由與解析**（對應 [[Ch03 真值表 (Truth Tables)]]）：
  - 根據邏輯蘊涵的定義，相應條件句 $(A_1 \cdot A_2 \cdot \dots \cdot A_n) \supset C$ 是**恆真句 (Tautology)**。因此當 $A_1, A_2, \dots, A_n$ 全部為真時，前件連言句為真，後件 $C$ 必然為真（不可能前提皆真而結論為假），故論證有效。

---

## 第二大題：語句集合一致性與不一致性證明（10%，共 2 題）

### (1) 檢驗集合 $\{\sim(A \cdot B), \ \sim(B \cdot C), \ \sim(A \cdot C), \ A \lor (B \cdot C)\}$
- **解答**：**一致的 (Consistent)**。
- **簡短真值表賦值證明**：
  - 令 **$V(A) = \mathbf{T}, \ V(B) = \mathbf{F}, \ V(C) = \mathbf{F}$**（對應形式賦值 $V(p)=T, V(q)=V(r)=F$）。
  - 核算四句真值：
    - $V(\sim(A \cdot B)) = \sim(\mathbf{T} \cdot \mathbf{F}) = \mathbf{T}$
    - $V(\sim(B \cdot C)) = \sim(\mathbf{F} \cdot \mathbf{F}) = \mathbf{T}$
    - $V(\sim(A \cdot C)) = \sim(\mathbf{T} \cdot \mathbf{F}) = \mathbf{T}$
    - $V(A \lor (B \cdot C)) = \mathbf{T} \lor (\mathbf{F} \cdot \mathbf{F}) = \mathbf{T}$
  - 四個語句同時為真，故語句集是**一致的**。

### (2) 檢驗集合 $\{\sim[J \lor (H \supset L)], \ L \equiv (\sim J \lor \sim H), \ H \equiv (J \lor L)\}$
- **解答**：**不一致的 (Inconsistent)**。
- **解法 A（簡短真值表逆向賦值法）**：
  1. 若要使第 1 句 $\sim[J \lor (H \supset L)] = \mathbf{T}$，則 $J \lor (H \supset L)$ 必為 $\mathbf{F}$ $\implies$ 強制決定 **$V(J) = \mathbf{F}$** 且 $V(H \supset L) = \mathbf{F}$；由 $H \supset L = \mathbf{F}$ 又強制決定 **$V(H) = \mathbf{T}$** 且 **$V(L) = \mathbf{F}$**！
  2. 將唯一可能的賦值 $V(J)=\mathbf{F}, V(H)=\mathbf{T}, V(L)=\mathbf{F}$ 代入第 2 句與第 3 句：
     - 第 2 句：$L \equiv (\sim J \lor \sim H) = \mathbf{F} \equiv (\mathbf{T} \lor \mathbf{F}) = \mathbf{F} \equiv \mathbf{T} = \mathbf{F}$！（無法為真）
     - 第 3 句：$H \equiv (J \lor L) = \mathbf{T} \equiv (\mathbf{F} \lor \mathbf{F}) = \mathbf{T} \equiv \mathbf{F} = \mathbf{F}$！（亦無法為真）
  3. 故所有語句不可能同時為真，集合**不一致**！
- **解法 B（自然演繹法直接導出矛盾句 —— 見 Ch. 5-5）**：
```text
  1. ~[J ∨ (H ⊃ L)]        p
  2. L ≡ (~J ∨ ~H)         p
  3. H ≡ (J ∨ L)           p
  4. ~J · ~(H ⊃ L)         1 DeM
  5. ~(H ⊃ L)              4 Simp
  6. ~(~H ∨ L)             5 Impl
  7. H · ~L                6 DeM, DN
  8. H                     7 Simp
  9. ~L                    7 Simp
 10. ~J                    4 Simp
 11. H ⊃ (J ∨ L)           3 Equiv, Simp
 12. J ∨ L                 8, 11 MP
 13. L                     10, 12 DS
 14. L · ~L                9, 13 Conj  (成功由語句集導出顯性矛盾，故不一致！)
```

---

## 第三大題：先用真值表法判定有效性，若有效再用推論規則證明（15%，共 2 題）

### (1) $1. \ P \supset Q \quad 2. \ R \supset S \quad 3. \ R \lor Q \ / \ \therefore P \lor S$
- **真值表判定**：**無效的 (Invalid)**。
  - **反例賦值**：令結論 $P \lor S = \mathbf{F} \implies$ **$V(P) = \mathbf{F}, \ V(S) = \mathbf{F}$**。
  - 代入前提 2 $R \supset S = \mathbf{T}$：因 $S=\mathbf{F}$，強制令 **$V(R) = \mathbf{F}$**。
  - 代入前提 3 $R \lor Q = \mathbf{T}$：因 $R=\mathbf{F}$，強制令 **$V(Q) = \mathbf{T}$**。
  - 檢查前提 1 $P \supset Q$：$\mathbf{F} \supset \mathbf{T} = \mathbf{T}$。
  - 故當 **$V(P)=\mathbf{F}, V(Q)=\mathbf{T}, V(R)=\mathbf{F}, V(S)=\mathbf{F}$** 時，前提皆真而結論為假，論證無效。

### (2) $1. \ \sim(A \lor \sim B) \quad 2. \ C \supset A \ / \ \therefore C \supset D$
- **真值表判定**：**有效的 (Valid)**。
  - 令結論 $C \supset D = \mathbf{F} \implies$ **$V(C) = \mathbf{T}, \ V(D) = \mathbf{F}$**。
  - 代入前提 2 $C \supset A = \mathbf{T}$：因 $C=\mathbf{T}$，強制得出 **$V(A) = \mathbf{T}$**。
  - 代入前提 1 $\sim(A \lor \sim B) = \mathbf{T} \implies A \lor \sim B = \mathbf{F} \implies$ 強制得出 **$V(A) = \mathbf{F}$**！與 $V(A)=\mathbf{T}$ 矛盾，故論證有效！
- **自然演繹法 7 步證明**：
```text
  1. ~(A ∨ ~B)             p
  2. C ⊃ A                 p          / ∴ C ⊃ D
  3. ~A · ~~B              1 DeM
  4. ~A                    3 Simp
  5. ~C                    2, 4 MT
  6. ~C ∨ D                5 Add      (用 Add 引進新字母 D！)
  7. C ⊃ D                 6 Impl     (由 Impl 轉為條件句結論！ Q.E.D.)
```

---

## 第四大題：不使用 IP 或 CP，只用 18 條推論規則證明（30%，共 3 題）

### (1) 綜合拆解題
```text
  1. P ⊃ ~R                p
  2. (S · N) ⊃ R           p
  3. ~S ⊃ Q                p
  4. ~(P ⊃ Q)              p          / ∴ ~N
  5. ~(~P ∨ Q)             4 Impl     (拆解否定條件句 ~(P ⊃ Q) 的標準起手式)
  6. P · ~Q                5 DeM, DN
  7. P                     6 Simp
  8. ~Q                    6 Simp
  9. ~R                    1, 7 MP
 10. ~~S                   3, 8 MT
 11. ~(S · N)              2, 9 MT
 12. ~S ∨ ~N               11 DeM
 13. ~N                    10, 12 DS  (Q.E.D.)
```

### (2) 一題三解經典題：$1. \ C \lor D \quad 2. \ C \supset B \quad 3. \ \sim C \supset \sim D \ / \ \therefore B$
```text
【解法一：利用 CD + Taut (最簡潔 7 步！)】
  1. C ∨ D                 p
  2. C ⊃ B                 p
  3. ~C ⊃ ~D               p          / ∴ B
  4. D ⊃ C                 3 Contra
  5. D ⊃ B                 2, 4 HS    (湊出與 C ⊃ B 共同後件的 D ⊃ B)
  6. B ∨ B                 1, 2, 5 CD (由建設性兩難律得出 B ∨ B！)
  7. B                     6 Taut     (由恆真律消去重複項得 B！)

【解法二：利用 CD + Impl + HS + Taut】
  4. D ⊃ C                 3 Contra
  5. B ∨ C                 1, 2, 4 CD
  6. ~B ⊃ C                5 DN, Impl
  7. ~B ⊃ B                2, 6 HS    (湊出 ~B ⊃ B 殺招！)
  8. ~~B ∨ B               7 Impl
  9. B                     8 DN, Taut

【解法三：先證出 C 再對前提 2 用 MP】
  4. ~C ⊃ D                1 DN, Impl
  5. D ⊃ C                 3 Contra
  6. ~C ⊃ C                4, 5 HS    (先證出 ~C ⊃ C)
  7. ~~C ∨ C               6 Impl
  8. C                     7 DN, Taut
  9. B                     2, 8 MP
```

### (3) 結合輸出律 (Exp)、異質換位律 (Contra)、假言三段論 (HS) 與 DeM
```text
  1. (A · B) ⊃ R           p
  2. A                     p
  3. C ⊃ ~R                p          / ∴ ~(C · B)
  4. A ⊃ (B ⊃ R)           1 Exp      (用輸出律把連言前件拆開！)
  5. B ⊃ R                 2, 4 MP    (用 A 拆下 B ⊃ R)
  6. ~R ⊃ ~B               5 Contra   (轉為逆否命題以便與前提 3 串聯)
  7. C ⊃ ~B                3, 6 HS    (由 HS 得 C ⊃ ~B)
  8. ~C ∨ ~B               7 Impl     (由 Impl 轉為選言句)
  9. ~(C · B)              8 DeM      (由 DeM 合併為 ~(C · B)！ Q.E.D.)
```

---

## 第五大題：使用推論規則（含 CP 與 IP）證明無前提邏輯定理（15%，共 3 題，每題皆附多重證法！）

### (1) 證明定理：$\vdash \{[\sim A \supset (D \cdot C)] \cdot \sim(B \cdot A)\} \supset (\sim C \supset \sim B)$
```text
【證法一：雙層巢狀 CP (Nested CP)】
  | 1. [~A ⊃ (D · C)] · ~(B · A)   AP         (外層 CP：假設主前件)
  | | 2. ~C                        AP         (內層 CP：假設後件的前件 ~C)
  | | 3. ~A ⊃ (D · C)              1 Simp
  | | 4. ~(B · A)                  1 Simp
  | | 5. ~B ∨ ~A                   4 DeM
  | | 6. ~C ∨ ~D                   2 Add      (用 Add 湊出 ~(D · C))
  | | 7. ~D ∨ ~C                   6 Comm
  | | 8. ~(D · C)                  7 DeM
  | | 9. ~~A                       3, 8 MT
  | | 10. ~B                       5, 9 DS    (得出內層目標後件 ~B)
  | 11. ~C ⊃ ~B                    2–10 CP    (先消去內層 AP)
 12. {[~A ⊃ (D · C)] · ~(B · A)} ⊃ (~C ⊃ ~B)  1–11 CP (再消去外層 AP！)

【證法二：單層 CP + Dist 割離多餘字母 D + Contra】
  | 1. [~A ⊃ (D · C)] · ~(B · A)   AP
  | 2. ~A ⊃ (D · C)                1 Simp
  | 3. ~(B · A)                    1 Simp
  | 4. ~B ∨ ~A                     3 DeM
  | 5. B ⊃ ~A                      4 Impl
  | 6. B ⊃ (D · C)                 2, 5 HS
  | 7. ~B ∨ (D · C)                6 Impl
  | 8. (~B ∨ D) · (~B ∨ C)         7 Dist     (用分配律割離多餘的 D！)
  | 9. ~B ∨ C                      8 Simp
  | 10. B ⊃ C                      9 Impl
  | 11. ~C ⊃ ~B                    10 Contra
 12. {[~A ⊃ (D · C)] · ~(B · A)} ⊃ (~C ⊃ ~B)  1–11 CP
```

### (2) 證明定理：$\vdash [(P \supset Q) \supset Q] \supset [(Q \supset P) \supset P]$
```text
【證法一：雙層巢狀 CP + Dist + Taut】
  | 1. (P ⊃ Q) ⊃ Q                 AP
  | | 2. Q ⊃ P                     AP
  | | 3. (P ⊃ Q) ⊃ P               1, 2 HS    (關鍵：直接對 1, 2 用 HS！)
  | | 4. ~(~P ∨ Q) ∨ P             3 Impl (x2)
  | | 5. (P · ~Q) ∨ P              4 DeM, DN
  | | 6. P ∨ (P · ~Q)              5 Comm
  | | 7. (P ∨ P) · (P ∨ ~Q)        6 Dist     (用 Dist 割離 ~Q！)
  | | 8. P ∨ P                     7 Simp
  | | 9. P                         8 Taut
  | 10. (Q ⊃ P) ⊃ P                2–9 CP
 11. [(P ⊃ Q) ⊃ Q] ⊃ [(Q ⊃ P) ⊃ P] 1–10 CP

【證法二：雙層 CP + 第三層內嵌 IP (三層封閉線！)】
  | 1. (P ⊃ Q) ⊃ Q                 AP
  | | 2. Q ⊃ P                     AP
  | | | 3. ~P                      AP         (第三層開啟 IP 假設 ~P)
  | | | 4. ~Q                      2, 3 MT
  | | | 5. ~(P ⊃ Q)                1, 4 MT
  | | | 6. ~(~P ∨ Q)               5 Impl
  | | | 7. P · ~Q                  6 DeM, DN
  | | | 8. P                       7 Simp
  | | | 9. P · ~P                  3, 8 Conj  (導出矛盾！)
  | | 10. P                        3–9 IP     (消去第三層 IP)
  | 11. (Q ⊃ P) ⊃ P                2–10 CP    (消去第二層 CP)
 12. [(P ⊃ Q) ⊃ Q] ⊃ [(Q ⊃ P) ⊃ P] 1–11 CP    (消去第一層 CP)
```

### (3) 證明選言型定理：$\vdash [(A \supset B) \cdot (B \supset C)] \lor (C \supset A)$
```text
【證法一：轉化為條件句 ~(C ⊃ A) ⊃ [(A ⊃ B) · (B ⊃ C)] 用 CP 證明】
  | 1. ~(C ⊃ A)                    AP         (假設右選言支的否定！)
  | 2. ~(~C ∨ A)                   1 Impl
  | 3. C · ~A                      2 DeM, DN  (拆出超好用的 C 與 ~A！)
  | 4. C                           3 Simp
  | 5. ~A                          3 Simp
  | 6. ~A ∨ B                      5 Add      (有了 ~A，用 Add + Impl 可變出任何 A ⊃ X！)
  | 7. A ⊃ B                       6 Impl
  | 8. C ∨ ~B                      4 Add      (有了 C，用 Add + Comm + Impl 可變出任何 X ⊃ C！)
  | 9. ~B ∨ C                      8 Comm
  | 10. B ⊃ C                      9 Impl
  | 11. (A ⊃ B) · (B ⊃ C)          7, 10 Conj
 12. ~(C ⊃ A) ⊃ [(A ⊃ B) · (B ⊃ C)]  1–11 CP
 13. ~~(C ⊃ A) ∨ [(A ⊃ B) · (B ⊃ C)] 12 Impl
 14. [(A ⊃ B) · (B ⊃ C)] ∨ (C ⊃ A)   13 DN, Comm

【證法二：直接使用間接證法 (IP) 假設整句結論的否定】
  | 1. ~{[(A ⊃ B) · (B ⊃ C)] ∨ (C ⊃ A)}   AP  (直接開啟 IP)
  | 2. ~[(A ⊃ B) · (B ⊃ C)] · ~(C ⊃ A)    1 DeM
  | 3. ~[(A ⊃ B) · (B ⊃ C)]               2 Simp
  | 4. ~(C ⊃ A)                           2 Simp
  | 5. ~(~C ∨ A)                          4 Impl
  | 6. C · ~A                             5 DeM, DN
  | 7. C                                  6 Simp
  | 8. ~A                                 6 Simp
  | 9. ~A ∨ B                             8 Add
  | 10. A ⊃ B                             9 Impl
  | 11. C ∨ ~B                            7 Add
  | 12. ~B ∨ C                            11 Comm
  | 13. B ⊃ C                             12 Impl
  | 14. (A ⊃ B) · (B ⊃ C)                 10, 13 Conj
  | 15. [(A ⊃ B) · (B ⊃ C)] · ~[(A ⊃ B) · (B ⊃ C)]  3, 14 Conj (與第 3 列矛盾！)
 16. [(A ⊃ B) · (B ⊃ C)] ∨ (C ⊃ A)        1–15 IP
```

---

## 第六部分：歷屆邏輯小考 (1) ~ (6) 全套詳解彙整（共 7 份小考卷）

### 1. 邏輯小考 (1) 解答（2024.09.19 —— Ch. 1 是非題 10 題精析）
> **對應原始檔案**：`raw/Quiz1_Ch01_邏輯小考1解答_20240919.docx`

| 題號 | 題目敘述 | 答案 | 核心邏輯理由與在地化實例 |
| :-: | :--- | :-: | :--- |
| 1 | 一個前提與結論都真的論證不必然是有效的論證。 | **`O`** | 無法單憑前提與結論皆真判定有效性。可能有效（如：清華在新竹且台大在台北 $\therefore$ 清華在新竹），也可能無效（如：清華在新竹 $\therefore$ 台大在台北）。 |
| 2 | 一個結論為假的有效論證的前提必然都為假。 | **`X`** | 前提不必然「都」為假，而是「**至少有一為假**」。 |
| 3 | 一個有效論證的結論有可能為真，也有可能為假。 | **`O`** | 有效論證只排除「前提都真而結論為假」，其餘 3 種真值條件皆可能。 |
| 4 | 若一個論證是無效的，則無法判定其前提與結論的真值。 | **`O`** | 無效論證可搭配全部 4 種前提與結論的實際真假組合。 |
| 5 | 一個健全論證的結論不可能為假。 | **`O`** | 健全論證 = 有效 + 前提皆真，故結論必然為真。 |
| 6 | 一個一致的語句集中的所有語句有可能都為假。 | **`O`** | 只要它們在邏輯上*有可能*同時為真即可。例：$\{\text{清華在澎湖}, \text{台大在金門}\}$ 是一致的，但事實上皆為假。 |
| 7 | 一個不一致的語句集中的所有語句有可能都為真。 | **`X`** | 根據不一致性的定義，它們在邏輯上不可能同時為真。 |
| 8 | 前提集一致的有效論證，其結論必然為真。 | **`X`** | 前提集一致只代表「前提有可能同時為真」，不代表「前提事實上都為真」。例：若清華在新竹則十八尖山在高雄(F)；清華在新竹(T) $/ \therefore$ 十八尖山在高雄(F)。 |
| 9 | 具有一個不一致的前提集的論證必然是有效的。 | **`O`** | 前提集不一致代表前提不可能同時為真，故絕不可能發生「前提都真且結論為假」，依定義必然有效（特殊有效論證 I）。 |
| 10 | 一個結論為假的有效論證，其前提集必然是不一致的。 | **`X`** | 結論為假的有效論證只代表前提在事實上至少有一為假，但其前提集**可以是一致的**（見第 8 題十八尖山在高雄例），也**可以是不一致的**（如：清華在新竹且清華不在新竹 $/ \therefore$ 十八尖山在高雄）。 |

---

### 2. 邏輯小考 (2) 解答（2024.09.26 —— Ch. 2 語句邏輯符號化 5 題）
> **對應原始檔案**：`raw/Quiz2_Ch02_邏輯小考2解答_20240926.docx`

1. **「如果我們不控制貨幣供給或不打破石油輸出國家組織 (OPEC) 的力量，我們將無法控制通貨膨脹。」**
   - **Ans.**：**$(\sim M \lor \sim O) \supset \sim I$** 或 **$\sim(M \cdot O) \supset \sim I$**（亦等值於 $I \supset (M \cdot O)$）。
2. **「如果小明有好的畢業成績 ($G$)，那麼他就會找到好工作 ($J$) 且賺很多錢 ($L$)——假如他沒有追求其他目標 ($O$) 的話。」**
   - **Ans.**：**$G \supset [\sim O \supset (J \cdot L)]$** 或 **$\sim O \supset [G \supset (J \cdot L)]$** 或 **$(G \cdot \sim O) \supset (J \cdot L)$**。
3. **「既非下雨 ($R$)、也非下雪 ($S$)、也非天色昏暗 ($G$)，將會阻止你去郊遊。」**
   - **Ans.**：**$(\sim R \cdot \sim S) \cdot \sim G$** 或 **$\sim[(R \lor S) \lor G]$**。
4. **「如果我們增加稅收 ($T$) 並消除政府浪費支出 ($S$)，那麼，除非有自然的大災害 ($N$)，否則赤字將會降低 ($D$)。」**
   - **Ans.**：**$(T \cdot S) \supset (N \lor D)$** 或 **$(T \cdot S) \supset (\sim N \supset D)$**。
5. **「並非小明 ($A$) 與小華 ($B$) 兩者都是笨蛋，但小芬 ($C$) 卻是。」**
   - **Ans.**：**$\sim(A \cdot B) \cdot C$** 或 **$(\sim A \lor \sim B) \cdot C$**。

---

### 3. 邏輯小考 (3) 解答（2024.10.03 真值表題 & 2023.10.24 觀念單選題 10 題）
> **對應原始檔案**：`raw/Quiz3_Ch03_邏輯小考3解答_20241003.docx`、`raw/Quiz3_Ch01_to_Ch03_邏輯小考3解答_20231024_選擇題.docx`

#### (A) 2024.10.03 小考 (3) 簡短真值表三題
1. $1. \ \sim(A \lor \sim B) \quad 2. \ C \supset A \ / \ \therefore C \supset D$ $\implies$ **有效 (Valid)**（令 $V(C)=T, V(D)=F \implies V(A)=T \implies V(\sim(A \lor \sim B))=F$ 矛盾！即 Ex 3-8(17) 與期中考第三大題第 2 題）。
2. $1. \ A \supset B \quad 2. \ (\sim B \cdot C) \lor \sim A \ / \ \therefore B$ $\implies$ **無效 (Invalid)**（當 **$V(A)=\mathbf{F}, \ V(B)=\mathbf{F}, \ V(C)=\mathbf{T}$** 時，前提皆真而結論為假！即 Ex 3-10(7)）。
3. 檢驗語句集 $\{B \supset A, \ C \supset B, \ \sim C \cdot A\}$ $\implies$ **一致的 (Consistent)**（當 **$V(A)=\mathbf{T}, \ V(C)=\mathbf{F}, \ V(B)=\mathbf{F}$ [或 T]** 時三句同時為真！即 Ex 3-11(1)）。

#### (B) ⭐ 2023.10.24 小考 (3) 經典單選題 10 題（含極高頻陷阱第 2, 5, 8, 9, 10 題！）
1. **一個前提都真的有效論證之結論必然是**：**(1) 真的**。
2. **一個「沒有前提都真且結論為假」（即在現實事實中並非前提皆真而結論假）的論證必然是**：**(3) 無法判定**！
   - *解析*：單看一個論證在*現實世界這一列*不是「前提皆真結論假」，完全無法判定它是否有效！因為一個「前提與結論在事實上都為真」的論證，有可能是有效論證（若清華在新竹則十八尖山在新竹；清華在新竹 $/ \therefore$ 十八尖山在新竹），也可能是**無效論證**（清華在新竹 $/ \therefore$ 十八尖山在新竹）！要有效，必須在**所有可能世界（真值表所有列）**都不可能前提皆真而結論為假！
3. **一個結論為假的有效論證，其前提集必然是**：**(3) 無法判定**（可能一致，也可能不一致）。
4. **前提一致的有效論證，其結論必然為**：**(3) 無法判定**（可能為真，也可能為假）。
5. **$A \supset (\sim A \supset B)$ 不具有下列哪一個語句形式？**
   - 選項：(1) $p \supset q$ \quad (2) $p \supset (\sim p \supset q)$ \quad **(3) $p \supset (\sim p \supset p)$** \quad (4) $p \supset (q \supset r)$。
   - **Ans.**：**`(3)`**！因為在 (3) 中最後一個變元也是 $p$，若一致取代必須得出 $A \supset (\sim A \supset A)$，唯有經由**不一致的非法取代**才會得出 $A \supset (\sim A \supset B)$！
6. **「除非明天下雨 ($A$)，否則我會去郊遊 ($B$)。」不可符號化為下列何者？**
   - 選項：(1) $A \lor B$ \quad (2) $\sim A \supset B$ \quad (3) $\sim B \supset A$ \quad **(4) $A \supset \sim B$**。
   - **Ans.**：**`(4)`**！（$A \lor B \equiv \sim A \supset B \equiv \sim B \supset A$ 三者完全等值；但 $A \supset \sim B$ 是「如果下雨我就不去郊遊」，不等值！）。
7. **假定 $V(A)=V(B)=\mathbf{T}, \ V(C)=V(D)=\mathbf{F}, \ V(Q)=V(R)=\text{？}$，則 $[(A \cdot D) \equiv Q] \supset [C \supset (R \cdot B)]$ 的真值為**：**(2) 真 (`T`)**！
   - *解析*：不用管前件含有未知的 $Q$！直接看主條件句的**後件** $[C \supset (R \cdot B)]$：因為 $V(C) = \mathbf{F}$，$C \supset (R \cdot B)$ 的前件為假，故後件 $[C \supset (R \cdot B)]$ **必為 `T`**！而主條件句只要後件為 `T`，整句必然為 **`T`**！
8. **下列哪一個不是 $\sim p \lor (q \supset r)$ 的取代實例？**
   - 選項：(1) $\sim(A \supset B) \lor (A \supset B)$ \quad (2) $\sim(C \lor B) \lor [(A \cdot C) \supset B]$ \quad **(3) $\sim C \lor A$**。
   - **Ans.**：**`(3)`**！因為取代只能針對單一變元進行，不能用一個原子語句 $A$ 把帶有邏輯結構的 $(q \supset r)$ 取代掉（語句的邏輯結構絕對不能比其形式更簡單！）。
9. ⭐ **有效論證的形式是 (The form of a valid argument is)**：**(3) 無法判定（可能有效，也可能無效）**！
   - *深度解析*：**每一個有效論證都同時具有有效形式與無效形式**！
     - 它必然至少具有一個**無效的論證形式**：即最粗糙的原子形式 $p_1, p_2, \dots, p_n / \therefore q$！
     - 它也必然至少具有一個**有效的論證形式**：即由其前提與結論的一對一展開形式（Expanded Form）所構成的論證形式！
10. ⭐ **無效的論證形式之取代實例是**：**(3) 無法判定（可能是有效論證，也可能是無效論證）**！
    - *深度解析*：以無效論證形式 $p / \therefore q$ 為例：
      - 它的取代實例 $A / \therefore B$ 是**無效論證**；
      - 但它的另一個取代實例 $A / \therefore B \supset B$（結論代入恆真句，或代入 $A / \therefore A$）卻是**有效論證**！

---

### 4. 邏輯小考 (4) & 小考 (5) 解答（Ch. 4 自然演繹法 18 條規則證明）
> **對應原始檔案**：`raw/Quiz4_Ch04_邏輯小考4解答_20241024.docx`、`raw/Quiz5_Ch04_邏輯小考5解答_20231107.docx`

- **小考 (4) 第 1 題**：$1. \ \sim(H \lor \sim K) \quad 2. \ L \supset H \ / \ \therefore L \supset M$ （即 Ex 4-8 (7)，用 DeM $\rightarrow$ Simp $\rightarrow$ MT 得 $\sim L$ $\rightarrow$ 用 **Add** 得 $\sim L \lor M$ $\rightarrow$ 用 **Impl** 得 $L \supset M$）。
- **小考 (4) 第 2 題**：$1. \ [(A \cdot B) \cdot D] \lor (C \cdot A) \ / \ \therefore A$ （即 Ex 4-11 (9)，用 Assoc $\rightarrow$ Comm $\rightarrow$ **逆向 Dist 提公因式**得 $A \cdot [(B \cdot D) \lor C]$ $\rightarrow$ **Simp** 得 $A$）。
- **小考 (5) 第 1 題（雙解法）**：$1. \ (A \cdot B) \lor (C \cdot D) \quad 2. \ \sim C \ / \ \therefore A$ （即 Ex 4-8 (13)：**證法一**對 $\sim C$ 用 Add 得 $\sim C \lor \sim D \xrightarrow{\text{DeM}} \sim(C \cdot D) \xrightarrow{\text{DS}} A \cdot B \xrightarrow{\text{Simp}} A$；**證法二**對前提 1 用 **Dist** 得 $[(A \cdot B) \lor C] \cdot [(A \cdot B) \lor D] \xrightarrow{\text{Simp}} (A \cdot B) \lor C \xrightarrow{\text{DS}} A \cdot B \xrightarrow{\text{Simp}} A$）。
- **小考 (5) 第 2 題**：$1. \ A \supset B \quad 2. \ C \supset D \quad 3. \ (B \lor D) \supset E \quad 4. \ \sim E \ / \ \therefore \sim(A \lor C)$ （不用 IP 的正向證法：由 3, 4 MT 得 $\sim(B \lor D) \xrightarrow{\text{DeM}} \sim B \cdot \sim D \xrightarrow{\text{Simp}} \sim B, \sim D \xrightarrow{\text{MT}} \sim A, \sim C \xrightarrow{\text{Conj}} \sim A \cdot \sim C \xrightarrow{\text{DeM}} \sim(A \lor C)$）。

---

### 5. ⭐ 邏輯小考 (6) 解答（2023.11.14 —— Ch. 5 無前提定理之「一題三解」與「一題四解」！）
> **對應原始檔案**：`raw/Quiz6_Ch05_邏輯小考6解答_20231114.docx`

#### 第一題：證明鄧斯·司各脫定理 (Duns Scotus' Law) $\vdash \sim A \supset (A \supset B)$（一題三解！）
```text
【證明一：雙層巢狀 CP + Add + DS】         【證明二：直接用 IP 拆解否定條件句】
  | 1. ~A                  AP                 | 1. ~[~A ⊃ (A ⊃ B)]     AP
  | | 2. A                 AP                 | 2. ~[~~A ∨ (~A ∨ B)]   1 Impl (x2)
  | | 3. A ∨ B             2 Add              | 3. ~A · (A · ~B)       2 DeM (x2), DN (x2)
  | | 4. B                 1, 3 DS            | 4. (~A · A) · ~B       3 Assoc
  | 5. A ⊃ B               2–4 CP             | 5. ~A · A              4 Simp (矛盾！)
  6. ~A ⊃ (A ⊃ B)          1–5 CP             6. ~A ⊃ (A ⊃ B)          1–5 IP

【證明三：最簡潔單層 CP + Add + Impl（僅需 5 步！）】
  | 1. ~A                  AP         (只假設最外層前件 ~A！)
  | 2. ~A ∨ B              1 Add      (直接對 ~A 用 Add 加上 ∨ B)
  | 3. A ⊃ B               2 Impl     (由 Impl 直接變成後件 A ⊃ B！)
  4. ~A ⊃ (A ⊃ B)          1–3 CP     (Q.E.D.)
```

#### 第二題：證明定理 $\vdash \{[S \lor (T \supset R)] \cdot [(S \supset T) \cdot \sim(T \supset R)]\} \supset T$（一題四解！）
```text
【證明一：外層 CP + 內層 IP】              【證明二：單層 CP + Add + Impl + CD + Taut】
  | 1. [S∨(T⊃R)]·[(S⊃T)·~(T⊃R)]  AP           | 1. [S∨(T⊃R)]·[(S⊃T)·~(T⊃R)]  AP
  | | 2. ~T                      AP (IP)      | 2. S ∨ (T ⊃ R)               1 Simp
  | | 3. S ∨ (T ⊃ R)             1 Simp       | 3. S ⊃ T                     1 Simp (x2)
  | | 4. S ⊃ T                   1 Simp (x2)  | 4. ~(T ⊃ R)                  1 Simp (x2)
  | | 5. ~(T ⊃ R)                1 Simp (x2)  | 5. ~(T ⊃ R) ∨ T              4 Add
  | | 6. ~S                      2, 4 MT      | 6. (T ⊃ R) ⊃ T               5 Impl
  | | 7. T ⊃ R                   3, 6 DS      | 7. T ∨ T                     2, 3, 6 CD
  | | 8. (T ⊃ R) · ~(T ⊃ R)      5, 7 Conj    | 8. T                         7 Taut
  | 9. T                         2–8 IP       9. {[...] ⊃ T}                 1–8 CP
 10. {[...] ⊃ T}                 1–9 CP

【證明三：單層 CP + DS + MP (7 步)】       【證明四：神級觀察！只拆 ~(T ⊃ R) 6 步秒殺！】
  | 1. [S∨(T⊃R)]·[(S⊃T)·~(T⊃R)]  AP           | 1. [S∨(T⊃R)]·[(S⊃T)·~(T⊃R)]  AP
  | 2. S ∨ (T ⊃ R)               1 Simp       | 2. ~(T ⊃ R)                  1 Simp (x2)
  | 3. S ⊃ T                     1 Simp (x2)  | 3. ~(~T ∨ R)                 2 Impl
  | 4. ~(T ⊃ R)                  1 Simp (x2)  | 4. ~~T · ~R                  3 DeM
  | 5. S                         2, 4 DS      | 5. T                         4 Simp, DN (直接拿到 T！)
  | 6. T                         3, 5 MP      6. {[...] ⊃ T}                 1–5 CP
  7. {[...] ⊃ T}                 1–6 CP       *(連前兩個連言支 S∨(T⊃R) 與 S⊃T 都不用看，因為 ~(T⊃R) 本身就蘊涵 T！)*
```
