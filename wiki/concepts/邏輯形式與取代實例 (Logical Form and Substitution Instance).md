---
title: "邏輯形式與取代實例 (Logical Form and Substitution Instance)"
category: concepts
chapters: ["Ch. 1", "Ch. 2", "Ch. 3", "Ch. 4"]
tags: [logic, concept, logical-form, substitution-instance, tautology, contradiction, contingent, equivalence]
updated: 2026-11-22
---

# 邏輯形式與取代實例 (Logical Form and Substitution Instance)

> **所屬章節**：[[Ch01 邏輯導論 (Introduction to Logic)]]、[[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]]、[[Ch03 真值表 (Truth Tables)]]、[[Ch04 自然演繹法證明 (Natural Deduction Proofs)]]
> **對應方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]、[[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]、[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]

演繹邏輯之所以被稱為「形式邏輯 (Formal Logic)」，是因為一個論證是否有效、一個語句是否為邏輯真理（恆真句），完全取決於它的**邏輯形式 (Logical Form)**，而非其具體經驗內容。本章節釐清「語句 vs. 語句形式」、「取代 (Substitution) vs. 置換 (Replacement)」以及「一對一邏輯形式」等核心概念。

---

## 1. 語句常元 (Constants) vs. 語句變元 (Variables)

| 比較項目 | 語句常元 (Sentence Constants: $A, B, C \dots$) | 語句變元 (Sentence Variables: $p, q, r \dots$) |
| :--- | :--- | :--- |
| **指稱對象** | 代表某個特定的具體陳述句（如 $A =$「今天新竹有刮風」） | 代表可以填入任何完構語句的**空位 (Placeholders)** |
| **真假值狀態** | **具有確定的真假值**（非 T 即 F，只對應真值表中的某一列） | **本身沒有真假值** |
| **構成的式子** | 構成具體的**語句 (Sentence)**，如 $(A \cdot B) \supset A$ | 構成抽象的**語句形式 (Statement Form)**，如 $(p \cdot q) \supset p$ |
| **與真值表關係** | 語句的真值取決於常元的實際賦值與其所對應的語句形式 | **語句形式才具有完整的 $2^n$ 列真值表** |

---

## 2. 取代實例 (Substitution Instance) 與形式層級譜系

- **取代實例 (Substitution Instance) 的嚴格定義**：
  - 將一個語句形式（或論證形式）中的語句變元 $p, q, r \dots$ 以任意完構語句（wff，可以是原子語句或極度複雜的複合語句）代入；**唯一且絕對的限制是：同一個變元在該形式中所有出現的位置，必須以完全相同的語句進行一致取代 (Uniform Substitution)**！
  - *注意*：**不同的變元**（如 $p$ 與 $q$）**允許**代入相同的語句（例如 $A \supset A$ 是 $p \supset q$ 的一個合法取代實例，也是 $p \supset p$ 的取代實例）；但**相同的變元**（如 $p \supset p$ 中的兩個 $p$）**絕對不允許**代入不同的語句（$A \supset B$ 不是 $p \supset p$ 的取代實例）。

- **一個語句的形式層級譜系（以語句 $(A \cdot B) \supset \sim(A \lor B)$ 為例）**：
  一個具體語句可以同時是許多不同語句形式的取代實例，從最粗糙到最精細依序為：
  1. **原子形式 (Atomic Form)**：$p$（**任何語句**都是單一變元 $p$ 的取代實例！）。
  2. **基本形式 (Basic Form)**：$p \supset q$（直接由該語句的**主要連接詞 Main Connective** 所決定的形式）。
  3. **中間形式 (Intermediate Forms)**：如 $(p \cdot q) \supset r$、$p \supset \sim q$、$(p \cdot q) \supset \sim(r \lor s)$ 等。
  4. **一對一邏輯形式 / 展開形式 (One-One / Expanded Logical Form)**：**$(p \cdot q) \supset \sim(p \lor q)$**
     - **定義**：將原語句中每一個原子語句皆以變元取代，且滿足**(1) 相同的原子語句代入相同的變元，(2) 相異的原子語句代入相異的變元**。
     - **重要性（原文書 p.63 核心定理）**：一個語句是否為恆真句、矛盾句或適真句，**完全由它的「一對一邏輯形式」之真值表決定**！
       - 若一個語句具有某個**非一對一的恆真形式**（例如 $\{[(A \cdot B) \supset (C \lor D)] \cdot (A \cdot B)\} \supset (C \lor D)$ 是恆真形式 $[(p \supset q) \cdot p] \supset q$ 的取代實例），那麼它的一對一邏輯形式也**必然是恆真形式**！
       - 但反過來不一定成立：一個一對一形式為恆真的語句（如 $[(A \supset B) \cdot A] \supset B$），可能除了它自己的一對一形式之外，沒有其他更簡單的恆真形式（它的其他較簡單形式如 $p \supset q$ 或 $p$ 都是適真形式！這正是**期中考是非題第 7 題**的考點：恆真句的某個語句形式 $p$ 之取代實例 $A$ 未必是恆真句！詳見 [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]]）。
       - 若一個語句的一對一邏輯形式是**適真形式 (Contingent Form)**，則它**絕對不可能**是任何恆真形式或矛盾形式的取代實例！
