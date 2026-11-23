---
title: "習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)"
category: exercises
chapters: ["Ch. 1", "Ch. 2", "Ch. 3"]
source: "Ex_Ch01_習題解答.docx, Ex_Ch02_習題解答.docx, Ex_Ch03_習題解答.docx, Supp_Ch02_Ch03_關於實質條件句的定義補充.docx, Supp_Ch03 PDFs (p.57-67, 81, 388)"
tags: [logic, exercise, argument, explanation, validity, soundness, truth-table, short-truth-table, substitution-instance, justification]
updated: 2026-11-23
---

# 習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)

> **涵蓋章節**：[[Ch01 邏輯導論 (Introduction to Logic)]]、[[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]]、[[Ch03 真值表 (Truth Tables)]]
> **對應原始題庫檔案**：`raw/Ex_Ch01_習題解答.docx`、`raw/Ex_Ch02_習題解答.docx`、`raw/Ex_Ch03_習題解答.docx`、`raw/Supp_Ch02_Ch03_關於實質條件句的定義補充.docx`、`raw/Supp_Ch03_WalkThrough_Substitution_Instances_Ex3-3_p57-59.pdf`、`raw/Supp_Ch03_WalkThrough_Construct_Truth_Table_p63-65.pdf`、`raw/Supp_Ch03_Logical_Equivalence_Ex3-7_p67.pdf`、`raw/Supp_Ch03_Exercise_3-12_Justification_of_Truth_Tables_p81.pdf`、`raw/Supp_Ch03_Exercise_3-11_3-12_Answers_p388.pdf`
> **對應概念**：[[論證與解釋 (Argument vs Explanation)]]、[[有效性與健全性 (Validity and Soundness)]]、[[一致性與反例集 (Consistency and Counterexample Set)]]、[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]、[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]
> **對應方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]
> **延伸期中考真題**：[[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]]

本頁完整彙整並解析 Ch. 1、Ch. 2、Ch. 3 課堂講義、中文習題解答檔與原文書補充頁中的所有題型與標準詳解。

---

## 第一部分：Ch. 1 論證 vs. 因果解釋、Exercise 1-3 真值與有效性推理

### 1. 辨識「理由證成 (論證)」與「因果說明 (解釋)」
- **判準（詳見 [[論證與解釋 (Argument vs Explanation)]]）**：
  - **因果解釋 (Explanation)**：說話者已預設結果為既定事實，提出原因說明其如何發生。
    - 例 1：「新竹風很大，因為新竹三面環山一面臨海，形成喇叭狀地形。」
    - 例 2：「小珍很氣他，因為他撞壞了她的車。」
  - **論證 (Argument)**：結論尚待確立或有爭議，提出前提作為理據以說服聽者接受結論。
    - 例 3：「小珍**應該**很氣他（結論），因為他撞壞了她的車（前提）。」
    - 例 4：「我們**應該**限制溫室氣體的排放（結論），因為它們正在破壞地球的大氣臭氧層（前提）。」

---

### 2. Exercise 1-3 標準詳解（對應 `raw/Ex_Ch01_習題解答.docx`）

#### (1) Can an argument have all true premises and a true conclusion, yet not be deductively valid?（一個論證是否可能所有前提與結論皆為真，卻不是演繹有效的？）
- **標準解答**：**是的，一個前提與結論都為真的論證有可能是無效的**。
  - **在地化經典例子**：
    1. $1+1=2$ `(T)`
    2. 清華大學旁有座十八尖山 `(T)`
    $/ \ \therefore 3.$ 貢丸與米粉是新竹名產 `(T)`
  - **形式證明為何無效**：
    - 此論證的形式為：`1. p, 2. q / ∴ 3. r`。
    - 具有這個論證形式的論證，完全有可能前提都真但結論卻為假。例如：
      1. $1+1=2$ `(T)`
      2. 清華大學旁有座十八尖山 `(T)`
      $/ \ \therefore 3.$ 台灣是南太平洋中的一座島嶼 `(F)`
    - 根據有效論證的定義，上述論證是**無效的 (Invalid)**。

#### (3) Can a deductively valid argument have false premises?（演繹有效論證是否可能有假前提？）
- **標準解答**：**是的，一個有效論證可能有假的前提**。因為有效論證只排除一種情況（即「前提都真但結論卻為假」）。
  - **在地化經典例子**（選言三段論 $p \lor q, \sim q / \therefore p$）：
    1. 清華大學旁有座十八尖山，或者貢丸與米粉是新竹名產 `(T)`
    2. 貢丸與米粉**不是**新竹名產 `(F)`
    $/ \ \therefore 3.$ 清華大學旁有座十八尖山 `(T)`
  - 此論證在形式上是**有效論證**，但其前提 2 為假。

#### (5) Can a deductively invalid argument have a true conclusion?（演繹無效論證是否可能有真結論？）
- **標準解答**：**是的，一個無效論證有可能有一個真的結論**。例如第 (1) 題的例子（前提「$1+1=2$」、「清華大學旁有座十八尖山」，結論「貢丸與米粉是新竹名產」為真，但論證無效）。

#### (7) Can an argument be sound but not valid?（一個論證是否可能健全但卻無效？）
- **標準解答**：**不可能！一個健全論證 (Sound Argument) 絕對不可能是一個無效論證**。因為根據定義，健全論證就是一個「所有前提都為真的**有效論證**」（詳見 [[有效性與健全性 (Validity and Soundness)]]）。

