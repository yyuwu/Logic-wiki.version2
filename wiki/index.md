---
title: "哲學邏輯學 LLM Wiki 知識庫總索引 (Master Index)"
category: index
updated: 2026-11-22
---

# 哲學邏輯學 LLM Wiki 知識庫總索引 (Master Index)

> 本索引遵循 Karpathy LLM Wiki 架構設計，收錄本知識庫所有已編譯之章節總覽、核心概念、形式推論方法、習題解析與跨章節綜合比較頁面，並標註每一頁與教學簡報（`slides/index.html`）之明確對應模組。

---

## 0. 系統規範、原始文獻與日誌 (System Schema, Raw Sources & Logs)

- **[[AGENT]]**（位於根目錄 `AGENT.md`） — 定義本知識庫之三層式架構、本體論目錄規範、8 節點工作流圖（Workflow Graph）、4 維度自我驗證迴圈（Lint Loop）與易錯節點反思。
- **[[log]]**（`wiki/log.md`） — 知識庫的時序演進日誌，詳載 `init`、`ingest`、`lint`（含自動檢測與修復紀錄）與 `slides` 對齊驗證紀錄。
- **原始檔案層 (`raw/` — 共 44 個唯讀原始檔案，全數封板完成)**：
  - **9 份中文邏輯講義**：`Ch_01_導論.docx`、`Ch_02_語句邏輯裡的符號化.docx`、`Ch_03_真值表法.docx`、`Ch_04_證明.docx`、`Ch_05_條件證法與間接證法.docx`、`Ch_07_述詞邏輯_述詞邏輯的符號化.docx`、`Ch_08_述詞邏輯_語意學.docx`、`Ch_09_述詞邏輯的證明.docx`、`Ch_11_等同與確定描述詞.docx`
  - **9 份中文章節習題解答、1 份期中考解答與 10 份歷屆邏輯小考解答**：`Ex_Ch01_習題解答.docx`、`Ex_Ch02_習題解答.docx`、`Ex_Ch03_習題解答.docx`、`Ex_Ch04_習題解答.docx`、`Ex_Ch05_習題解答.docx`、`Ex_Ch07_習題解答.docx`、`Ex_Ch08_習題解答.docx`、`Ex_Ch09_習題解答.docx`、`Ex_Ch10_關係述詞習題解答.docx`、`Exam_Ch01_to_Ch05_邏輯115上期中考解答.doc`、`Quiz1_Ch01_邏輯小考1解答_20240919.docx`、`Quiz2_Ch02_邏輯小考2解答_20240926.docx`、`Quiz3_Ch03_邏輯小考3解答_20241003.docx`、`Quiz3_Ch01_to_Ch03_邏輯小考3解答_20231024_選擇題.docx`、`Quiz4_Ch04_邏輯小考4解答_20241024.docx`、`Quiz5_Ch04_邏輯小考5解答_20231107.docx`、`Quiz5_Ch07_邏輯小考5解答_20241205_述詞符號化.docx`、`Quiz6_Ch05_邏輯小考6解答_20231114.docx`、`Quiz8_Ch08_邏輯小考8解答_20231212_展開式與無效反例.docx`、`Quiz9_Ch09_邏輯小考9解答_20231219_述詞邏輯證明.docx`
  - **14 份專題補充講義與原文書重點頁**：`Supp_Ch01_Plan_of_Book_Ex1-3_p14.pdf`、`Supp_Ch02_Symbolizing_Examples_Ex2-6_p44-45.pdf`、`Supp_Ch02_Ch03_關於實質條件句的定義補充.docx`、`Supp_Ch03_WalkThrough_Substitution_Instances_Ex3-3_p57-59.pdf`、`Supp_Ch03_WalkThrough_Construct_Truth_Table_p63-65.pdf`、`Supp_Ch03_Logical_Equivalence_Ex3-7_p67.pdf`、`Supp_Ch03_Exercise_3-12_Justification_of_Truth_Tables_p81.pdf`、`Supp_Ch03_Exercise_3-11_3-12_Answers_p388.pdf`、`Supp_Ch04_Ch05_Valid_Forms_for_Sentential_Logic.pdf`、`Supp_Ch07_補充一_部份否定與全部否定.docx`、`Supp_Ch07_補充二_部分否定全部否定和雙重否定的翻譯.docx`、`Supp_Ch07_Ch09_Ex10-6_複雜關係述詞符號化與定理Q17補充.docx`、`Supp_Ch09_Ch10_附錄二_林正弘述詞邏輯55條定理與證明.docx`、`Supp_Ch09_Ch11_Rules_for_Predicate_Logic.pdf`
  - **原文書完整 PDF**：Alan Hausman, Frank Boardman, Howard Kahane, *Logic and Philosophy: A Modern Introduction* (13th Ed., Hackett, 2021).

