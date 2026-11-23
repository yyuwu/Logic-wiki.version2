---
title: "真值表與簡短真值表法 (Truth Table and Short Truth Table Method)"
category: methods
chapters: ["Ch. 3", "Ch. 8"]
tags: [logic, method, truth-table, short-truth-table, decision-procedure, invalidity, consistency]
updated: 2026-11-22
---

# 真值表與簡短真值表法 (Truth Table and Short Truth Table Method)

> **所屬章節**：[[Ch03 真值表 (Truth Tables)]]、[[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]]
> **理論基礎**：[[有效性與健全性 (Validity and Soundness)]]、[[一致性與反例集 (Consistency and Counterexample Set)]]、[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]
> **對應練習**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]

**真值表法 (Truth Table Method)** 是語句邏輯（SL）的**機械決定程序 (Decision Procedure)**：不需要靠靈感或猜測，只要按照固定演算法在有限步驟內執行，就能 100% 判定任何 SL 語句或論證的語意性質。而**簡短真值表法 (Short Truth Table Method)** 則是透過「逆向賦值」直接搜尋反例列，解決 $2^n$ 列數爆炸的高效方法。

---

## 1. 完整真值表法 (Full Truth Table Method) 操作 SOP

### Step 1：計算列數並配置基準欄
- 找出式子或論證中所有相異的原子語句（共 $n$ 個），總列數為 **$2^n$ 列**。
- 基準欄配置規律：
  - 最右邊第 $n$ 個原子語句：`T, F, T, F...`（每 1 列交替一次）
  - 右起第 2 個原子語句：`T, T, F, F...`（每 2 列交替一次）
  - 最左邊第 1 個原子語句：前 $2^{n-1}$ 列為 `T`，後 $2^{n-1}$ 列為 `F`。

### Step 2：由內而外逐層計算複合子句真值
- 依據括弧層級，從最內層的原子語句與單一否定號 $\sim$ 開始向外計算，最後算出每個前提與結論之**主要連接詞 (Main Connective)** 下方的真值欄。

### Step 3：判讀結果

| 檢驗目標 | 完整真值表判讀標準 |
| :--- | :--- |
| **單一語句分類** | - 每一列皆為 `T` $\implies$ **恆真句 (Tautology)**<br>- 每一列皆為 `F` $\implies$ **矛盾句 (Contradiction)**<br>- 至少有一列 `T` 且至少有一列 `F` $\implies$ **適真句 (Contingent)** |
| **兩語句是否邏輯等值** | 比較兩語句在每一列的真值：若**所有列真值完全相同**（即 $X \equiv Y$ 恆真） $\implies$ **邏輯等值 (`::`)** |
| **語句集合是否一致** | 檢查是否存在**至少一列**使集合中所有語句**同時為 `T`**：<br>- 存在此列 $\implies$ **一致 (Consistent)**<br>- 不存在此列 $\implies$ **不一致 (Inconsistent)** |
| **論證是否有效** | 檢查是否存在任何一列使**所有前提皆為 `T` 而結論為 `F`**（**反例列 Counterexample Row**）：<br>- 存在至少一列反例列 $\implies$ **無效 (Invalid)**<br>- 不存在任何反例列 $\implies$ **有效 (Valid)** |

---

## 2. 簡短真值表法 (Short Truth Table Method) —— 逆向賦值演算法

當一個論證含有 5 個原子語句（$2^5 = 32$ 列）或 6 個原子語句（$2^6 = 64$ 列）時，畫完整真值表極不切實際。事實上，要證明論證**無效**，我們只需要找出**一列**反例列即可！