#### (9) Have we proved that the conclusion of a deductively valid argument is true when we have established that its premises are all true?（當我們確立了一個演繹有效論證的所有前提皆為真時，是否就證明了其結論為真？）
- **標準解答**：**是的**。根據有效論證的定義，一個有效論證當其前提都為真時，結論也**必然為真**（因為有效論證在邏輯上不可能前提都真但結論卻為假）。

#### (11) Can some members of an inconsistent set of sentences be true?（一個不一致的語句集中的部分成員是否可能為真？）
- **標準解答**：**是的，一個不一致的語句集中的部分語句有可能為真**（只是不可能*所有*成員*同時*為真）。
  - **在地化經典例子**：語句集 $\{\text{「貢丸與米粉是新竹名產」}, \ \text{「貢丸與米粉不是新竹名產」}\}$ 是不一致的，但其中第一句「貢丸與米粉是新竹名產」在事實上為真！（詳見 [[一致性與反例集 (Consistency and Counterexample Set)]]）。

#### 原文書 p.14 Exercise 1-3 偶數題與後段題目完整補齊（第 2, 4, 6, 8, 10, 12, 13, 14, 15 題 & Philosophical Discussions）
- **(2) Can an inductively strong argument have all true premises and a false conclusion?（歸納強論證是否可能前提皆真而結論為假？）**
  - **Ans.**：**是的 (Yes)**！歸納強論證的前提為真時，只是使結論**很可能 (Probably)** 為真，而非邏輯必然為真（例如過去每隻看到的天鵝都是白的 (T) $/ \therefore$ 下一隻天鵝也是白的 (F，澳洲黑天鵝)）。
- **(4) Can a deductively valid argument have a false conclusion?（演繹有效論證是否可能有假結論？）**
  - **Ans.**：**是的 (Yes)**！只要前提中**至少有一個為假**，有效論證就可以有假的結論（例如：若清華大學在新竹，則十八尖山在高雄 (F)；清華大學在新竹 (T) $/ \therefore$ 十八尖山在高雄 (F)）。
- **(6) Can a deductively valid argument have all true premises and a false conclusion?（演繹有效論證是否可能前提皆真而結論為假？）**
  - **Ans.**：**絕對不可能 (No)**！這正是演繹有效論證的定義所唯一排除的禁區。
- **(8) Can a deductively valid argument be sound, yet have a false conclusion?（健全論證是否可能有假結論？）**
  - **Ans.**：**絕對不可能 (No)**！因為健全論證（Sound Argument）定義為「有效 + 所有前提皆為真」，而有效論證在前提皆為真時，結論**必然為真**。
- **(10) Can all the members of a consistent set of sentences be false?（一致語句集中的所有成員是否可能全部為假？）**
  - **Ans.**：**是的 (Yes)**！一致（Consistent）只要求「邏輯上*有可能*同時為真」，並不代表它們在現實中為真（例如 $\{\text{清華大學在澎湖 (F)}, \ \text{台灣大學在金門 (F)}\}$ 是一致的，但現實中兩句皆為假）。
- **(12) Can all members of an inconsistent set of sentences be true?（不一致語句集中的所有成員是否可能全部為真？）**
  - **Ans.**：**絕對不可能 (No)**！根據不一致（Inconsistent）的定義，它們在邏輯上不可能同時為真。
- **(13) List two English words that commonly signal premises of arguments.**
  - **Ans.**：*Because, since, for, given that, as*.（中文：因為、既然、由於、鑑於）。
- **(14) List two English words that commonly signal conclusions of arguments.**
  - **Ans.**：*Therefore, thus, hence, consequently, so, it follows that*.（中文：所以、因此、因而、由此可見）。
- **(15) What is the difference between the context of discovery and the context of justification? Which one is the concern of logic?**
  - **Ans.**：發現的脈絡（Context of Discovery）探討人們如何想出某個點子的心理或歷史過程；證成的脈絡（Context of Justification）探討提出什麼理由與證據來支持或證明某個結論。**邏輯學唯一關心的是「證成的脈絡」**。
- **Philosophical Discussions（原文書 p.14 模態概念討論）**：
  1. **可能性（Possibility）的不同意義**：除了**邏輯可能性 (Logical Possibility，無邏輯矛盾)** 之外，還有**物理／自然律可能性 (Physical / Nomological Possibility，不違反自然科學定律)**、**技術可能性 (Technological Possibility)** 與**認識論可能性 (Epistemic Possibility，就我們目前所知可能為真)**。邏輯可能性範圍最廣（例如「人一秒鐘跳上月球」在物理上不可能，但在邏輯上是可能的！）。
  2. **用「必然性 ($\Box$)」與「否定 ($\sim$)」定義「矛盾 (Contradiction)」與「可能性 ($\Diamond$)」**：
     - $p$ 是矛盾句（不可能為真）：$\Box \sim p$（必然非 $p$）。
     - $p$ 是可能的（$\Diamond p$）：$\sim \Box \sim p$（並非必然非 $p$）。
  3. **「一個假陳述句可能為真 (A false statement could possibly be true)」是什麼意思？**
     - 意思是該陳述句雖然在現實世界（Actual World）事實上為假，但它本身**不是矛盾句**（它是**適真句 Contingent Sentence**），在某個邏輯可能世界（Possible World / 某列真值表賦值）中它可以為真！

