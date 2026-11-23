---
title: "有效性與健全性 (Validity and Soundness)"
category: concepts
chapters: ["Ch. 1", "Ch. 3"]
tags: [logic, concept, validity, soundness, deduction, induction, truth-value]
updated: 2026-11-22
---

# 有效性與健全性 (Validity and Soundness)

> **所屬章節**：[[Ch01 邏輯導論 (Introduction to Logic)]]、[[Ch03 真值表 (Truth Tables)]]
> **對應方法**：[[真值表與簡短真值表法 (Truth Table and Short Truth Table Method)]]
> **對應練習**：[[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]

在形式邏輯中，**有效性 (Validity)** 與**健全性 (Soundness)** 是評價演繹論證（Deductive Arguments）的兩個核心標準。初學者最常犯的錯誤，就是將「語句的真假 (Truth/Falsity of Statements)」與「論證的有效無效 (Validity/Invalidity of Arguments)」混為一談。

---

## 1. 演繹論證 (Deduction) vs. 歸納論證 (Induction)

| 比較項目 | 演繹有效論證 (Deductively Valid Argument) | 歸納強論證 (Inductively Strong Argument) |
| :--- | :--- | :--- |
| **核心定義** | **不可能前提皆真而結論為假**（若前提皆真，結論**必然**為真） | 若前提皆真，結論**很可能 (Probably)** 為真，但**邏輯上仍可能前提皆真而結論為假** |
| **訊息含量** | 結論的訊息**已完全隱含於前提之中**（不擴展經驗新知，旨在釐清蘊涵關係） | 結論的訊息**超出前提所含範圍**（從已知推論未知，可擴展經驗知識） |
| **決定因素** | 完全由**[[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]** 決定（屬於非黑即白的全有或全無性質） | 取決於經驗證據的數量、代表性與機率支持程度（有強弱程度之分） |
| **添加新前提的影響** | **單調性 (Monotonic)**：有效論證無論再加入任何新前提，依然有效 | **非單調性 (Non-monotonic)**：加入新證據（如「今天早上小行星撞地球」）可能使原本強的歸納論證變弱 |
| **講義經典範例** | 1. 小明是新竹人或台北人。<br>2. 小明不是新竹人。<br>$\therefore$ 小明是台北人。（選言三段論 $p \lor q, \sim p / \therefore q$） | 1. 過去幾十億年太陽每天從東邊升起。<br>$\therefore$ 明天太陽也會從東邊升起。<br>（或：George Lucas 前幾部電影都大賣 $\therefore$ 下一部也會大賣） |

---

## 2. 真假值與有效性的 8 種組合矩陣 (Truth vs. Validity Matrix)

- **基本範疇鐵律**：
  - 只有**陳述句 (Statements)** 才有「真 (True)」或「假 (False)」（論證不能說是真的或假的）。
  - 只有**論證 (Arguments)** 才有「有效 (Valid)」或「無效 (Invalid)」（單一語句不能說是有效或無效的）。
- 在「前提事實真假 × 結論事實真假 × 論證有效/無效」的 $2 \times 2 \times 2 = 8$ 種排列組合中，**有 7 種皆可存在，唯獨 1 種在邏輯上絕對不可能存在**：

| 情況 | 前提實際真值 | 結論實際真值 | 有效 (Valid) 範例 | 無效 (Invalid) 範例 |
| :---: | :---: | :---: | :--- | :--- |
| **Case 1** | **全真 (All T)** | **真 (T)** | **【健全論證 Sound】**<br>所有人都會死 (T)；孔子是人 (T)<br>$\therefore$ 孔子會死 (T) | 華盛頓曾橫渡德拉瓦河 (T)<br>拿破崙曾是法國皇帝 (T)<br>$\therefore$ 花椰菜是一種蔬菜 (T) |
| **Case 2** | **全真 (All T)** | **假 (F)** | 🚫 **【邏輯上絕對不可能！】**<br>*(依有效論證定義，前提皆真時結論必真)* | 若下雨則地濕 (T)；地是濕的 (T)<br>$\therefore$ 剛才下雨了 (F，其實是灑水車)<br>*(肯定後件謬誤：$p \supset q, q / \therefore p$)* |
| **Case 3** | **含假 (Some F)** | **真 (T)** | 所有狗都有八條腿 (F)<br>賴清德是一隻狗 (F)<br>$\therefore$ 賴清德有八條腿 *(此為 Case 4)*<br>---<br>所有魚都會游泳 (T)；海豚是魚 (F)<br>$\therefore$ 海豚會游泳 (T) | 所有哺乳類都有翅膀 (F)<br>鯨魚有翅膀 (F)<br>$\therefore$ 鯨魚是哺乳類 (T) |
| **Case 4** | **含假 (Some F)** | **假 (F)** | 所有人都有翅膀 (F)<br>孔子是人 (T)<br>$\therefore$ 孔子有翅膀 (F) | 所有人都是萬物之靈 (T)<br>孔子不是人 (F)<br>$\therefore$ 孔子不是萬物之靈 (F) |

> **關鍵考試結論**：
> 1. 知道一個論證**無效**，完全無法推知其前提或結論在事實上是真是假（Case 1~4 的無效欄皆可能發生）。
> 2. 知道一個論證的前提與結論在事實上**全部為真**，也無法斷定該論證一定有效（見 Case 1 無效欄）！
> 3. 只有當「論證有效 **且** 前提全真」時，才能保證結論一定為真；或者當「前提全真 **且** 結論為假」時，能立刻斷定論證一定無效（反例法核心原理）。

---

## 3. 健全性 (Soundness)

為了在日常與科學論證中同時要求「形式推論正確」與「前提內容符合事實」，邏輯學定義了**健全論證 (Sound Argument)**：

$$\text{健全論證 (Sound Argument)} \equiv \underbrace{\text{形式上有效 (Valid)}}_{\text{邏輯學家的任務}} + \underbrace{\text{所有前提在事實上皆為真 (All Premises are True)}}_{\text{各學科經驗科學的任務}}$$

- 若一個論證是**不健全的 (Unsound)**，代表它要嘛是**無效的 (Invalid)**，要嘛**至少有一個假前提 (Has at least one false premise)**（或兩者皆是）。
- **為什麼邏輯學主要研究「有效性」而非直接檢驗前提真假？**
  1. 檢驗前提的經驗真假（如「宇宙正在加速膨脹」或「某藥物能抑制病毒」）屬於物理學、醫學、歷史學等經驗學科的專業範疇。
  2. 在許多哲學、數學或科學假設推演（如歸謬法、思想實驗）中，我們經常需要對**目前不知真假、甚至已知為假的前提**進行推演（「如果這個假說為真，會推導出什麼結果？」），此時只有形式有效性才能發揮作用。

---

## 4. 相關概念與方法連結

- **有效性與一致性的等價轉換**：如何把「論證有效性」轉化為「語句集合的不一致性」？ $\implies$ [[一致性與反例集 (Consistency and Counterexample Set)]]
- **有效性的決定因素**：什麼是邏輯形式與取代實例？ $\implies$ [[邏輯形式與取代實例 (Logical Form and Substitution Instance)]]
- **後設系統層級的健全性**：區分「個別論證的健全性」與「邏輯系統的健全性與完備性」 $\implies$ [[後設邏輯：健全性與完備性 (Metalogic - Soundness and Completeness)]]
- **實戰演練**：真假值與有效性 8 種組合判斷題 $\implies$ [[習題解析一：論證辨識、真值組合與真值表檢驗 (Exercises on Arguments and Truth Tables)]]
