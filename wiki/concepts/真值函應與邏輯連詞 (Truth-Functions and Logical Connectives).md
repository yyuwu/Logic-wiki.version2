---
title: "真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)"
category: concepts
chapters: ["Ch. 2", "Ch. 3"]
tags: [logic, concept, truth-function, connectives, material-conditional, negation, conjunction, disjunction, biconditional]
updated: 2026-11-22
---

# 真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)

> **所屬章節**：[[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]]、[[Ch03 真值表 (Truth Tables)]]
> **對應方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]
> **對應練習**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]

語句邏輯（Sentential Logic, SL）之所以能擁有真值表這套 100% 機械化的決定程序，關鍵在於它將自然語言中複雜多變的連接詞，提煉為嚴格服從**真值函應原則 (Principle of Truth-Functionality)** 的五個基本邏輯連詞：$\sim, \cdot, \lor, \supset, \equiv$。

---

## 1. 真值函應原則 vs. 非真值函應連接詞

- **真值函應原則 (Principle of Truth-Functionality)**：
  - 一個複合語句的真假值，**完全且唯一地由其構成成分語句（Component Sentences）的真假值所決定**，與成分語句之間的內容意義、因果關聯或時間順序無關。
- **如何檢驗一個自然語言連接詞是否為真值函應？**
  - **檢驗法**：固定成分語句 $p$ 與 $q$ 的真假值（例如皆為真 `T`），觀察複合句是否可能在某些情況下為 `T`，在另一些情況下卻為 `F`。若是，則該連接詞**不是**真值函應連接詞！
  - **常見非真值函應連接詞 (Non-Truth-Functional Connectives)**：
    1. **「因為 ($p$ because $q$)」**：即使 $p=$「林肯遇刺身亡」(T)、$q=$「花椰菜是蔬菜」(T)，「林肯遇刺身亡因為花椰菜是蔬菜」卻是 **F**！但「地濕了因為剛才下雨」在兩成分皆 T 時卻是 **T**。故「因為」非真值函應。
    2. **「在……之前 ($p$ before $q$)」**：就算 $p, q$ 皆為真，還取決於兩事件發生的時間先後順序。
    3. **認識論與模態算子（「眾所周知 It is well known that $p$」、「小明相信 $p$」、「必然 $\Box p$」）**：即使 $p$ 為真（例如某個冷門的數學真理），「眾所周知 $p$」仍可能為假。

---

## 2. 五大真值函應邏輯連詞聯合真值表

| $p$ | $q$ | 否定<br>$\sim p$ | 連言 (And)<br>$p \cdot q$ | 選言 (Inclusive Or)<br>$p \lor q$ | 實質條件句 (If...then)<br>$p \supset q$ | 實質雙條件句 (Iff)<br>$p \equiv q$ |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **T** | **T** | F | **T** | **T** | **T** | **T** |
| **T** | **F** | F | F | **T** | **F** *(唯一為假之列)* | F |
| **F** | **T** | **T** | F | **T** | **T** *(前件為假恆真)* | F |
| **F** | **F** | **T** | F | F | **T** *(前件為假恆真)* | **T** |

---

## 3. 各連詞的哲學細節與自然語言翻譯陷阱

### (1) 連言 (Conjunction, $p \cdot q$)
- **同義轉折詞**：自然語言中的「而且 (and)」、「但是 (but)」、「然而 (however)」、「雖然……但是 (although)」、「儘管 (nevertheless)」，在真值條件上全部都是在斷言前後兩句**同時為真**，故一律符號化為 **`$p \cdot q$`**（轉折語氣屬於語用修辭色彩，不影響真假值）。
- **不可譯為連言 `$\cdot$` 的兩種「和 (and)」**：
  1. **相互關係 / 集體述詞**：「亞當和夏娃是戀人 (Art and Betsy are lovers)」不能拆成「亞當是戀人 $\cdot$ 夏娃是戀人」（必須在 [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] 中用二元關係述詞 $Lab$ 表達）。
  2. **帶有時間先後順序的 and**：「他穿上降落傘並跳出飛機」與「他跳出飛機並穿上降落傘」在日常語言不等價，但在 SL 中 $P \cdot J \equiv J \cdot P$（交換律）。