---

## 第二部分：Ch. 2 語句邏輯符號化（Exercise 2-7 & Exercise 2-10）

### 1. 原文書 p.44–45 經典符號化範例、Exercise 2-6 與 Exercise 2-7 全解

#### (A) 原文書 p.44–45 劃線重點例題（對應 `raw/Supp_Ch02_Symbolizing_Examples_Ex2-6_p44-45.pdf` & 邏輯小考 2）
- **雙重檢查法 (Double-Check Method)**：符號化完畢後，暫時忘掉原英文/中文句子，把你寫出的邏輯式**直接直譯回自然語言**，比較兩者的真值條件是否完全相同！
- **例題 7（雙重條件句與輸出律 Exp 預備）**：
  - *"If Melissa graduates with a strong academic record ($G$), she gets a good job ($J$) and makes lots of money ($L$) — if she doesn't pursue other goals ($O$)."*
  - **兩種等價符號化**：**$(G \cdot \sim O) \supset (J \cdot L)$** 或 **$G \supset [\sim O \supset (J \cdot L)]$**（亦可寫為 $\sim O \supset [G \supset (J \cdot L)]$）。
- **例題 9（否定選言 vs. 連言）**：
  - *"Melissa doesn't make lots of money ($L$) or pursue other goals ($O$), but she does graduate with a strong academic record ($G$) and she gets a good job ($J$)."*
  - 注意前半句「doesn't ($L$ or $O$)」意思是既沒賺大錢也沒追求其他目標：**$(\sim L \cdot \sim O) \cdot (G \cdot J)$** 或 **$\sim(L \lor O) \cdot (G \cdot J)$**。
- **例題 10（小考 2 第 1 題原型！）**：
  - 原文書例題 10：*"If we don't control the money supply ($M$) and break the power of OPEC ($O$), we won't control inflation ($I$)."*
  - 原文書註解提醒：此句英文的意思是「除非我們**同時做到 $M$ 與 $O$ 兩件事**，否則無法控制通膨」，即 $\sim(M \cdot O) \supset \sim I$，取逆否命題即為 **$I \supset (M \cdot O)$**（若小考中文寫為「如果不控制貨幣供給**或**不打破 OPEC 力量，將無法控制通膨」，則直譯為 $(\sim M \lor \sim O) \supset \sim I \equiv \sim(M \cdot O) \supset \sim I$，兩者由 DeM 完全等值！）。

#### (B) Exercise 2-6 全套 12 題標準解答（原文書 p.45）
> 字典：$A =$ Art attends class; $G =$ Art graduates; $H =$ Art completes his homework; $L =$ Art does well in logic; $M =$ Art does well in math; $P =$ Art does well in philosophy; $T =$ Art pays tuition; $W =$ Art does well in all his classes.

1. *"Art does not do well in either logic or math."*（既不 L 也不 M）：**$\sim(L \lor M)$** 或 **$\sim L \cdot \sim M$**
2. *"If Art completes his homework, he does well in both logic and math."*：**$H \supset (L \cdot M)$**
3. *"If Art does not complete his homework, he does well in neither logic nor math."*：**$\sim H \supset \sim(L \lor M)$** 或 **$\sim H \supset (\sim L \cdot \sim M)$**
4. *"If Art does well in logic or math, he graduates."*：**$(L \lor M) \supset G$**
5. *"Art graduates only if he does well in logic or math."*（`only if` 後接必要條件放後件）：**$G \supset (L \lor M)$**
6. *"If Art neither pays tuition nor attends classes, he does not graduate."*：**$(\sim T \cdot \sim A) \supset \sim G$** 或 **$\sim(T \lor A) \supset \sim G$**
7. *"Art does well in logic if he completes his homework and attends class."*（`if` 後接充分條件放前件）：**$(H \cdot A) \supset L$**
8. *"Art does well in logic only if he either completes his homework or attends class."*：**$L \supset (H \lor A)$**
9. *"If Art pays his tuition, he graduates, unless he doesn't attend class."*（除非 $\sim A$，否則 $T \supset G$）：**$A \supset (T \supset G)$** 或 **$(T \cdot A) \supset G$** 或 **$(T \supset G) \lor \sim A$**
10. *"Art does well in all his classes if he does well in logic and philosophy."*：**$(L \cdot P) \supset W$**
11. *"Art does well in all his classes unless he doesn't do well in logic or philosophy."*：**$(L \cdot P) \supset W$** 或 **$W \lor \sim(L \cdot P)$** 或 **$W \lor (\sim L \lor \sim P)$**
12. *"Art does well in all his classes only if he does well in logic, philosophy, and math."*：**$W \supset [L \cdot (P \cdot M)]$**

#### (C) Exercise 2-7 奇數題完整符號化解答（對應 `raw/Ex_Ch02_習題解答.docx`）
1. *"If nothing is perfect, then I can't be blamed for my mistakes."* ($N =$ "nothing is perfect"; $B =$ "I can be blamed for my mistakes")
   - **Ans.**：$N \supset \sim B$
