---
title: "後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)"
category: concepts
chapters: ["Ch. 2", "Ch. 5", "Ch. 8"]
tags: [logic, concept, metalogic, soundness, completeness, theorem, tautology, object-language, metalanguage]
updated: 2026-11-22
---

# 後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)

> **所屬章節**：[[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]]、[[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]]、[[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]]
> **對應綜合頁**：[[語法學與語意學的雙軌對稱架構 (Syntactic vs Semantic Dual Architecture in Logic)]]

當我們不是直接「使用」邏輯符號來推導某個具體論證，而是站高一層，把整個邏輯系統本身當作研究對象，探討這套符號系統的性質（例如：「每一個用推論規則能證出來的定理，在真值表上都一定是恆真句嗎？」），我們所進行的研究就稱為**後設邏輯 (Metalogic)**。

---

## 1. 語言層次區分：使用 vs. 提及、對象語言 vs. 後設語言

### (1) 使用 (Use) vs. 提及 (Mention)（Ch. 2-8）
- **使用 (Use)**：直接用一個字詞作為工具，去指稱世界上的事物。
  - 例：`台北是台灣的首都。`（此處「台北」指稱那座城市）。
- **提及 (Mention)**：加上**引號 (`'...'`)**，把該字詞或符號本身當作談論的對象。
  - 例：`'台北' 由兩個中文字組成。`（此處談論的是「台北」這個符號字串本身，而不是那座城市）。
- **在邏輯中的重要性**：當我們討論語法規則（如「若 $\phi$ 與 $\psi$ 是完構式，則 '$(\phi \supset \psi)$' 也是完構式」）時，我們是在**提及**這些符號並規定其組合方式。

### (2) 對象語言 (Object Language) vs. 後設語言 (Metalanguage)
- **對象語言 (Object Language)**：我們正在建構與研究的**形式邏輯語言本身**（如語句邏輯 SL 中的常元 $A, B$、連詞 $\sim, \cdot, \lor, \supset, \equiv$ 與括弧；或述詞邏輯 PL 中的 $Fx, (x), (\exists x), =$）。
- **後設語言 (Metalanguage)**：我們用來**定義、解釋、討論對象語言**的高階語言（包含我們使用的繁體中文、英文，以及代表「任意對象語言完構句」的後設變元 $p, q, r$ 或 $u, w$，還有真值符號 `T, F`、語意蘊涵符號 $\models$、語法可證符號 $\vdash$ 與等值符號 `::`）。
  - *注意*：`T` 與 `F`、$\models$ 與 $\vdash$ 屬於**後設語言**，絕對不會出現在對象語言的完構式（如 $A \supset B$）內部！

---

## 2. 語意學 ($\models$) 與語法學 ($\vdash$) 的後設概念對照

在形式邏輯系統中，所有核心概念都呈現嚴格的「語意學（看真假值 / 解釋）」與「語法學（看符號推導規則）」雙軌對稱：

| 邏輯維度 | 語意學概念 (Semantics: Truth & Valuation) | 語法學概念 (Syntax: Proof & Derivation) |
| :--- | :--- | :--- |
| **核心操作工具** | 真值表賦值 $V$ / 模型論域解釋 $I$ | 自然演繹法推論規則（18 條 + CP/IP + 4 量詞 + QN + ID/IR） |
| **邏輯真理** | **恆真句 (Tautology / Logical Truth)**：$\models \phi$<br>（在所有可能賦值或解釋下皆為真 `T`） | **定理 (Theorem)**：$\vdash \phi$<br>（可在**零前提 / 無未消去假設**下由 CP 或 IP 證明出來） |
| **有效推論** | **語意有效 (Semantic Validity / Entailment)**：$\Gamma \models C$<br>（所有使前提集 $\Gamma$ 皆為 `T` 的賦值/解釋，結論 $C$ 必為 `T`） | **語法可證 (Syntactic Derivability)**：$\Gamma \vdash C$<br>（可從前提集 $\Gamma$ 透過有限步推論規則推導出結論 $C$） |
| **一致性** | **語意一致 / 可滿足 (Semantic Consistency / Satisfiability)**<br>（存在至少一組賦值/解釋使 $\Gamma$ 中所有語句同時為 `T`） | **語法一致 (Syntactic Consistency)**<br>（無法從 $\Gamma$ 透過推論規則推導出顯性矛盾句 $q \cdot \sim q$） |