---

## 1. 章節總覽 (`wiki/chapters/` — 共 9 頁)

| Wiki 頁面連結 | 對應講義章節 | 一句話核心摘要 | 對應 HTML 簡報投影片 |
| :--- | :---: | :--- | :---: |
| [[Ch01 邏輯導論 (Introduction to Logic)]] | Ch. 1 | 定義陳述句、論證 vs. 因果解釋、演繹有效性 vs. 歸納強度、真值與有效性 8 種組合、健全性、一致性與反例集定理 | Slide 3 |
| [[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]] | Ch. 2 | 建立語句邏輯 (SL) 語法與語意、真值函應原則、五大連詞 ($\sim, \cdot, \lor, \supset, \equiv$)、括弧範圍、使用與提及、Only if 與 Unless 符號化 | Slide 4 |
| [[Ch03 真值表 (Truth Tables)]] | Ch. 3 | 語句形式與一致取代實例、恆真/矛盾/適真句、邏輯等值與蘊涵、完整真值表與簡短真值表逆向賦值法、真值表定義證成 | Slide 5 |
| [[Ch04 自然演繹法證明 (Natural Deduction Proofs)]] | Ch. 4 | 建立語句邏輯自然演繹系統：8 條單向蘊含規則（整列限制）與 10 條雙向等值置換規則（可用於子句）及解題策略 | Slide 6 |
| [[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]] | Ch. 5 | 引入自行假設前提 (AP) 與封閉線機制之條件證法 (CP) 與間接證法 (IP)、無前提定理證明、後設邏輯之系統健全性與完備性 | Slide 7 |
| [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]] | Ch. 7 | 引入個體常元/變元、一元與多元述詞、全稱 $(x)$ 與存在 $(\exists x)$ 量詞、A/E/I/O 定言命題與范恩圖、存在意涵與現代對當方陣、有限論域展開式 | Slide 8 |
| [[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]] | Ch. 8 (含 Ch.12) | 定義述詞邏輯的 5 步解釋、證明無效性的三種反例法（日常事實、正整數算術、有限模型展開式+簡短真值表）與邱奇不可判定性定理 | Slide 9 |
| [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]] | Ch. 9 (含 Ch.11) | 準變元哲學意義、四條單向量詞規則 (UI, EI, UG, EG)、必考五項主要限制（含先 EI 後 UI、EI 下毒與 AP 解毒）與雙向量詞否定規則 (QN) | Slide 10 |
| [[Ch11 等同與確定描述詞 (Identity and Definite Descriptions)]] | Ch. 11 (原文 Ch.13) | 區分屬性斷言與等同 (`=`)、等同規則 (ID) 與反身性 (IR)、數量詞（至少/至多/恰好 $n$ 個）、羅素確定描述詞理論與二元關係性質 | Slide 11 |

---

## 2. 核心概念 (`wiki/concepts/` — 共 8 頁)