3. **Ans.**：$(N \cdot M) \supset \sim B$
5. **Ans.**：$E \supset (\sim M \cdot \sim B)$
7. **Ans.**：$M \equiv H$
9. **Ans.**：$D \supset G$
11. **Ans.**：$\sim(S \cdot G) \supset \sim D$ 或 $\sim D \lor (S \cdot G)$
13. **Ans.**：$\sim C \cdot \sim L$ 或 $\sim(C \lor L)$ （Neither $C$ nor $L$）
15. **Ans.**：$M \cdot (S \lor B)$
17. **Ans.**：$S \supset (B \lor H)$ 或 $S \supset (\sim H \supset B)$ （If $S$, then $B$ unless $H$）
19. **Ans.**：$(\sim D \cdot \sim E) \supset G$ 或 $\sim(D \lor E) \supset G$
21. **Ans.**：$(\sim D \cdot \sim E) \cdot \sim G$ 或 $\sim(D \lor E) \cdot \sim G$
23. **Ans.**：$B \cdot (\sim W \supset O)$ 或 $B \cdot (\sim O \supset \sim W)$
25. **Ans.**：$D \supset (T \cdot S)$
27. **Ans.**：$T \cdot (\sim D \supset S)$ 或 $T \cdot (\sim S \supset \sim D)$
29. **Ans.**：$(T \cdot S) \supset (N \lor D)$ 或 $(T \cdot S) \supset (\sim N \supset D)$

---

### 2. Exercise 2-10 真值函應與原子/複合語句深度觀念題（對應 `raw/Ex_Ch02_習題解答.docx`）

#### (1) What's wrong with abbreviating the sentence "George Plimpton is not a public figure" by the letter $P$?
- **標準解答**：因為 *"George Plimpton is not a public figure"* 是一個**否定句（複合語句）**，而單一大寫字母 $P$ 代表的是**原子語句 (Atomic Sentence)**。在邏輯上，原子語句 $P$ 不含有任何邏輯連詞，若直接縮寫為 $P$，就無法顯示出該句內部含有否定連詞 $\sim$ 的邏輯結構（正確做法應設 $P =$ "George Plimpton is a public figure"，並將原句符號化為 **$\sim P$**）。

#### (3) Why isn't the expression "It is well known that..." truth-functional?（為什麼「眾所周知……」不是真值函應連詞？）
- **標準解答**：*"It is well known that..."* 不是真值函應的，因為**某些為真的語句是眾所周知的，但另一些同樣為真的語句卻不是眾所周知的**！
  - 例如：設成分語句皆為真，「眾所周知 $2+2=4$」這句話為**真 (`T`)**；但是「眾所周知小明愛小華」（假設小明真的暗戀小華，故「小明愛小華」為真）卻為**假 (`F`)**！成分語句真值固定為 T，複合句真值卻不唯一，這直接違反了[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]的**真值函應原則**。

#### (5) Is the sentence "Lady Gaga and Stefani Joanne Angelina Germanotta are well-known public figures" atomic or compound?
- **標準解答**：這是一個**複合語句 (Compound Sentence)**！因為此處的 *"and"* 並沒有「共同或一起相互做某事」的意思。原句與連言句 *"Lady Gaga is a well-known public figure **and** Stefani Joanne Angelina Germanotta is a well-known public figure"* ($L \cdot S$) 真值完全相同（儘管 Lady Gaga 的本名就是 Stefani Germanotta，這在語句邏輯中仍可拆為兩個獨立斷言她們各自是知名公眾人物的連言句）。

#### (7) And how about "Lady Gaga and Stefani Joanne Angelina Germanotta have been lifelong best friends"?
- **標準解答**：這是一個**原子語句 (Atomic Sentence / 單句)**！因為此處的 *"and"* 帶有「**共同、一起、相互 (together / with each other)**」的關係意義，把她拆成兩句單句（「Lady Gaga 是一輩子的摯友」且「Stefani 是一輩子的摯友」）在語意上是改變原意甚至無意義的（此類關係句需進入 [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] 與 [[Ch11 等同與確定描述詞 (Identity and Definite Descriptions)]] 以二元關係述詞 $Fls$ 分析）。

---

## 第三部分：Ch. 3 真值計算、取代實例、真值表檢驗與證成（Ex 3-1 ~ Ex 3-13 全解）

### 1. Ex 3-1 & Ex 3-2：已知賦值與未知賦值計算真值（對應 `raw/Ex_Ch03_習題解答.docx`）

- **Ex 3-1**（假定 $V(A)=V(B)=\mathbf{T}$，且 $V(C)=V(D)=V(E)=\mathbf{F}$）：
  - **(7)** $\sim(A \cdot B) \equiv (\sim A \lor \sim B)$：
    - 左式 $\sim(\mathbf{T} \cdot \mathbf{T}) = \mathbf{F}$；右式 $(\mathbf{F} \lor \mathbf{F}) = \mathbf{F}$；故 $\mathbf{F} \equiv \mathbf{F} = \mathbf{T}$（此即狄摩根定理恆真式）。
  - **(9)** $[(A \cdot B) \cdot C] \lor [(A \cdot C) \lor (A \cdot D)]$：
    - 左選言支 $[(\mathbf{T}\cdot\mathbf{T})\cdot\mathbf{F}] = \mathbf{F}$；右選言支 $[(\mathbf{T}\cdot\mathbf{F}) \lor (\mathbf{T}\cdot\mathbf{F})] = \mathbf{F} \lor \mathbf{F} = \mathbf{F}$；故整句為 **$\mathbf{F}$**。
  - **(11)** $[(A \cdot B) \cdot (C \cdot D)] \supset E$：
    - 前件 $(\mathbf{T} \cdot \mathbf{F}) = \mathbf{F}$，後件 $E = \mathbf{F}$，故 $\mathbf{F} \supset \mathbf{F} = \mathbf{T}$。
  - **(15)** $[(E \supset \sim D) \cdot \sim A] \supset \{(\sim A \cdot \sim B) \cdot [(C \cdot D) \cdot E]\}$：
    - 因 $A=\mathbf{T}$，故 $\sim A = \mathbf{F}$，導致前件 $[(E \supset \sim D) \cdot \mathbf{F}] = \mathbf{F}$！**只要條件句前件為 F，不需算後件，整句條件句必為 $\mathbf{T}$**！