### (2) 選言 (Disjunction, $p \lor q$)
- **相容選言 (Inclusive Or)** vs. **排斥選言 (Exclusive Or)**：
  - 邏輯學預設的 $\lor$ 是**相容選言**（至少有一為真，**兩者皆真時亦為真**，如「應徵者須會寫 Python 或 C++」）。
  - 若語境明確要求**排斥選言**（「兩者擇一且不可兼得」，如「套餐附紅茶或咖啡擇一」），則須符號化為：
    $$(p \lor q) \cdot \sim(p \cdot q) \quad \text{或} \quad \sim(p \equiv q)$$

### (3) 實質條件句 (Material Conditional, $p \supset q$) 的哲學證成與系統性理由
- **對應原始補充講義**：`raw/Supp_Ch02_Ch03_關於實質條件句的定義補充.docx`、`raw/Supp_Ch03_Exercise_3-12_Justification_of_Truth_Tables_p81.pdf`
- **為什麼當前件 $p$ 為假（第 3、4 列）或前後件皆真（第 1 列）時，$p \supset q$ 必須一律定義為真 (`T`)？**
  1. **內容不相干 vs. 內容相干條件句的觀察**：
     - 初看**內容上不相干**的句子（如 `(a) 若新竹是一座城市(T)，則沒有最大的偶數(T)`、`(b) 若有最大的偶數(F)，則新竹是一座城市(T)`、`(c) 若有最大的偶數(F)，則新竹是一種植物(F)`），日常直覺很難決定它們的真值。
     - 但考慮**內容上相干**的數學語句：
       - `(d) 如果沒有最大的偶數(T)，則沒有最大的數(T)。`
       - `(e) 如果 5 是最大的偶數(F)，則 7 不是偶數(T)。`
       - `(f) 如果 5 是最大的偶數(F)，則 6 不是偶數(F)。`
     - 幾乎沒有人會否定 `(d), (e), (f)` 這三句話在邏輯上是**真的 (`T`)**！這顯示在 `(T,T)`, `(F,T)`, `(F,F)` 三種真值條件下，條件句確實有時候必須為真。
  2. **支持一律定義為真 (`T, F, T, T`) 的三大系統性理由（補充講義核心論證）**：
     - **理由一：一致性（Consistency with Truth-Functionality & Substitution）—— 最重要的理由！**
       - **真值函應原則**與 Ch. 3-2 的**「取代觀念 (Substitution)」**（參見 Richmond H. Thomason, *Symbolic Logic: An Introduction*, 1970, Ch. V 歸納取代定義：用 $A$ 取代 $B$ 中出現的 $P$ 所得的結果 $S_A^P B$ 完全依賴於對子句的取代結果）是緊密一致的。唯有採取真值函應原則，複合句的真值才能完全由較簡單成分子句的真值唯一決定。
     - **理由二：理論簡單性（Simplicity）**
       - 若否認真值函應原則（讓 $p \supset q$ 在 $p=F, q=T$ 時有時為真、有時為假），就必須在語意理論中引入真值以外的額外決定因素，使語意理論大幅複雜化。
     - **理由三：不影響論證的有效性與無效性（Preserving Validity and Invalidity）**
       - 定義當 $p$ 假或 $q$ 真時 $p \supset q$ 為真，**絕對不會使有效論證變成無效，也不會使無效論證變成有效**！
       - 反之，若 $p \supset q$ 的四列真值表不是定義為 `T, F, T, T`，將立即導致以下四個邏輯災難：
         1. **【第 1 列 ($p=T, q=T$) 若改為 `F`】**：則直覺明顯**無效**的論證形式 `$p \supset q, p / \therefore \sim q$`（例：若 Bob 愛 Sally 則 Sally 愛 Bob；Bob 愛 Sally；$\therefore$ Sally 不愛 Bob）將失去唯一的反例列（$p=T, q=T$ 時 $\sim q=F$），而被荒謬地判定為「有效」！
         2. **【第 2 列 ($p=T, q=F$) 若改為 `T`】**：則直接違背**肯定前件律 (MP: `$p \supset q, p / \therefore q$`)**，使這個最基本且明顯有效的論證在 $p=T, q=F$ 時出現「前提皆真而結論為假」，變成「無效」！
         3. **【第 3 列 ($p=F, q=T$) 若改為 `F`】**：則直覺明顯**無效**的**否定前件謬誤 (`$p \supset q, \sim p / \therefore \sim q$`)** 在 $p=F, q=T$（此時 $\sim p=T, \sim q=F$）時前提 $p \supset q$ 變為 F，無法構成反例列，導致否定前件謬誤被判定為「有效」！
         4. **【第 4 列 ($p=F, q=F$) 若改為 `F`】**：則直覺明顯**無效**的論證形式 **`$p \supset q, \sim p / \therefore q$`**（或 `$p \supset q, \sim q / \therefore p$`，例：若 Bob 愛 Sally 則 Sally 愛 Bob；Bob 不愛 Sally [或 Sally 不愛 Bob]；$\therefore$ Sally 愛 Bob [或 Bob 愛 Sally]）在 $p=F, q=F$ 時無法構成前提皆真而結論為假的反例列，也會變成「有效」！
  3. **反事實條件句 (Counterfactual Conditionals) 的語用例外（期中考是非題第 1 題）**：
     - 日常語言如「如果太陽從西邊升起來，我就請你吃飯」，語用意義是「我絕不會請你吃飯」，屬於非真值函應的反事實條件句，**不可**恰當地翻譯為實質條件句（詳見 [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]]）。