| Wiki 頁面連結 | 所屬領域 | 一句話核心摘要 | 對應 HTML 簡報投影片 |
| :--- | :---: | :--- | :---: |
| [[論證與解釋 (Argument vs Explanation)]] | 邏輯基礎 | 剖析語句 vs. 陳述句、前提/結論指示詞、「理由證成 (論證)」與「因果說明 (解釋)」的判準，以及發現脈絡 vs. 證成脈絡 | Slide 3 |
| [[有效性與健全性 (Validity and Soundness)]] | 邏輯基礎 | 對比演繹有效與歸納強論證，詳列「前提真假 × 結論真假 × 有效/無效」8 種組合矩陣，並定義健全論證 (Sound = Valid + True Premises) | Slide 3 |
| [[一致性與反例集 (Consistency and Counterexample Set)]] | 邏輯基礎 / 跨章節 | 定義語句集合的一致與不一致，確立「論證有效 $\iff$ 反例集 $\{P_1 \dots P_n, \sim C\}$ 不一致 $\iff$ 相應條件句恆真」三位一體定理 | Slide 3, 5, 7 |
| [[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]] | 語句邏輯 | 闡述二值原則與真值函應原則，檢驗非真值函應連詞，剖析實質條件句 $p \supset q$ 前件為假恆真的證成，以及 Only if / Unless / Neither 翻譯表 | Slide 4 |
| [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]] | 語句邏輯 | 區分常元與變元、一致取代 (Substitution) vs. 等值置換 (Replacement)、一對一邏輯形式，以及恆真句、矛盾句與適真句 | Slide 5 |
| [[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]] | 後設邏輯 | 釐清使用 vs. 提及、對象語言 vs. 後設語言，對比語意有效 ($\models$) 與語法可證 ($\vdash$)，闡明系統健全性與完備性定理 | Slide 7, 12 |
| [[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]] | 述詞邏輯 | 剖析自由與拘束變元、A/E/I/O 命題與范恩圖、為何現代邏輯因無存在意涵而使傳統對當方陣只剩對角線矛盾關係，以及橋倒定理 Q17/Q18 | Slide 8 |
| [[等同與確定描述詞理論 (Identity and Theory of Descriptions)]] | 等同邏輯 | 剖析萊布尼茲定律、數量詞（至少/至多/恰好）構造邏輯、羅素確定描述詞「存在性+唯一性+屬性」三合一公式與內外部否定範圍歧義 | Slide 11 |

---

## 3. 形式推論與檢驗方法 (`wiki/methods/` — 共 6 頁)

| Wiki 頁面連結 | 方法類型 | 一句話核心摘要 | 對應 HTML 簡報投影片 |
| :--- | :---: | :--- | :---: |
| [[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]] | 語意檢驗 (SL) | 完整真值表 $2^n$ 列演算法、簡短真值表「令結論 F、前提皆 T」逆向賦值搜尋反例演算法，以及真值表定義反推證成法 | Slide 5 |
| [[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]] | 語法推導 (SL) | 詳解 MP, MT, DS, HS, Simp, Conj, Add, CD 八條規則圖式、單向與整列限制（Whole-Line Restriction）及 Add 弱化引進新字母技巧 | Slide 6 |
| [[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]] | 語法推導 (SL) | 詳解 DN, DeM, Comm, Assoc, Dist, Contra, Impl, Exp, Taut, Equiv 十條雙向子句置換規則，以及用 Dist + Simp 割離多餘字母的高階技巧 | Slide 6 |
| [[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]] | 語法子證明 (SL/PL) | 詳解自行假設前提 (AP) 與封閉線（Scope Line）管理、單層与巢狀 CP、IP 歸謬法、爆炸原理 4 步推導，以及無前提定理證明策略 | Slide 7 |
| [[述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)]] | 語意檢驗 (PL) | 構造 5 步完整解釋，詳解證明 PL 無效性的三種方法：日常經驗事實反例法、正整數算術反例法、有限模型論域 $D=\{a,b\}$ 展開式+簡短真值表法 | Slide 9 |
| [[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]] | 語法推導 (PL/ID) | 詳解 UI, EI, UG, EG 四條規則與準變元、必考五項主要限制（含「先 EI 後 UI」、EI 同列沾染下毒、CP 消去 AP 解毒）、雙向 QN 與等同 ID/IR 規則 | Slide 10, 11 |

---

## 4. 習題解析與錯誤診斷 (`wiki/exercises/` — 共 5 頁)