- **Ex 3-2**（假定 $V(A)=V(B)=\mathbf{T}, \ V(C)=V(D)=\mathbf{F}$，而 **$V(Q)=V(R)=\text{未知 (?)}$**）：
  - **(3)** $\sim C \supset (D \supset Q)$：
    - 雖然 $Q$ 的真值未知，但因為內層前件 $D = \mathbf{F}$，所以 $(D \supset Q)$ **無條件為 $\mathbf{T}$**！因此整句 $\mathbf{T} \supset \mathbf{T} = \mathbf{T}$！
  - **(5)** $\sim[R \equiv \sim R]$：
    - 雖然 $R$ 的真值未知，但 $V(R)$ 與 $V(\sim R)$ 的真值必然對立（一真一假），故內層雙條件句 $(R \equiv \sim R)$ **恆為 $\mathbf{F}$**，加上外層否定號後，整句必為 **$\mathbf{T}$**！
  - **(9)** $\sim(A \lor R) \equiv (\sim A \lor \sim R)$：
    - 左式因 $A=\mathbf{T}$，故 $(A \lor R) = \mathbf{T}$，左式 $\sim(A \lor R) = \mathbf{F}$；
    - 但右式為 $(\mathbf{F} \lor \sim R)$，其真值取決於 $\sim R$ 是 T 還是 F！因此整句真值為 **未知 (`?`)**。
  - **(11)** $(A \cdot C) \supset [(D \cdot Q) \supset (\sim A \cdot R)]$：
    - 因 $C = \mathbf{F}$，主前件 $(A \cdot C) = (\mathbf{T} \cdot \mathbf{F}) = \mathbf{F}$！前件為假，整句條件句直接為 **$\mathbf{T}$**！

---

### 2. Ex 3-3 & Ex 3-5：語句形式與取代實例（對應 `raw/Ex_Ch03_習題解答.docx` & 原文書 p.57–59）

- **Walk-Through 核心四步法（原文書 p.57–58，以 $\sim(A \lor B) \supset (C \cdot D)$ 為例）**：
  1. **原子形式 (Atomic Form)**：$p$（任何語句皆是 $p$ 的取代實例）。
  2. **基本形式 (Basic Form)**：$p \supset q$（只保留整句的**主要連接詞**！**除了原子形式 $p$ 之外，一個語句的所有其他正確形式，其主要連接詞都必須與基本形式完全相同**！這是快速排除錯誤選項的鐵律）。
  3. **中間形式 (Intermediate Forms)**：逐步揭露左支與右支的內部結構：$\sim p \supset q$、$p \supset (q \cdot r)$、$\sim p \supset (q \cdot r)$、$\sim(p \lor q) \supset r$。
  4. **展開形式 / 一對一邏輯形式 (Expanded / One-One Form)**：$\sim(p \lor q) \supset (r \cdot s)$。

- **Ex 3-3 標準解答**：
  1. 哪些**不是** $p \supset q$ 的取代實例？ $\implies$ **C. $A \lor (B \supset C)$**（因為 C 的主要連接詞是 $\lor$ 而非 $\supset$！其餘 A, B, D, E, F 的主要連接詞皆為 $\supset$）。
  2. 哪些**是** $p \supset q$ 的取代實例？ $\implies$ **B. $A \supset \sim B$** 與 **F. $(\sim A \lor \sim B) \supset C$**（A 的主要連詞是 $\sim$，C 是原子句，D, E 的主要連詞是 $\lor$）。
  3. 哪些**是** $\sim p$ 的取代實例？ $\implies$ **B. $\sim A$**、**C. $\sim\sim A$**、**F. $\sim(A \supset B)$**（這三句的主要連接詞皆為最外層的 $\sim$；而 D 的主要連詞是 $\lor$，E 的主要連詞是 $\supset$）。
  4. 哪些**不是** $\sim\sim p$ 的取代實例？ $\implies$ **A. $A$**（結構比形式簡單，不可！）、**B. $\sim(\sim A \supset B)$**（只有一個外層否定號）、**E. $\sim\sim A \supset \sim B$**（主要連詞為 $\supset$）、**F. $(A \lor B) \supset C$**。只有 **C. $\sim\sim(A \supset B)$** 與 **D. $\sim\sim\sim A$**（令 $p = \sim A$）才是 $\sim\sim p$ 的取代實例！
  5. $\sim A \supset (B \supset C)$ 是哪些形式的取代實例？ $\implies$ **A. $[p]$**、**C. $[p \supset q]$**、**D. $[\sim p \supset q]$**、**E. $[p \supset (q \supset r)]$**。