---

## 4. 高頻易錯句型符號化速查表

| 自然語言句型 | 英文對應 | 標準符號化 | 等值替代式 | 記憶與邏輯解析 |
| :--- | :--- | :---: | :---: | :--- |
| **若 A 則 B / 只要 A 就 B** | If A then B / B if A | **$A \supset B$** | $\sim A \lor B$ | `if` 後面接的是**充分條件（放前件）** |
| **只有 B 才 A / A 僅當 B** | **A only if B** | **$A \supset B$** | $\sim B \supset \sim A$ | `only if` 後面接的是**必要條件（放後件）**！若沒 B 就一定沒 A |
| **A 若且唯若 B** | A if and only if B (iff) | **$A \equiv B$** | $(A \supset B) \cdot (B \supset A)$ | $A$ 與 $B$ 互為充分必要條件 |
| **A 除非 B / 除非 B 否則 A** | **A unless B** | **$\sim B \supset A$** | **$A \lor B$** | 「若非 B 則 A」；等值於「A 或 B 至少有一成立」 |
| **不會既 A 又 B** | **Not both A and B** | **$\sim(A \cdot B)$** | $\sim A \lor \sim B$ | 否定號在括弧外（最多只有一個成立） |
| **既不 A 也不 B** | **Neither A nor B** | **$\sim A \cdot \sim B$** | $\sim(A \lor B)$ | 兩者皆不成立（比 Not both 更強！） |

---

## 5. 相關概念與方法連結

- **下一個概念**：常元與變元、取代實例與恆真句分類 $\implies$ [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]
- **語意檢驗方法**：用真值表計算複雜複合句與論證 $\implies$ [[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]
- **述詞邏輯中的 Only / Unless**：比較 SL 的 `A only if B` ($A \supset B$) 與 PL 的 `Only A are B` ($(x)(Bx \supset Ax)$) $\implies$ [[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]]
- **實戰演練**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]