---

## 3. 邏輯系統的兩大黃金後設性質：健全性與完備性

當我們設計了一套語法推論規則（如 Ch.4~Ch.5 的 18 條規則 + CP/IP），我們怎麼知道這套規則既「不會亂證出錯誤的東西」，又「足夠強大到不會漏掉任何有效的推論」？這正是**系統健全性**與**系統完備性**要回答的問題：

### (1) 系統健全性 (System Soundness)：語法可證 $\implies$ 語意有效
$$\text{If } \Gamma \vdash C, \text{ then } \Gamma \models C \qquad (\text{特別地：If } \vdash \phi, \text{ then } \models \phi)$$
- **白話定義**：**每一個能用自然演繹規則證明出來的定理，在真值表上必然都是恆真句**；每一個能從前提證明出結論的論證，在語意上必然都是有效論證。
- **直覺意義**：我們的推論規則是**安全可靠的 (Truth-Preserving)**，絕對不會「無中生有」把無效論證證成有效，或把非恆真句證成定理。
- **如何證明系統健全？**
  - 利用數學歸納法：先用真值表驗證每一條基本推論規則（8 條蘊含 + 10 條等值 + CP/IP）都是保真的（只要前提為 T，推得的下一列必為 T）；因此由有限步保真規則串聯起來的任何證明，也必然保真！
- ⚠️ **切勿混淆「個別論證的健全性」與「邏輯系統的健全性」**：
  - [[有效性與健全性 (Validity and Soundness)]]（Ch.1）談的是**單一論證**：「論證有效 + 前提在經驗事實上為真」。
  - 本節（Ch.5-7）談的是**整個邏輯系統**：「凡是系統語法可證的 ($\vdash$)，在語意上必然有效 ($\models$)」。

### (2) 系統完備性 (System Completeness)：語意有效 $\implies$ 語法可證
$$\text{If } \Gamma \models C, \text{ then } \Gamma \vdash C \qquad (\text{特別地：If } \models \phi, \text{ then } \vdash \phi)$$
- **白話定義**：**每一個真值表上的恆真句，都必然可以在零前提下用我們的推論規則證明為定理**；每一個語意上有效的論證，都一定找得到一條自然演繹證明路徑。
- **直覺意義**：我們的推論規則系統**足夠強大且完整**，沒有任何一條邏輯真理是真值表算得出為恆真、但推論規則卻證不出來的！
- **為什麼必須加入 CP 與 IP 才能達到完備性？**
  - 若只有 [[Ch04 自然演繹法證明 (Natural Deduction Proofs)]] 的 18 條規則，每一步推論都至少需要 1 到 3 個既有前提，因此在「零前提」下根本無法跨出第一步（連最簡單的恆真句 $\vdash A \supset A$ 或 $\vdash A \lor \sim A$ 都證不出來）！
  - 此外，即使是帶前提的有效論證如 $A \supset B / \therefore A \supset (A \cdot B)$，若不用 CP 或 IP（或極為迂迴的 Add + Dist 技巧），僅靠直覺的 18 條規則極難或無法推導。加入 **CP**（或 **IP**）後，語句邏輯（SL）與一階述詞邏輯（PL，由哥德爾 Kurt Gödel 於 1929 年證明其完備性定理）才真正成為**既健全又完備**的形式系統！

---

## 4. 語句邏輯的「表達完備性 / 功能完備性」(Expressive / Functional Completeness) 與選言範式 (DNF)

> **對應原始檔案**：`raw/Ex_Ch04_習題解答.docx`（Ex 4-14 第 5, 7, 9 題詳解）

除了推論規則的「演繹完備性（$\models \phi \implies \vdash \phi$）」之外，後設邏輯還關心另一個重要問題：**我們的邏輯連接詞集合（如 $\{\sim, \cdot, \lor, \supset, \equiv\}$）是否足夠表達所有可能的真值函應關係？** 這稱為**表達完備性 (Expressive Completeness)**。