- **Ex 3-5 列出語句的所有語句形式（注意相同字母產生額外受限形式！）**：
  - **(1) $A \cdot \sim B$**：$p$, $p \cdot q$, $p \cdot \sim q$
  - **(5) $\sim(\sim R \lor S)$**：$p$, $\sim p$, $\sim(p \lor q)$, $\sim(\sim p \lor q)$
  - **(7) $\sim A \supset (B \supset A)$** *(注意 $A$ 出現兩次！)*：$p$, $p \supset q$, $\sim p \supset q$, $p \supset (q \supset r)$, $\sim p \supset (q \supset r)$, 以及一對一形式 **$\sim p \supset (q \supset p)$**！
  - **(9) $(A \equiv B) \supset C$**：$p$, $p \supset q$, $(p \equiv q) \supset r$
  - **(11) $\sim(B \cdot D) \lor (R \equiv D)$** *(注意 $D$ 出現兩次！)*：$p$, $p \lor q$, $\sim p \lor q$, $p \lor (q \equiv r)$, $\sim p \lor (q \equiv r)$, $\sim(p \cdot q) \lor r$, $\sim(p \cdot q) \lor (r \equiv s)$, 以及一對一形式 **$\sim(p \cdot q) \lor (r \equiv q)$**！

---

### 3. Ex 3-6 & Ex 3-7：恆真/矛盾/適真句判定與邏輯等值檢驗（對應 `raw/Ex_Ch03_習題解答.docx` & 原文書 p.63–67）

- **Ex 3-6 真值表分類**：
  - **(3) $A \supset (A \lor B)$**：一對一形式 $p \supset (p \lor q)$ 在 4 列真值表皆為 `T` $\implies$ **恆真句 (Tautology)**。
  - **(7) $(A \cdot B) \supset (\sim A \supset \sim B)$**：一對一形式 $(p \cdot q) \supset (\sim p \supset \sim q)$ 在 4 列皆為 `T` $\implies$ **恆真句 (Tautology)**。
  - **(9) $(A \supset B) \equiv (A \lor B)$**：一對一形式 $(p \supset q) \equiv (p \lor q)$ 的 4 列真值依序為 `T, T, F, F`（有 T 有 F） $\implies$ **適真句 (Contingent Sentence)**。

- **Ex 3-7 邏輯等值檢驗（原文書 p.67 勾選重點題：第 6, 12, 20 題）**：
  - **(6) $F \cdot \sim F$ 與 $F \equiv \sim F$**：
    - 兩者の一對一形式分別為 $p \cdot \sim p$ 與 $p \equiv \sim p$。在真值表每一列中，$p \cdot \sim p$ 恆為 **`F`**，$p \equiv \sim p$ 也恆為 **`F`**（**所有矛盾句彼此之間皆邏輯等值；所有恆真句彼此之間亦皆邏輯等值**！）$\implies$ **邏輯等值 (Logically Equivalent)**！
  - **(12) $A \lor B$ 與 $A \lor (B \supset B)$**：
    - 因 $(B \supset B)$ 為恆真句（恆為 `T`），故右式 $A \lor (B \supset B)$ 在所有列皆為 **`T`**（恆真句）；但左式 $A \lor B$ 在 $V(A)=F, V(B)=F$ 時為 **`F`**（適真句）$\implies$ **不邏輯等值 (Not Logically Equivalent)**！
  - **(20) $(H \cdot K) \lor (K \cdot L)$ 與 $(\sim H \cdot \sim K) \lor (\sim K \cdot \sim L)$**：
    - 當 $V(H)=V(K)=V(L)=\mathbf{T}$ 時，左式為 **$\mathbf{T}$**，右式為 **$\mathbf{F}$** $\implies$ **不邏輯等值**！

---

### 4. Ex 3-8、Ex 3-10 & Ex 3-11：簡短真值表法檢驗有效性與一致性（對應 `raw/Ex_Ch03_習題解答.docx` & 原文書 p.388）

#### (A) Ex 3-8 & Ex 3-10：簡短真值表檢驗論證有效性
- **Ex 3-8 (3)**：$1. \ (A \cdot B) \supset C \quad 2. \ A \ / \ \therefore B \supset C$
  - 令結論 $B \supset C = \mathbf{F} \implies V(B)=\mathbf{T}, V(C)=\mathbf{F}$。又令前提 2 $V(A)=\mathbf{T}$，則前提 1 $(A \cdot B) \supset C$ 變成 $(\mathbf{T} \cdot \mathbf{T}) \supset \mathbf{F} = \mathbf{F}$（矛盾！）$\implies$ **有效 (Valid)**（即輸出律 Exp）。
- **Ex 3-8 (7)**：$1. \ \sim(D \lor \sim K) \quad 2. \ H \supset D \ / \ \therefore H \supset K$
  - 令結論 $H \supset K = \mathbf{F} \implies V(H)=\mathbf{T}, V(K)=\mathbf{F}$。由前提 2 $H \supset D = \mathbf{T}$ 得 $V(D)=\mathbf{T}$；但代入前提 1 $\sim(D \lor \sim K)$ 得 $\sim(\mathbf{T} \lor \mathbf{T}) = \mathbf{F}$（矛盾！）$\implies$ **有效 (Valid)**。
- **Ex 3-8 (11)**：$1. \ F \supset G \quad 2. \ (G \cdot H) \lor K \ / \ \therefore F$
  - 令結論 $V(F) = \mathbf{F}$，則前提 1 $F \supset G = \mathbf{T}$；再令 $V(G)=V(H)=V(K)=\mathbf{T}$，前提 2 亦為 $\mathbf{T}$ $\implies$ **無效 (Invalid)**。
