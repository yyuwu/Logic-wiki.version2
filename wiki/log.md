---
title: "LLM Wiki 操作與驗證日誌 (Chronological Operation & Lint Log)"
category: log
updated: 2026-11-22
---

# LLM Wiki 操作與驗證日誌 (Chronological Operation & Lint Log)

> 本檔案採用只追加（Append-Only）之時序格式（`## [YYYY-MM-DD] <operation> | <title>`），完整記錄本知識庫的架構初始化、批次文獻攝取（Ingest）、四維度健康檢查與自動修復迴圈（4-Dimensional Lint Loop），以及教學簡報（HTML Slides）的對齊驗證結果。

---

## [2026-11-22] init | 初始化哲學邏輯學 LLM Wiki 知識庫架構與 AGENT.md 規範

- **執行節點**：Node 0 (Source Inventory & Schema Initialization)
- **完成項目**：
  1. 與使用者確認知識庫領域為「哲學的邏輯學（Philosophical Logic）」，確定以 **9 份繁體中文章節講義為主、Hausman 等人原文書第 13 版 PDF 為輔**。
  2. 撰寫核心規範檔 [[AGENT]]（`AGENT.md`），明確定義：
     - **三層式架構 + 教學展示層**：`raw/`（唯讀原始講義）、`wiki/`（LLM 維護之 Markdown 知識庫）、`AGENT.md`（Schema 規範）、`slides/index.html`（互動式教學簡報）。
     - **五大本體論目錄**：`wiki/chapters/`、`wiki/concepts/`、`wiki/methods/`、`wiki/exercises/`、`wiki/syntheses/`。
     - **8 節點工作流圖 (Workflow Graph)** 與 **4 維度自我驗證迴圈 (Self-Verifying Lint Loop)**。
     - **四大易錯節點反思與提前防範機制 (Pre-Check)**。
  3. 建立所有目錄結構並初始化 [[index]]（`wiki/index.md`）。

---

## [2026-11-22] ingest | 批次攝取 9 章中文邏輯講義與原文書並建構 30 篇知識圖譜頁面

- **執行節點**：Node 1 (Deep Parsing) $\rightarrow$ Node 2 (Ontological Categorization) $\rightarrow$ Node 3 (Relational Graph Construction)
- **原始檔案歸檔 (`raw/`)**：
  - `Ch_01_導論.docx`、`Ch_02_語句邏輯裡的符號化.docx`、`Ch_03_真值表法.docx`、`Ch_04_證明.docx`、`Ch_05_條件證法與間接證法.docx`、`Ch_07_述詞邏輯_述詞邏輯的符號化.docx`、`Ch_08_述詞邏輯_語意學.docx`、`Ch_09_述詞邏輯的證明.docx`、`Ch_11_等同與確定描述詞.docx`
  - `Hausman_Boardman_Kahane_Logic_and_Philosophy_13th_Ed.pdf`