1. **$n$ 個語句變元共有多少種可能的真值表？**
   - 含有 $n$ 個語句變元的語句形式，其真值表共有 **$2^n$ 列**。
   - 由於每一列的輸出真值都有 `T` 或 `F` 兩種可能，因此 $n$ 個變元總共可以定義出 **$2^{(2^n)}$ 種不同的真值函應（真值表）**！
   - 例如：當 $n = 2$（兩個變元 $p, q$）時，共有 $2^2 = 4$ 列，可構成 **$2^4 = 16$ 種不同的真值表**（我們熟悉的 $p \cdot q, \ p \lor q, \ p \supset q, \ p \equiv q$ 只是這 16 種裡面的 4 種）。
2. **選言範式 (Disjunctive Normal Form, DNF) 證明 $\{\sim, \cdot, \lor\}$ 具表達完備性**：
   - 任何一張含有 $n$ 個變元的真值表 $X$，都可以只用 **`$\sim$`, `$\cdot$`, `$\lor$`** 三個連詞構造出對應的完構式：
     - **Case A（$X$ 至少有一列為 `T`）**：把真值表中每一列使 $X$ 為 **`T`** 的賦值寫成一個「基本連言式」（若該列變元為 `T` 就寫變元本身 $p$，若為 `F` 就寫其否定 $\sim p$），再用選言號 **`$\lor$`** 把所有為 `T` 之列的基本連言式連起來，所得式子即為 $X$ 的**選言範式 (DNF)**！
       - 例：若 $X$ 在 $(T,T)$ 與 $(F,T)$ 為 `T`，其餘為 `F`，則 $X$ 的 DNF 為 **$(p \cdot q) \lor (\sim p \cdot q)$**。
     - **Case B（$X$ 所有列皆為 `F`，即矛盾句）**：直接用 **$p \cdot \sim p$** 表示。
3. **極簡表達完備連詞集 $\{\sim, \lor\}$（或 $\{\sim, \cdot\}$、$\{\sim, \supset\}$）**：
   - 由於 $p \cdot q \ :: \ \sim(\sim p \lor \sim q)$（DeM），$p \supset q \ :: \ \sim p \lor q$（Impl），$p \equiv q \ :: \ \sim(\sim p \lor \sim q) \lor \sim(p \lor q)$，因此**僅靠否定號 `$\sim$` 與選言號 `$\lor$` 兩個連詞，就足以表達語句邏輯中所有 $2^{(2^n)}$ 種可能的真值函應**！（詳見 [[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]] Ex 4-14）。
4. **推論規則系統的「經濟性 vs. 實用性」權衡（Ex 4-14 第 5 題）**：
   - **公設法系統 (Axiomatic System)**（如歐幾里得《幾何原本》或羅素《數學原理》）：公設與規則極少，但證明極度違反日常直覺。
   - **引進與消去規則系統 (Int-Elim System，課本 p.146，共 11 條規則)**：比 Kahane 系統更具備**理論簡單性與經濟性**，適合用來做後設邏輯證明，但日常推導步驟較冗長。
   - **Kahane 自然演繹系統（本課程採用：18 條規則 + CP/IP = 20 條規則）**：在保持健全性與完備性的前提下，兼顧了**實用性上的優越性**（證明簡短且貼近人類日常推論）；反之，若把無限多個有效論證形式全部列為推論規則，系統將喪失經濟性與實用性。

---

## 5. 相關概念與方法連結

- **雙軌對稱全貌**：[[語法學與語意學的雙軌對稱架構 (Syntactic vs Semantic Dual Architecture in Logic)]]
- **定理證明實戰**：[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]、[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]、[[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]]
- **可判定性 vs. 完備性**：一階述詞邏輯雖然具備**健全性與完備性**，但卻具有**邱奇不可判定性 (Undecidability)** $\implies$ [[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]]、[[語句邏輯與述詞邏輯的演進與比較 (Evolution from Sentential to Predicate and Identity Logic)]]