- **Ex 3-8 (17)**：$1. \ \sim(A \supset \sim B) \quad 2. \ C \supset A \ / \ \therefore C \supset D$
  - 令結論 $C \supset D = \mathbf{F} \implies V(C)=\mathbf{T}, V(D)=\mathbf{F}$。由前提 2 $C \supset A = \mathbf{T}$ 得 $V(A)=\mathbf{T}$；但注意前提 1 $\sim(A \supset \sim B)$（若原題為 $\sim(A \lor \sim B)$，當 $A=\mathbf{T}$ 時 $\sim(\mathbf{T} \lor \sim B) = \mathbf{F}$ 矛盾！）$\implies$ **有效 (Valid)**（此題正是**期中考第三大題第 (2) 題**的原型！）。
- **Ex 3-10 多變元長題無效反例賦值速查表（原文書 p.388 & 中文解答）**：
  - **(1)** $H \supset K, \sim H / \therefore \sim K$（否定前件謬誤）：當 $V(H)=\mathbf{F}, V(K)=\mathbf{T}$ 時前提皆真、結論假 $\implies$ **無效**。
  - **(11)** $P \supset Q, R \supset S, R \lor Q / \therefore P \lor S$（**期中考第三大題第 (1) 題原題！**）：當 **$V(P)=\mathbf{F}, V(Q)=\mathbf{T}, V(R)=\mathbf{F}, V(S)=\mathbf{F}$** 時前提皆真、結論假 $\implies$ **無效**。
  - **(13)** $A \supset (B \supset C), C \supset (D \supset E), A \supset B, E \supset A / \therefore D \supset E$：當 **$V(A)=\mathbf{F}, V(C)=\mathbf{F}, V(D)=\mathbf{T}, V(E)=\mathbf{F}$**（$B$ 任意）時前提皆真、結論假 $\implies$ **無效**。
  - **(15)** $(A \lor B) \supset C, D \supset (E \supset B), (E \supset A) \supset F, C \supset (B \lor F) / \therefore B \equiv C$：當 **$V(A)=\mathbf{F}, V(B)=\mathbf{F}, V(C)=\mathbf{T}, V(D)=\mathbf{F}, V(E)=\mathbf{T}, V(F)=\mathbf{T}$** 時無效。
  - **(19)** 含 8 個變元之大型論證：當 **$V(K)=V(L)=V(M)=V(S)=V(T)=\mathbf{T}, \ V(R)=\mathbf{F}$** 時前提皆真、結論 $\sim R$（或 $R$）為假 $\implies$ **無效**。

#### (B) Ex 3-11：簡短真值表檢驗語句集一致性（原文書 p.388 & 中文解答）
- **(1)** $\{B \supset A, \ C \supset B, \ \sim C \cdot A\}$：令 **$V(A)=\mathbf{T}, V(C)=\mathbf{F}, V(B)=\text{任意}$**，三句同時為真 $\implies$ **一致**。
- **(2)**（p.388 偶數題解答）：$V(F)=\mathbf{T}, V(G)=\mathbf{F}, V(H)=\mathbf{F}$ $\implies$ **一致**。
- **(4)**（p.388 偶數題解答）：$V(F)=\mathbf{F}, V(G)=\mathbf{T}, V(H)=\mathbf{F}$ $\implies$ **一致**。
- **(5)** $\{A \cdot \sim B, \ B \lor \sim C, \ \sim(C \cdot B)\}$：令 **$V(A)=\mathbf{T}, V(B)=\mathbf{F}, V(C)=\mathbf{F}$**，三句同時為真 $\implies$ **一致**。
- **(6)**（p.388 偶數題解答）：$V(A)=\mathbf{F}, V(B)=\mathbf{F}, V(C)=\mathbf{F}, V(D)=\mathbf{T}$ $\implies$ **一致**。
- **(7)** $\{\sim[(A \lor B) \supset (C \lor D)], \ C \supset \sim A, \ D \supset E\}$：令 **$V(A)=\mathbf{T}, V(B)=\mathbf{T}, V(C)=\mathbf{F}, V(D)=\mathbf{F}, V(E)=\mathbf{T}$**，三句同時為真 $\implies$ **一致**。
- **(8)**（p.388 偶數題解答）：$V(A)=\mathbf{T}, V(B)=\mathbf{T}, V(C)=\mathbf{F}, V(D)=\mathbf{T}, V(E)=\mathbf{T}, V(F)=\mathbf{F}$ $\implies$ **一致**。

---

### 5. Exercise 3-12（原文書 p.81 & p.388 勾選重點題：第 2, 4, 6 題）—— 真值表定義證成的高階反思！

#### 第 2 題：如何證成雙條件句 $p \equiv q$（tribar）的第 4 列（$p=F, q=F$ 時為 T）？
- **標準解答（原文書 p.388）**：
  - 考慮日常直覺明顯**無效**的論證：「Bob 愛 Mary 若且唯若 Mary 愛 Bob ($p \equiv q$)；Bob 不愛 Mary ($\sim p$)；$\therefore$ Mary 愛 Bob ($q$)」。
  - 為捕捉此論證形式 $p \equiv q, \sim p / \therefore q$ 的無效性，必須指派結論 $V(q) = \mathbf{F}$ 且前提 2 $V(\sim p) = \mathbf{T}$（即 **$V(p) = \mathbf{F}$**）。在此條件下（第 4 列 $p=F, q=F$），第一個前提 **$V(p \equiv q)$ 必須為 `T`**，才能構成前提皆真而結論為假的反例列！