| Wiki 頁面連結 | 對應章節範圍 | 收錄代表性題型摘要 | 對應 HTML 簡報投影片 |
| :--- | :---: | :--- | :---: |
| [[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]] | Ch. 1 ~ Ch. 3 | 論證 vs. 因果解釋、**Ex 1-3 真值與有效性（十八尖山與貢丸米粉例）**、**Ex 2-7 & Ex 2-10 符號化與 Lady Gaga 原子/複合句辨析**、**Ex 3-1 ~ Ex 3-13 全解（含取代實例 Walk-Through、Ex 3-7 邏輯等值、Ex 3-10/3-11 簡短真值表、Ex 3-12 真值表證成第 2, 4, 6 題）** | Slide 3, 4, 5, 13 |
| [[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]] | Ch. 4 ~ Ch. 5 | **Ex 4-1 ~ Ex 4-14 全解（含正向/逆向 Dist 提公因式、Ex 4-13 一題三解、Ex 4-14 語句邏輯表達完備性與選言範式 DNF）**、**Ex 5-1 ~ Ex 5-8 全解（含用 IP 與不用 IP 雙軌對照、無前提定理、Ex 5-7 證明前提不一致、Ex 5-8 新規則評估）** | Slide 6, 7, 13 |
| [[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]] | Ch. 7, Ch. 10, Ch. 11 | **Ex 7-3 ~ Ex 7-11 全解**（含大象保育部分否定 vs. 全部否定辨析、「大多數 Most」限制）、**邏輯小考 5 (2024.12.05)**、**Ch.10 關係述詞 Ex 10-1 ~ Ex 10-6 全解**（雙量詞展開式、時間/地點顯性量化、選民迎合 Q17 與欠牛頓錢）、數量詞與羅素確定描述詞 | 百科詞條 & 焦點簡報 08 |
| [[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]] | Ch. 8, Ch. 9, Ch. 10, Ch. 11 | **Ex 8-1 ~ Ex 8-3 全解**、**邏輯小考 8 (2023.12.12)**、**Ex 10-8 二元/三元關係自然數反例與展開式反例**、**Ex 9-1 ~ Ex 9-5 全解（含 Ex 9-2 抓錯與 Ex 9-4 QN 診斷）**、**邏輯小考 9 (2023.12.19)**、**Ex 10-10 & Ex 10-11 多重量詞關係證明**、ID/IR 等同證明 | 百科詞條 & 焦點簡報 04, 07 |
| [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]] | Ch. 1 ~ Ch. 5 綜合 | **邏輯 (115 上) 期中考 100% 全卷詳解 + 7 份歷屆邏輯小考 (1)~(6) 全解**：含小考 1 是非題、小考 2 符號化、小考 3 簡短真值表與 10 題觀念單選題、小考 4&5 18 條規則證明、**小考 6 定理一題三解與一題四解** | 百科詞條 & 焦點簡報 05, 08 |

---

## 5. 跨章節綜合比較與演進 (`wiki/syntheses/` — 共 4 頁)

| Wiki 頁面連結 | 綜合比較主題 | 一句話核心摘要 | 對應前端展示位置 |
| :--- | :---: | :--- | :---: |
| [[語句邏輯與述詞邏輯的演進與比較 (Evolution from Sentential to Predicate and Identity Logic)]] | 三階段系統演進 | 橫向比較 SL $\rightarrow$ PL $\rightarrow$ PL+Identity 在分析顆粒度、真值函應性、語意解釋數、可判定性（$2^n$ 真值表 vs. 邱奇不可判定性）與結構同構性上的演進 | 焦點簡報 01 & 百科詞條 |
| [[語法學與語意學的雙軌對稱架構 (Syntactic vs Semantic Dual Architecture in Logic)]] | 語意 $\models$ vs. 語法 $\vdash$ | 繪製貫穿全書的「語意學左軌（賦值/解釋/恆真句/反例）」與「語法學右軌（取代/自然演繹/定理/CP-IP）」雙軌對稱架構圖及 7 大概念映射表 | 焦點簡報 02 & 百科詞條 |
| [[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]] | 三大防呆限制家族 | 統整並比較 Ch.4「單向規則整列限制」、Ch.5「CP/IP 封閉線作用域限制」與 Ch.9「量詞 EI/UG 五項主要限制」如何共同捍衛系統健全性，附準變元汙染與解毒狀態機 | 焦點簡報 03, 04 & 百科詞條 |
| [[述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)]] | 述詞邏輯 55 條定理 (Q1~Q55) | 完整收錄並分類證明林正弘《邏輯》附錄二之 55 條述詞邏輯定理與課本 Ex 10-12（量詞分配律 Q1~Q10、量詞進出括弧與橋倒定理 Q11~Q22、飲酒者定理 Q24、多重量詞交換順序 Q34~Q55） | 百科詞條 & 焦點簡報 01, 04 |
