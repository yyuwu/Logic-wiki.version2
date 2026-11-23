---
title: "論證與解釋 (Argument vs Explanation)"
category: concepts
chapters: ["Ch. 1"]
tags: [logic, concept, argument, explanation, statement, premise, conclusion, justification]
updated: 2026-11-22
---

# 論證與解釋 (Argument vs Explanation)

> **所屬章節**：[[Ch01 邏輯導論 (Introduction to Logic)]]
> **對應練習**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]

在哲學邏輯中，我們進行形式分析的第一步，是判斷一段自然語言文本究竟是不是一個**論證 (Argument)**。日常語言中的連接詞「因為 (because)」、「所以 (therefore)」既可以用來提出**證成結論的理由 (Reason / Justification)**，也可以用來提供**解釋既定事實的成因 (Causal / Genetic Explanation)**。嚴格區分這兩者是邏輯分析的起點。

---

## 1. 語句 (Sentence) 與陳述句 (Statement)

- **語句 (Sentence)**：符合文法結構的語言字串，包含直述句、疑問句、命令句、感嘆句。
- **陳述句 (Statement / Proposition)**：具有**真假值 (Truth-value: True `T` / False `F`)**、能夠對世界做出斷言的語句。
- **語境脈絡原則 (Principle of Context)**：
  - 邏輯學不單看表面的文法句型，而是看該句在**實際語境中所表達的意義**。
  - 例如：主管對遲到的員工大吼：「誰是這裡的老大？（疑問句型）」或「給我看看你的考績！（命令句型）」，在實際脈絡中其實是在陳述「我是這裡的老大，你應該聽我的話」，因此可以作為論證的前提或結論。

---

## 2. 論證的結構：前提與結論

- **論證 (Argument)**：由一組陳述句所構成的集合，其中**一個**陳述句是說話者試圖確立的**結論 (Conclusion)**（標準記號以 `∴` 表示），其餘一或多個陳述句則是提供理據來支持該結論的**前提 (Premises)**。
- **指示詞 (Indicator Words)**：
  - **前提指示詞**：因為（because, since, for）、既然、由於、鑑於（given that, inasmuch as）、假設。
  - **結論指示詞**：所以（therefore, thus）、因此（hence, consequently, accordingly）、由此可見（it follows that, we may infer that）、證明了。
- **注意**：一個論證不一定含有指示詞！必須根據前後句之間的「支持與被支持關係」來判定何者為前提、何者為結論。

---

## 3. 核心辨析：理由證成 (論證) vs. 因果說明 (解釋)

當遇到「$Q$，因為 $P$」的結構時，該如何判斷它是**論證**還是**因果解釋**？

| 比較維度 | 論證 (Argument / Justification) | 因果說明 / 發生學解釋 (Causal / Genetic Explanation) |
| :--- | :--- | :--- |
| **對 $Q$ 的預設態度** | $Q$ 是否為真**尚待確立或有爭議**（聽者未必相信 $Q$） | 說話者與聽者**皆已預設 $Q$ 是既定事實（已確知 $Q$ 為真）** |
| **提出 $P$ 的目的** | 提供**認識論上的理由 (Epistemic Reason)**，說服聽者相信 $Q$ 為真 | 提供**存有論上的成因 (Causal Factor)**，說明 $Q$ 為何會發生 |
| **邏輯形式檢驗** | 關心從 $P$ 推導出 $Q$ 是否具有[[有效性與健全性 (Validity and Soundness)]] | 關心因果機制是否符合科學定律或歷史事實 |
| **講義經典範例 1** | 「小珍**應該**很氣他（推測結論），因為他撞壞了她的車（支持理由）。」 | 「小珍很氣他（已知事實），因為他撞壞了她的車（生氣的原因）。」 |
| **講義經典範例 2** | 「我們**應該**限制溫室氣體排放，因為它正在破壞大氣臭氧層。」 | 「新竹風很大（眾所周知的事實），因為新竹三面環山一面臨海（地理成因）。」 |

---

## 4. 發現的脈絡 vs. 證成的脈絡 (Context of Discovery vs. Context of Justification)

二十世紀科學哲學家萊欣巴哈（Hans Reichenbach）提出的經典區分：
1. **發現的脈絡 (Context of Discovery)**：
   - 關注一個人是**透過什麼心理過程、歷史機緣或靈感**想出某個點子或假說的。
   - 範例：牛頓因為在樹下被掉下來的蘋果砸到頭，因而想出萬有引力定律；科學家在夢中看見蛇咬住自己的尾巴，因而想出苯環分子結構。
   - 這屬於心理學、傳記歷史學或知識社會學的研究對象。
2. **證成的脈絡 (Context of Justification)**：
   - 關注一個主張或結論是**透過什麼樣的前提、實驗證據與推論規則**而被證明或支持的。
   - **邏輯學唯一關心的就是「證成的脈絡」**！一個科學理論或哲學主張是否合理，完全取決於支持它的論證是否有效或歸納強，而與提出者當初是做夢還是被蘋果砸到毫無關係（若以某人的出身或發現動機來否定其論證，即犯了「發生學謬誤 Genetic Fallacy」）。

---

## 5. 相關概念與方法連結

- **下一個概念**：一旦確認一段話是論證，下一步就是評估它的推論品質 $\implies$ [[有效性與健全性 (Validity and Soundness)]]
- **語句集合的內在性質**：檢查一組陳述句是否自相矛盾 $\implies$ [[一致性與反例集 (Consistency and Counterexample Set)]]
- **實戰演練**：辨識日常語句是論證還是因果解釋 $\implies$ [[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]