#### ⭐ 第 4 題（黃色螢光筆重點題！）：給定論證形式 $p, q / \therefore p \ \# \ q$ 是「有效的 (Valid)」（且假設結論既非恆真句亦非矛盾句），我們能否據此決定神秘連詞 `$p \ \# \ q$` 真值表中的哪一列？為什麼？這對我們的真值表證成程序有何啟示？
- **標準解答（原文書 p.388 核心洞見）**：
  - **是的，可以決定第 1 列（當 $V(p)=T, V(q)=T$ 時，$V(p \ \# \ q)$ 必為 `T`），但若從「令結論 $V(p \ \# \ q) = \mathbf{F}$」反推，卻無法決定哪一列為 `F`**！
  - **原文書解答深度剖析**：如果我們嘗試指派結論 $V(p \ \# \ q) = \mathbf{F}$ 來找哪一列為 F，因為論證有效（不能前提皆真），我們只知道此時**「$V(p) = \mathbf{F}$ 或者 $V(q) = \mathbf{F}$（至少有一個前提為假）」**，但我們**沒有足夠的資訊斷定究竟是哪一列（第 2、3 還是 4 列）讓 $p \ \# \ q$ 為 F**！
  - **方法論啟示 (Lesson for our justificatory procedure)**：這揭示了僅靠「直覺有效的論證（且結論在最後）」來證成真值表列的**侷限性 (Limitation)**——單靠「若 $p$ 真且 $q$ 真則 $p \cdot q$ 真」這個有效論證，並不足以告訴我們當 $p \cdot q$ 為假時對應的是第 2、3、4 列中的哪一列；必須搭配**無效論證形式**（強制所有前提皆為 T 且結論為 F，唯一鎖定特定的一列）或把該連詞放在前提位置，才能精準鎖定每一列！

#### ⭐ 第 6 題（畢業魔王題 Graduation Exercise！）：已知論證形式 $p \ * \ \sim q, \ p \lor q / \therefore q$ 是「無效的 (Invalid)」，請決定神秘連詞 `$*$` 真值表中的一列！（小心變元陷阱！）
- **標準解答（原文書 p.388 經典陷阱解析）**：
  - **Step 1**：因為論證無效，必存在一組賦值使**所有前提為 `T` 且結論為 `F`**。
  - **Step 2**：為使結論 $q$ 為假，必須指派 **$V(q) = \mathbf{F}$**；再代入第二個前提 $p \lor q = \mathbf{T}$，因 $V(q)=\mathbf{F}$，強制決定 **$V(p) = \mathbf{T}$**！
  - **Step 3（90% 學生會踩中的致命陷阱！）**：
    - 許多人看到 $V(p)=\mathbf{T}, V(q)=\mathbf{F}$ 時 $V(p \ * \ \sim q) = \mathbf{T}$，就誤以為這決定了 `$*$` 真值表的「第 2 列（左 T 右 F）」為 T —— **大錯特錯**！
    - 請仔細看 `$*$` 右邊放的運算元不是 $q$，而是 **$\sim q$**！
    - 當 $V(q) = \mathbf{F}$ 時，**右邊運算元 $V(\sim q) = \mathbf{T}$**！同時左邊運算元 **$V(p) = \mathbf{T}$**！
    - 因此，這告訴我們的是：**當 `$*$` 的「左邊為 `T`」且「右邊（即 $\sim q$）也為 `T`」時，整個 $p \ * \ \sim q$ 為 `T`**！
    - **結論**：這決定的是神秘連詞 `$*$` 真值表的**第 1 列（左 `T`、右 `T` 時，結果為 `T`）**，而不是第 2 列！

---

### 6. Ex 3-13：賦值原則與一致性觀念問答（對應 `raw/Ex_Ch03_習題解答.docx`）
1. **賦值原則 (Principle of Valuation)**：賦值就是賦予原子語句真值，每次只能賦予一個原子語句真 (`T`) 或假 (`F`) 其中之一；在同一個論證中出現的同一個原子語句 $A$，在同一次賦值下必須保持一致（$V(A)=T$ 或 $V(A)=F$ 二者選一）。
3. **恆真語句形式的取代實例有可能不是恆真句嗎？** $\implies$ **否**。因為根據定義，恆真語句形式（Tautological Statement Form）的所有取代實例都必然是恆真句。（注意與期中考是非題第 7 題區分！）
5. **含有 $n$ 個語句變元的語句形式有幾列真值表？** $\implies 2^n$ 列（如 4 個變元有 $2^4 = 16$ 列）。
7. **一個「前提一致」的有效論證，其結論必然為真嗎？** $\implies$ **不一定（並不必然為真）**！
   - **在地化經典反例**：
     1. 清華大學在新竹。(T)
     2. 如果清華大學在新竹，則台大在屏東。(F)
     $/ \ \therefore$ 台大在屏東。(F)
   - 此有效論證（MP）的兩個前提是**一致的**（因為在邏輯上*有可能*清華在新竹且台大搬去屏東），但因為前提 2 在*事實上*為假，故結論在事實上為假。唯有**前提事實上都為真**的有效論證（即**健全論證 Sound Argument**），其結論才必然為真！