- **新建與更新之 Wiki 頁面（共 30 篇核心知識頁 + 2 篇索引日誌頁 = 32 篇）**：
  1. **章節總覽 (`wiki/chapters/`，9 篇)**：
     - [[Ch01 邏輯導論 (Introduction to Logic)]]
     - [[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]]
     - [[Ch03 真值表 (Truth Tables)]]
     - [[Ch04 自然演繹法證明 (Natural Deduction Proofs)]]
     - [[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]]
     - [[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]]
     - [[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]]
     - [[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]]
     - [[Ch11 等同與確定描述詞 (Identity and Definite Descriptions)]]
  2. **核心概念 (`wiki/concepts/`，8 篇)**：
     - [[論證與解釋 (Argument vs Explanation)]]
     - [[有效性與健全性 (Validity and Soundness)]]
     - [[一致性與反例集 (Consistency and Counterexample Set)]]
     - [[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]
     - [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]
     - [[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]
     - [[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]]
     - [[等同與確定描述詞理論 (Identity and Theory of Descriptions)]]
  3. **推論與檢驗方法 (`wiki/methods/`，6 篇)**：
     - [[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]
     - [[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]
     - [[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]
     - [[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]
     - [[述詞邏輯解釋與無效性反例法 (Predicate Logic Interpretations and Invalidity Methods)]]
     - [[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]
  4. **習題解析與錯誤診斷 (`wiki/exercises/`，4 篇)**：
     - [[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]
     - [[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]
     - [[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]]
     - [[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]
  5. **跨章節綜合比較 (`wiki/syntheses/`，3 篇)**：
     - [[語句邏輯與述詞邏輯的演進與比較 (Evolution from Sentential to Predicate and Identity Logic)]]
     - [[語法學與語意學的雙軌對稱架構 (Syntactic vs Semantic Dual Architecture in Logic)]]
     - [[邏輯推論中的三大核心限制與防呆機制比較 (Comparison of Core Restrictions in Formal Proofs)]]

---

## [2026-11-22] lint | 執行 4 維度健康檢查迴圈 (Node 4 $\rightleftarrows$ Node 4b) 實際檢測與修復紀錄

- **執行節點**：Node 4 (4-Dimensional Lint Check) $\rightarrow$ Node 4b (Auto-Fix Loop) $\rightarrow$ Node 4 (Re-Verification Pass)
- **檢查工具**：PowerShell 自動化正規表達式連結解析與雙向圖譜掃描腳本。
- **第一輪檢查 (Pass 1) 發現之問題與自動修復 (Node 4b)**：
  1. **【維度一：斷連與孤島頁檢查 (Broken Links & Orphans)】**
     - *初檢發現*：掃描全部 32 個檔案中的 Wikilinks 時，發現 `log.md` 初始模板說明文字中有一處未跳脫的範例字串，被正規表達式判定為指向不存在頁面的斷連（Broken Link = 1）。
     - *Node 4b 修復*：將 `log.md` 中的格式說明改為敘述文字，並補齊所有 30 篇知識頁面的真實雙向 Wikilinks。
  2. **【維度二：符號與定義一致性檢查 (Notation & Definition Consistency)】**
     - *初檢發現*：在 [[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]] 題型 5-2（皮爾士定律無前提證明第 8 列）的文字區塊中，有一處條件號誤打為純文字 `supset` 而非統一符號 `⊃`。
     - *Node 4b 修復*：已精確替換為 `[(A ⊃ B) ⊃ A] ⊃ A`，確保全庫符號 100% 遵循 `~`, `·`, `∨`, `⊃`, `≡`, `(x)`, `(∃x)` 標準。
  3. **【維度三：概念—方法—習題雙向對齊檢查 (Concept-Method-Exercise Alignment)】**
     - *檢驗結果*：4 篇習題解析頁之 YAML 與標頭皆完整連結至對應之 `chapters`、`concepts` 與 `methods`；同時 8 篇概念頁與 6 篇方法頁底部皆設有「實戰演練」反向連結指回對應習題頁，雙向對齊率 100%。
- **第二輪複檢 (Pass 2) 最終指標**：
  - **總檔案數**：32 篇 Markdown 檔案（含 `AGENT.md`, `wiki/index.md`, `wiki/log.md` 與 29 篇分類知識頁/習題頁/綜合頁）。
  - **斷連數 (Broken Wikilinks)**：**0**。
  - **孤島頁數 (Orphan Content Pages)**：**0**（每篇核心知識頁面皆擁有 **6 至 21 條**有效反向連結 Inbound Links，其中 [[Ch03 真值表 (Truth Tables)]] 擁有最高的 21 條反向連結，[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]] 擁有 19 條反向連結）。

---

## [2026-11-22] slides | 生成互動式教學簡報 (`slides/index.html`) 並完成 Node 6 雙向溯源驗證

- **執行節點**：Node 5 (HTML Slide Generation) $\rightarrow$ Node 6 (Wiki-to-Slide Alignment Check) $\rightarrow$ Node 7 (Final Logging)
- **簡報教學結構（共 8 大模組、14 張互動式投影片）**：
  - **Slide 1 (Module 0)**：Karpathy LLM Wiki 三層架構與 8 節點自我驗證迴圈 (Loop / Graph) 圖解。
  - **Slide 2 (Module 0)**：實際執行 Lint 檢查紀錄表與四大易錯節點反思（Pre-Check 機制）。
  - **Slide 3 (Module 1)**：Ch.1 邏輯導論——論證 vs. 因果解釋、有效性 8 種真值組合禁區、健全性與反例集定理。
  - **Slide 4 (Module 2)**：Ch.2 語句邏輯符號化——真值函應原則、五大連詞真值表、Only if / Unless / Neither 翻譯鐵律。
  - **Slide 5 (Module 2)**：Ch.3 真值表與簡短真值表逆向賦值法實戰演練。
  - **Slide 6 (Module 3)**：Ch.4 自然演繹法——8 條單向蘊含規則（整列限制）vs. 10 條雙向等值置換規則（Dist+Simp 割離多餘字母）。
  - **Slide 7 (Module 3)**：Ch.5 條件證法 (CP)、間接證法 (IP)、皮爾士定律無前提定理證明與後設邏輯（健全性 vs. 完備性）。
  - **Slide 8 (Module 4)**：Ch.7 述詞邏輯符號化——A/E/I/O 定言命題、存在意涵與現代對當方陣崩解、橋倒問題 (Q17 vs. Q18)。
  - **Slide 9 (Module 4)**：Ch.8 述詞邏輯語意學——證明無效性的三大反例法（日常、正整數算術、有限模型展開式）與邱奇不可判定性定理。
  - **Slide 10 (Module 5)**：Ch.9 述詞邏輯證明——四條量詞規則 (UI/EI/UG/EG)、必考五項主要限制（先 EI 後 UI、EI 同列沾染下毒、CP 消去 AP 解毒）與量詞否定 (QN)。
  - **Slide 11 (Module 5)**：Ch.11 (13) 等同關係 (`=`)、ID/IR 規則、數量詞（至少/至多/恰好）與羅素確定描述詞理論（內外部否定歧義）。
  - **Slide 12 (Module 6)**：跨章節全景綜整——三階段邏輯系統演進、語意 ($\models$) vs. 語法 ($\vdash$) 雙軌對稱架構、三大防呆限制家族。
  - **Slide 13 (Module 6)**：互動式考題演練與證明錯誤診斷室（點擊按鈕即時切換顯示/隱藏解答）。
  - **Slide 14 (Module 7)**：Wiki 知識庫（32 篇檔案）與教學簡報（14 張投影片）100% 對應溯源總表（點擊標籤可直接開啟對應 `.md` 檔案）。
- **Node 6 驗證結果**：100% 通過（0 缺漏頁面，每張投影片頂部皆鑲嵌 `.wiki-trace-bar` 對應連結）。

---

## [2026-11-23] ingest | 第二批增量導入：12 份章節習題解答、實質條件句補充、原文書重點頁與期中考全卷解答

- **執行節點**：Node 0 (Pre-Check) $\rightarrow$ Node 1 (Raw Extraction) $\rightarrow$ Node 2 (Entity Update) $\rightarrow$ Node 3 (Relational Graph Linking)
- **依檔名線索與內容判定之章節關聯與歸檔 (`raw/` 新增 12 個唯讀原始檔，累計 22 個原始檔)**：
  1. `Ex_Ch01_習題解答.docx`（Exercise 1-3 第 1, 3, 5, 7, 9, 11 題，含清大十八尖山與新竹貢丸米粉在地化例題） $\implies$ 關聯 **Ch. 1**（[[Ch01 邏輯導論 (Introduction to Logic)]]、[[有效性與健全性 (Validity and Soundness)]]）。
  2. `Ex_Ch02_習題解答.docx`（Exercise 2-7 第 1~29 奇數題符號化、Exercise 2-10 第 1, 3, 5, 7 題真值函應與 Lady Gaga 原子/複合句辨析） $\implies$ 關聯 **Ch. 2**（[[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]]、[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]）。
  3. `Supp_Ch02_Ch03_關於實質條件句的定義補充.docx`（實質條件句定義的三大系統性理由：與 Thomason 歸納取代一致、理論簡單性、以及四列真值表若改變任一列將破壞有效性/無效性判定的完整證明） $\implies$ 關聯 **Ch. 2 & Ch. 3**（[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]、[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]）。
  4. `Ex_Ch03_習題解答.docx`（Ex 3-1, 3-2, 3-3, 3-5, 3-6, 3-8, 3-10, 3-11, 3-13 完整中文解答） $\implies$ 關聯 **Ch. 3**（[[Ch03 真值表 (Truth Tables)]]）。
  5. 5 份原文書 Ch.3 補充 PDF（`Supp_Ch03_WalkThrough_Substitution_Instances_Ex3-3_p57-59.pdf`、`Supp_Ch03_WalkThrough_Construct_Truth_Table_p63-65.pdf`、`Supp_Ch03_Logical_Equivalence_Ex3-7_p67.pdf`、`Supp_Ch03_Exercise_3-12_Justification_of_Truth_Tables_p81.pdf`、`Supp_Ch03_Exercise_3-11_3-12_Answers_p388.pdf`） $\implies$ 關聯 **Ch. 3**（[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]、[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]）。
  6. `Ex_Ch04_習題解答.docx`（Ex 4-1 ~ Ex 4-14 完整證明與問答，特別包含 **Ex 4-14 語句邏輯的表達完備性 Expressive Completeness、$2^{(2^n)}$ 種真值表計數與選言範式 DNF 構造法**） $\implies$ 關聯 **Ch. 4 & Ch. 5 後設邏輯**（[[Ch04 自然演繹法證明 (Natural Deduction Proofs)]]、[[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]）。
  7. `Ex_Ch05_習題解答.docx`（Ex 5-1 ~ Ex 5-8 完整證明，含使用 IP vs. 不使用 IP 雙軌對照、無前提定理、Ex 5-7 證明前提集不一致、Ex 5-8 評估候選推論規則能否加入系統） $\implies$ 關聯 **Ch. 5**（[[Ch05 條件證法與間接證法 (Conditional and Indirect Proofs)]]、[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]）。
  8. `Exam_Ch01_to_Ch05_邏輯115上期中考解答.doc`（2026/10/29 期中考全卷五大題 100% 詳解與一題三解） $\implies$ 綜合關聯 **Ch. 1 ~ Ch. 5**。
- **新建與大幅擴充之 Wiki 頁面**：
  - **新建頁面**：[[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]]（完整收錄期中考五大題與多重證法）。
  - **大幅擴充習題頁**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]（納入 Ex 1-3, Ex 2-7, Ex 2-10, Ex 3-1 ~ Ex 3-13 及原文書 p.81/p.388 Ex 3-12 第 2, 4, 6 題畢業魔王題詳解）、[[習題解析二：語句邏輯自然演繹法、CP與IP證明 (Exercises on Sentential Logic Proofs)]]（納入 Ex 4-1 ~ Ex 4-14 含逆向 Dist 提公因式與 DNF 表達完備性、Ex 5-1 ~ Ex 5-8 全解）。
  - **擴充核心概念與章節頁**：[[真值函應與邏輯連詞 (Truth-Functions and Logical Connectives)]]、[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]、[[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]] 及 Ch.01 ~ Ch.05 章節總覽頁與 `wiki/index.md`（依使用者指示，本次僅擴充 Wiki 資料庫，暫不修改簡報 `slides/index.html`）。

---

## [2026-11-23] lint | 第二批增量導入後之 4 維度健康檢查迴圈 (Node 4 Verification)

- **執行節點**：Node 4 (4-Dimensional Lint Check)
- **檢驗指標**：
  - **總 Wiki Markdown 檔案數**：33 篇（含 `AGENT.md`, `wiki/index.md`, `wiki/log.md` 與 30 篇分類知識頁/習題頁/綜合頁）。
  - **斷連數 (Broken Wikilinks)**：**0**。
  - **孤島頁數 (Orphan Pages)**：**0**（新增之 [[習題解析五：邏輯(115上)期中考全卷詳解與多重證法比較 (Midterm Exam Solutions and Alternative Proofs)]] 已與 Ch.01~Ch.05、核心概念頁及習題解析一、二完成雙向互連）。

---

## [2026-11-23] ingest | 第三批增量導入：11 份歷屆邏輯小考(1)~(6)解答、關係述詞 Ex 10-6 修正補充與原文書規則總表

- **執行節點**：Node 0 (Pre-Check) $\rightarrow$ Node 1 (Raw Extraction) $\rightarrow$ Node 2 (Entity Update) $\rightarrow$ Node 3 (Relational Graph Linking) $\rightarrow$ Node 4 (Lint Verification)
- **依檔名線索與內容判定之章節關聯與歸檔 (`raw/` 新增 11 個唯讀原始檔，累計 33 個原始檔)**：
  1. `Supp_Ch01_Plan_of_Book_Ex1-3_p14.pdf`（原文書 p.14 *The Plan of This Book*、Exercise 1-3 全套 15 題與 Philosophical Discussions 模態可能性討論） $\implies$ 關聯 **Ch. 1**（[[Ch01 邏輯導論 (Introduction to Logic)]]、[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]）。
  2. `Supp_Ch02_Symbolizing_Examples_Ex2-6_p44-45.pdf`（原文書 p.44–45 符號化回譯雙重檢查法、12 個複雜符號化範例與 Exercise 2-6 全套 12 題） $\implies$ 關聯 **Ch. 2**（[[Ch02 語句邏輯的符號化 (Symbolizing in Sentential Logic)]]、[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]）。
  3. `Supp_Ch04_Ch05_Valid_Forms_for_Sentential_Logic.pdf`（語句邏輯 8 條蘊含規則 + 10 條等值規則 + CP/IP 速查總表） $\implies$ 關聯 **Ch. 4 & Ch. 5**（[[八條單向蘊含推論規則 (Eight Implicational Rules of Inference)]]、[[十條雙向等值置換規則 (Ten Equivalence Rules of Replacement)]]、[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]）。
  4. `Supp_Ch07_Ch09_Ex10-6_複雜關係述詞符號化與定理Q17補充.docx`（Ex 9 / Ex 10-6 第 3 題選民迎合與定理 Q17 應用、第 13 題欠牛頓錢四元/五元關係三種等價修正寫法） $\implies$ 關聯 **Ch. 7 & Ch. 9 (原文書 Ch. 10)**（[[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]]、[[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]]、[[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]]）。
  5. 7 份歷屆邏輯小考解答：
     - `Quiz1_Ch01_邏輯小考1解答_20240919.docx`（Ch.1 是非題 10 題） $\implies$ 關聯 **Ch. 1**
     - `Quiz2_Ch02_邏輯小考2解答_20240926.docx`（Ch.2 符號化 5 題） $\implies$ 關聯 **Ch. 2**
     - `Quiz3_Ch03_邏輯小考3解答_20241003.docx`（Ch.3 簡短真值表有效性與一致性 3 題） $\implies$ 關聯 **Ch. 3**
     - `Quiz3_Ch01_to_Ch03_邏輯小考3解答_20231024_選擇題.docx`（Ch.1~Ch.3 觀念單選題 10 題，含有效論證的無效形式與一對一展開形式） $\implies$ 關聯 **Ch. 1 ~ Ch. 3**
     - `Quiz4_Ch04_邏輯小考4解答_20241024.docx` & `Quiz5_Ch04_邏輯小考5解答_20231107.docx`（Ch.4 自然演繹 18 條規則證明與一題雙解） $\implies$ 關聯 **Ch. 4**
     - `Quiz6_Ch05_邏輯小考6解答_20231114.docx`（Ch.5 無前提定理 $\vdash \sim A \supset (A \supset B)$ 一題三解與複雜定理一題四解） $\implies$ 關聯 **Ch. 5**
- **Node 4 Lint 檢驗結果**：全部 33 篇 Wiki Markdown 檔案 **0 斷連 (Broken Links = 0)**、**0 孤島頁 (Orphans = 0)**。

---

## [2026-11-23] slides | 依據人類介入點 C 決策：重構 AGENT.md 六大工程規範與「百科全書 + 主頁最熱焦點輪播簡報」合一 HTML

- **執行節點**：Node 5 (Unified HTML & Spotlight Carousel Compilation) $\rightarrow$ Node 6 (Frontend Link & Carousel Verification) $\rightarrow$ Node 7 (Logging)
- **更新項目 1：升級後台規範 [[AGENT]] (`AGENT.md`)**：
  - 完整寫入截圖六大工程設計：(1) 節點拆解、(2) 每個節點的輸入與輸出檔案表、(3) 程式腳本 / AI 審查 / 人類審查三層檢查分工（新增 Regex 算式缺字預檢）、(4) 三大人類介入點 (Checkpoints A, B, C) 與對話框同步回報機制、(5) 分級錯誤退回路由（退回 Node 4b 或 Node 1）、(6) **硬性止損熔斷機制 (`Max Retries = 2` / `Max Fallback = 1` / `Max Auto-Overwrite = 0`)**。
- **更新項目 2：建構「百科全書主知識庫 + 主頁最熱時事輪播式教學簡報」二合一 HTML (`logic_wiki.html` & `slides/index.html`)**：
  1. **後台資訊隔離**：將 LLM Wiki 架構說明與 `log.md` 完全保留於後台 Markdown，不混入前端畫面。
  2. **承襲 `hw9` 極簡百科視覺風格**：純白底色 (`#ffffff`)、亮橘色線條與高光 (`#ff7300`)、藍紫色底線雙向連結 (`#5c56d6` 的 `a.wikilink`)、右側磨砂玻璃可收折目錄側欄（含即時篩選、全部展開/收合），清空舊資料後完整灌入目前知識庫的 **31 篇核心知識頁與題庫全解**。
  3. **主頁「最熱時事輪播式 (Spotlight Carousel)」跨章節綜合與互動診斷簡報**：
     - 嵌入於主頁（`#home`）搜尋框正下方，支援**自動輪播（8.5 秒切換，滑鼠移入自動暫停）**、**頂部 8 大焦點話題頁籤 (Ticker Tabs)**、**左右方向鍵切換**、**底部動態圓點指示器**與**一鍵展開全螢幕簡報 (`⛶ 全螢幕簡報`)**。
     - 8 張焦點簡報聚焦於**跨章節綜合比較 (`syntheses`)**（01. 三階段邏輯演進、02. 語意 $\models$ vs 語法 $\vdash$ 雙軌對稱、03. 三大推論防呆限制、04. 準變元下毒與解毒狀態機）與**互動式考題與錯誤證明診斷室 (`exercises`)**（05. 期中考是非題十大陷阱、06. 真值表證成魔王題 Ex 3-12 與 DNF 表達完備性、07. 量詞五項限制抓錯 Ex 9-2、08. 小考 6 無前提定理 6 步秒殺與羅素確定描述詞）。
- **Node 6 前端驗證結果**：HTML 內嵌 32 個 `<article>` 視圖（1 個含輪播簡報之主頁 + 31 篇百科詞條），**未解析連結數 (`wikilink-unresolved`) = 0**。

---

## [2026-11-23] ingest | 第四批（最終封板批次）增量導入：11 份述詞邏輯習題解答(Ch.7~10)、部分/全部否定補充、林正弘55條述詞邏輯定理與小考(5)(8)(9)

- **執行節點**：Node 1 (Raw Extraction & Pre-Check) $\rightarrow$ Node 2 (Entity Compilation) $\rightarrow$ Node 3 (Graph Linking) $\rightarrow$ Node 4 (4D Lint) $\rightarrow$ Node 5 (Encyclopedia HTML Sync)
- **依檔名線索與內容判定之章節關聯與歸檔 (`raw/` 新增 11 個唯讀原始檔，全庫累計 44 個原始檔封板)**：
  1. `Supp_Ch07_補充一_部份否定與全部否定.docx` & `Supp_Ch07_補充二_部分否定全部否定和雙重否定的翻譯.docx`（兩者與三者以上之部分否定 `not all / both...not` vs. 全部否定 `neither / none / no one`、總括副詞部分否定、以及 6 種雙重否定轉肯定句型） $\implies$ 關聯 **Ch. 2 & Ch. 7**（[[量詞、論域與對當方陣 (Quantifiers, Domain, and Square of Opposition)]] 第 5 節）。
  2. `Ex_Ch07_習題解答.docx`（Ex 7-3 ~ Ex 7-11 全解，含大象保育句部分否定 vs. 全部否定空真辨析、「大多數 Most」在無等同號時的翻譯限制） & `Quiz5_Ch07_邏輯小考5解答_20241205_述詞符號化.docx` $\implies$ 關聯 **Ch. 7**（[[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]]、[[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]]）。
  3. `Ex_Ch08_習題解答.docx`（Ex 8-1 解釋真假構造、Ex 8-2 自然數算術反例、Ex 8-3 $D=\{a,b\}$ 展開式反例） & `Quiz8_Ch08_邏輯小考8解答_20231212_展開式與無效反例.docx`（$D=\{a,b,c\}$ 展開式與 $D=\{a,b\}$ 無效反例） $\implies$ 關聯 **Ch. 8**（[[Ch08 述詞邏輯語意學 (Predicate Logic Semantics)]]、[[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]）。
  4. `Ex_Ch09_習題解答.docx`（Ex 9-1 ~ Ex 9-5 全解，含 Ex 9-2 抓錯與 Ex 9-4 QN 診斷）、`Quiz9_Ch09_邏輯小考9解答_20231219_述詞邏輯證明.docx`（EG 換變元防 EI 衝突技巧） & `Supp_Ch09_Ch11_Rules_for_Predicate_Logic.pdf`（UI, EI, UG, EG, QN, ID, IR 規則與限制官方總表） $\implies$ 關聯 **Ch. 9 & Ch. 11**（[[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]]、[[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]、[[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]）。
  5. `Ex_Ch10_關係述詞習題解答.docx`（Ex 10-1 ~ 10-6 多元關係與時間/地點顯性量化符號化、Ex 10-2 雙量詞展開式、Ex 10-8 二元/三元關係自然數與展開式反例、Ex 10-10 ~ 10-12 多重量詞關係證明） $\implies$ 關聯 **Ch. 7, Ch. 8, Ch. 9 (原文書 Ch. 10 多量詞關係邏輯)**（[[習題解析三：述詞邏輯與確定描述詞符號化 (Exercises on Predicate Logic Symbolization)]]、[[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]）。
  6. `Supp_Ch09_Ch10_附錄二_林正弘述詞邏輯55條定理與證明.docx`（參考林正弘《邏輯》pp. 346–365 之 Q1 ~ Q55 定理與無前提證明） $\implies$ 關聯 **Ch. 7, Ch. 9, Ch. 10**，新建跨章節綜合專頁 [[述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)]]。
- **人類介入點 A 偵測與同步回報紀錄**：
  1. `Ex_Ch08_習題解答.docx` 中 `Ex 8-2 (5)` 原始檔令 $Px=$ 2 的倍數、$Qx=$ 3 的倍數、$Rx=$ 偶數，這會使結論 $(\exists x)(Rx \cdot \sim Qx)$ 也為真（$x=2$）而無法構成無效反例！已於 [[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]] 中修正為「$Px=$ 偶數、$Qx=$ 4 的倍數、$Rx=$ 8 的倍數」（使前提皆真、結論為假），並於對話框向人類回報。
  2. `Ex_Ch10_關係述詞習題解答.docx` 中 `Ex 10-11 (11)` 第 2~3 列在 AP `(∃y)(Ay · Cxy)` 含自由變元 $x$ 時直接對第 2 列做 EI 得 `Ay · Cxy`，使 $x$ 出現在 EI 列中；已在 [[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]] 加註教學提示說明為何在 EG 重新拘束 $y$ 後語意有效，並同步回報人類。
- **Node 4 & Node 6 最終封板檢驗結果**：
  - `raw/` 原始檔案總數：**44 個**。
  - `wiki/` Markdown 檔案總數：**34 篇**（含 `AGENT.md`, `wiki/index.md`, `wiki/log.md` 與 31 篇核心知識頁/習題頁/綜合頁）。
  - 斷連數 (`Broken Wikilinks`)：**`0`**｜孤島頁數 (`Orphans`)：**`0`**｜HTML 未解析連結數 (`wikilink-unresolved`)：**`0`**（簡報維持 8 張焦點輪播不變，百科詞條已同步更新至 32 篇完整詞條）。


---

## [2026-11-23] slides | 前端視覺與教學簡報三項客製化調整（底部關聯卡片、主頁跨章節綜合教學簡報與鳥獸戲畫貼圖、統一正體字樣）

- **執行節點**：Node 5 (Unified HTML & Teaching Slides Compilation) $\rightarrow$ Node 6 (Frontend Link & Style Verification) $\rightarrow$ Node 7 (Logging)
- **完成之三項 HTML 介面與簡報重構**：
  1. **「涵蓋章節」與「對應概念／方法」下移至每篇百科詞條最下方**：
     - 調整編譯器解析器，將每篇百科頁面原本位於頂部標題下方的 `> **所屬章節** / **涵蓋章節** / **對應概念** / **對應方法** / **對應原始檔案**` 區塊抽出，統一渲染於每篇詞條最底部的 `.article-bottom-meta-card`（章節與概念關聯索引卡），讓讀者打開頁面即可直接進入核心正文，閱讀完畢後再由底部卡片雙向跳轉。
  2. **主頁預覽輪播簡報改為「跨章節綜合比較 (`wiki/syntheses/`)」10 張完整教學簡報，並搭配 `assets/` 鳥獸戲畫貼圖裝飾**：
     - 將 `wiki/syntheses/` 下的四大跨章節綜合比較主題完整轉化為 **10 張結構化教學簡報**，直接嵌入於主頁（`#article-home`）預覽與輪播（亦支援一鍵展開全螢幕教學簡報模式），並依每張投影片的教學情境配置 [assets/](file:///d:/家當/清大/生成式AI文字與圖像生成的原理與實務/hw10/LLM%20Wiki%20Notes/assets) 中的 10 張鳥獸戲畫貼圖：
       - **Slide 01–02（系統演進三部曲）**：語句邏輯 (SL) $\rightarrow$ 述詞邏輯 (PL) $\rightarrow$ 等同與確定描述詞 (ID) 的表達力三級跳（搭配飛躍青蛙貼圖 `choju111_0006_2.png`）與三系統語法／語意／推論規則底層同構表（搭配執教鞭青蛙講師貼圖 `choju109_0011_3.png`）。
       - **Slide 03–04（語意 $\models$ vs. 語法 $\vdash$ 雙軌對稱架構）**：語意學真值世界與語法學自然演繹系統的健全性與完備性橋樑（搭配張開雙臂平衡老虎貼圖 `choju23_0038_4.png`），以及四大邏輯性質在語意（真值表／模型）與語法（自然演繹／CP／IP）的雙軌檢驗對照表（搭配撐荷葉大傘老虎貼圖 `choju68_0023_1.png`）。
       - **Slide 05–07（自然演繹法三大核心限制比較）**：防範圍越界、防任意特例冒充通則、防特定個體偷渡進假設的三大防呆結界（搭配施展八角結界老虎貼圖 `choju97_0024_5.png`）、蘊含規則整列限制 vs. 等值規則子句置換（搭配舉大槌敲醒青蛙貼圖 `choju108_0007_1.png`）、以及量詞五項限制與「EI 同列下毒、CP 消去 AP 解毒」生命週期（搭配抱頭冒汗老虎貼圖 `choju95_0039_3.png`）。
       - **Slide 08–10（林正弘述詞邏輯 55 條核心定理 Q1–Q55）**：量詞對連詞分配律之雙向等值 vs. 單向蘊含（搭配托腮沉思老虎貼圖 `choju93_0012_3.png`）、大一邏輯頭號殺手「橋倒問題 Q17 vs. Q18」（搭配恍然大悟青蛙貼圖 `choju112_0017_4.png`）、以及多重量詞交換律 Q49–Q55 與「每個男孩都喜歡某個女孩」範疇歧義（搭配執扇回眸老虎貼圖 `chojuother2nd0014_10.png`）。
  3. **全面移除無故斜體字（`font-style: italic`），統一全站字樣**：
     - 全域 CSS 強制設定 `font-style: normal !important`（涵蓋 `*`, `em`, `i`, `.logic-math-inline`, `.logic-math-block`, `blockquote`），並將 Markdown 解析器中的單星號 `*...*` 改為正體 `<span>`，確保所有中英文術語、邏輯連詞與量詞公式皆以乾淨統一的正體字樣呈現。
- **Node 6 前端驗證結果**：`logic_wiki.html` 與 `slides/index.html` 同步生成完畢，`wikilink-unresolved = 0`、`font-style: italic = 0`、10 張鳥獸戲畫貼圖路徑與 33 張底部關聯卡片 100% 正常顯示。