- **結構複雜度鐵律与基本形式檢驗法（原文書 p.57–58 Walk-Through）**：
  - **結構複雜度鐵律**：一個語句的邏輯結構可以比它的形式**更複雜**（例如 $\sim\sim A$ 是 $p$、$\sim p$ 與 $\sim\sim p$ 三種形式的取代實例），但**絕對不能比它的形式更簡單**（例如原子語句 $A$ 只具有形式 $p$，**不是** $\sim\sim p$ 的取代實例！）。
  - **主要連接詞快速檢驗法**：**除了原子形式 $p$ 之外，一個複合語句的所有正確語句形式，其「主要連接詞 (Main Connective)」都必須與該語句的「基本形式 (Basic Form)」完全一致**！如果某個候選形式的主要連接詞與原句不同（例如原句是 $\sim(A \lor B) \supset (C \cdot D)$，候選形式卻是 $\sim p$ 或 $p \lor q$），它 100% 是錯的！

---

## 3. 關鍵辨析：取代 (Substitution) vs. 置換 (Replacement)

這是 [[Ch03 真值表 (Truth Tables)]] 與 [[Ch04 自然演繹法證明 (Natural Deduction Proofs)]] 中最容易混淆的兩個後設概念：

| 比較維度 | 取代 (Substitution) | 邏輯等值置換 (Replacement) |
| :--- | :--- | :--- |
| **操作對象** | 針對**語句形式中的變元 ($p, q, r$)** 進行代入 | 針對**具體語句中的子句 ($A, B \dots$)** 進行等值替換 |
| **一致性要求** | **必須全式一致取代 (Must be Uniform)**：式中所有的 $p$ 都必須換成同一個語句 | **不必全式一致置換 (Need NOT be Uniform)**：可只把句中第一個 $A$ 換成 $\sim\sim A$ (由 DN)，第二個 $A$ 保持不變 |
| **適用規則** | 所有 18 條推論規則（8 條蘊含 + 10 條等值）在套用到具體證明列時，都是找該規則形式的**取代實例** | 僅 **10 條雙向等值規則 (`::`)** 與 **QN** 允許對一列中的**部分子句**進行置換 |

---

## 4. 三大語句分類與兩大語句間關係

依據語句之**一對一邏輯形式**的真值表結果：

1. **恆真句 / 套套邏輯 (Tautology, $\models \phi$)**：
   - 真值表**每一列皆為 `T`**（例如排中律 $A \lor \sim A$、不矛盾律 $\sim(A \cdot \sim A)$）。
   - **重要性質**：恆真句的任何取代實例也必然是恆真句！
2. **矛盾句 (Contradiction)**：
   - 真值表**每一列皆為 `F`**（例如 $A \cdot \sim A$）。
   - **重要性質**：矛盾句的任何取代實例也必然是矛盾句！
3. **適真句 / 偶真句 (Contingent Sentence)**：
   - 真值表**至少有一列為 `T` 且至少有一列為 `F`**（例如 $A$、$A \supset B$）。
   - *注意*：適真句形式（如 $p \lor q$）的取代實例**不一定**是適真句（若將 $p$ 代入 $A$、$q$ 代入 $\sim A$，所得的 $A \lor \sim A$ 就變成了恆真句！）。
4. **邏輯等值 (Logical Equivalence, $X :: Y$)**：
   - 兩語句 $X$ 與 $Y$ 邏輯等值 $\iff$ 雙條件句 **$X \equiv Y$ 是恆真句**（在所有真值列中 $X$ 與 $Y$ 同真同假）。
5. **邏輯蘊涵 (Logical Implication)**：
   - 語句 $X$ 邏輯蘊涵 $Y$ $\iff$ 條件句 **$X \supset Y$ 是恆真句**（不可能 $X$ 為 T 而 $Y$ 為 F，即論證 $X / \therefore Y$ 為有效論證）。

---

## 5. 相關概念與方法連結

- **前導概念**：[[有效性與健全性 (Validity and Soundness)]]、[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]
- **語意檢驗方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]
- **語法推論應用**：[[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]、[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]
- **實戰演練**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]