### (1) 用簡短真值表檢驗「論證有效性 / 證明無效性」
- **核心目標**：嘗試構造出一列使**所有前提皆為 `T`，且結論為 `F`** 的原子語句賦值。
- **操作步驟**：
  1. 在結論的主要連接詞下方直接寫上 **`F`**，在所有前提的主要連接詞下方全部寫上 **`T`**。
  2. 從「只有唯一一種真值組合能使該式為 F 或 T」的句子（強制賦值列）開始逆推：
     - 若結論是條件句 $P \supset Q$ 且為 **`F`** $\implies$ **強制決定**前件 $P = \mathbf{T}$ 且後件 $Q = \mathbf{F}$！
     - 若結論是選言句 $P \lor Q$ 且為 **`F`** $\implies$ **強制決定** $P = \mathbf{F}$ 且 $Q = \mathbf{F}$！
     - 若某前提是連言句 $P \cdot Q$ 且為 **`T`** $\implies$ **強制決定** $P = \mathbf{T}$ 且 $Q = \mathbf{T}$！
  3. 將已確定的原子語句真值（如 $A=T, B=F$）代入其他所有前提中，利用連鎖反應繼續推算其餘原子語句的真值。
  4. **最終判定**：
     - **成功找到一組無矛盾的賦值**：使所有前提皆為 `T`、結論為 `F`（若有某個原子語句直到最後都可 T 可 F，任選其一填入即可）$\implies$ **證明該論證無效 (Invalid)**！並寫出該組反例賦值。
     - **被迫產生矛盾**：若在所有可能的分支情況下，都必然導致某個原子語句既必須是 `T` 又必須是 `F` $\implies$ 代表反例列不存在，**證明該論證有效 (Valid)**！

#### 💡 講義經典實戰範例（簡短真值表證無效）
> **檢驗論證**：
> 1. $A \supset (B \lor C)$
> 2. $B \supset (D \cdot E)$
> 3. $\sim D$ / $\therefore \sim(A \cdot \sim C)$
>
> **逆向推算步驟**：
> 1. 令結論 $\sim(A \cdot \sim C) = \mathbf{F} \implies (A \cdot \sim C) = \mathbf{T} \implies$ 強制決定 **$A = \mathbf{T}$** 且 $\sim C = \mathbf{T}$（即 **$C = \mathbf{F}$**）。
> 2. 令前提 3 $\sim D = \mathbf{T} \implies$ 強制決定 **$D = \mathbf{F}$**。
> 3. 將 $D = \mathbf{F}$ 代入前提 2 $B \supset (D \cdot E) = \mathbf{T}$：因為 $D=F$，後件 $(D \cdot E) = \mathbf{F}$（無論 $E$ 是 T 或 F）；為使前提 2 為 T，前件強制決定 **$B = \mathbf{F}$**！
> 4. 將已得出的 **$A = \mathbf{T}, B = \mathbf{F}, C = \mathbf{F}$** 代入前提 1 $A \supset (B \lor C)$：
>    - 前件 $A = \mathbf{T}$，後件 $(B \lor C) = (\mathbf{F} \lor \mathbf{F}) = \mathbf{F}$，因此前提 1 變成 $\mathbf{T} \supset \mathbf{F} = \mathbf{F}$！與「所有前提必須為 T」產生**必然矛盾**！
> 5. **結論**：因為所有步驟皆為唯一強制決定且必然導致矛盾，不存在任何反例列，故**此論證有效 (Valid)**！

### (2) 用簡短真值表檢驗「語句集合一致性」
- **操作步驟**：直接令集合中的**每一個語句皆為 `T`**，逆向推算是否存在一組一致的原子語句賦值。若找得到一組賦值使所有語句皆為 `T`，即證明**一致 (Consistent)**；若必然矛盾，則證明**不一致 (Inconsistent)**。

---

## 3. 真值表定義的反推證成法 (Justification of Truth Tables)

在 [[Ch03 真值表 (Truth Tables)]] 3-10 節（及習題 3-12）中，我們利用已知有效或無效的論證形式，來反推某個連詞真值表每一列應該填 `T` 還是 `F`：
- **核心原理**：
  - 若已知一個論證形式是**無效的 (Invalid)**，則它的真值表中**必定至少有一列是「前提皆為 T 且結論為 F」**！
  - 若已知一個論證形式是**有效的 (Valid)**，則在真值表中**凡是前提皆為 T 的那一列，結論必定為 T**（或者若結論為 F，則前提不可能全部為 T）！

---

## 4. 相關概念與方法連結

- **在述詞邏輯中的升級應用**：將有限模型展開式與簡短真值表法結合，證明 PL 論證無效 $\implies$ [[述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)]]
- **語法推論的替代方案**：當論證有效時，與其畫龐大真值表，不如用自然演繹法直接推導 $\implies$ [[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]、[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]
- **實戰演練**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]
