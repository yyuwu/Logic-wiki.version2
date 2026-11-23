---
title: "述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)"
category: syntheses
chapters: ["Ch. 7", "Ch. 9", "Ch. 10 (Relational Predicate Logic)"]
source: "Supp_Ch09_Ch10_附錄二_林正弘述詞邏輯55條定理與證明.docx (林正弘《邏輯》pp. 346-365) & Ex_Ch10_關係述詞習題解答.docx (Ex 10-12)"
tags: [logic, synthesis, predicate-logic, theorems, quantifier-shift, Q1-Q55, CP, IP, UG, EI]
updated: 2026-11-23
---

# 述詞邏輯55條核心定理與量詞推論架構 (55 Theorems of Predicate Logic)

> **對應原始文獻**：`raw/Supp_Ch09_Ch10_附錄二_林正弘述詞邏輯55條定理與證明.docx`（參考林正弘《邏輯》，三民書局 1970，pp. 346–365）及 `raw/Ex_Ch10_關係述詞習題解答.docx`（課本 p. 239 習題 10-12）
> **關聯章節與方法**：[[Ch07 述詞邏輯的符號化 (Predicate Logic Symbolization)]]、[[Ch09 述詞邏輯的證明 (Predicate Logic Proofs)]]、[[四條量詞推論規則與五項限制 (Four Quantifier Rules and Five Main Restrictions)]]、[[條件證法與間接證法 (Conditional and Indirect Proof - CP and IP)]]
> **對應習題頁**：[[習題解析四：述詞邏輯無效性反例與量詞證明 (Exercises on Predicate Logic Invalidity and Proofs)]]

本頁完整收錄並分類整理**附錄二：述詞邏輯 55 條核心定理（Q1 ～ Q55）**及其無前提自然演繹證明（Zero-Premise Deductions）。這 55 條定理系統性地揭示了**量詞對邏輯連詞的分配律**、**量詞移入與移出括弧（Prenex Normal Form 前束範式轉換）的等價條件**、以及**多重量詞交換順序的單向與雙向法則**。

---

## 一、 第一類：單一量詞對邏輯連詞（$\supset, \lor, \cdot, \equiv$）的分配律（Q1 ～ Q10）

> ⚠️ **必考核心判準**：
> - **全稱量詞 $(x)$ 可以雙向分配進「連言 $\cdot$」（Q4）**，但對「選言 $\lor$」只有單向（Q6：從 $[(x)Fx \lor (x)Gx]$ 可推得 $(x)(Fx \lor Gx)$，反之不然！例如每個人都是男的或女的，不能推出所有人都是男的或所有人都是女的！）。
> - **存在量詞 $(\exists x)$ 可以雙向分配進「選言 $\lor$」（Q3）**，但對「連言 $\cdot$」只有單向（Q5：從 $(\exists x)(Fx \cdot Gx)$ 可推得 $[(\exists x)Fx \cdot (\exists x)Gx]$，反之不然！）。

| 定理編號 | 述詞邏輯定理標準公式（注意單向 $\supset$ vs. 雙向 $\equiv$） | 逆命題是否成立？ |
| :---: | :--- | :---: |
| **Q1** | $\vdash (x)(Fx \supset Gx) \ \supset \ [(x)Fx \supset (x)Gx]$ | ❌ 反之不然！ |
| **Q2** | $\vdash (x)(Fx \supset Gx) \ \supset \ [(\exists x)Fx \supset (\exists x)Gx]$ （即 Ex 10-12 第 7 題） | ❌ 反之不然！ |
| **Q3** | $\vdash (\exists x)(Fx \lor Gx) \ \equiv \ [(\exists x)Fx \lor (\exists x)Gx]$ （存在對選言**雙向等值**！） | ✅ 雙向等值 |
| **Q4** | $\vdash (x)(Fx \cdot Gx) \ \equiv \ [(x)Fx \cdot (x)Gx]$ （全稱對連言**雙向等值**！即 Ex 10-12 第 5 題） | ✅ 雙向等值 |
| **Q5** | $\vdash (\exists x)(Fx \cdot Gx) \ \supset \ [(\exists x)Fx \cdot (\exists x)Gx]$ | ❌ 反之不然！ |
| **Q6** | $\vdash [(x)Fx \lor (x)Gx] \ \supset \ (x)(Fx \lor Gx)$ | ❌ 反之不然！ |
| **Q7** | $\vdash [(\exists x)Fx \supset (\exists x)Gx] \ \supset \ (\exists x)(Fx \supset Gx)$ | ❌ 反之不然！ |
| **Q8** | $\vdash [(x)Fx \supset (\exists x)Gx] \ \supset \ (\exists x)(Fx \supset Gx)$ | ❌ 反之不然！ |
| **Q9** | $\vdash (\exists x)(Fx \supset Gx) \ \equiv \ [(x)Fx \supset (\exists x)Gx]$ （即 Ex 10-11 第 3 題 & Ex 10-12 第 9 題） | ✅ 雙向等值 |
| **Q10** | $\vdash (x)(Fx \equiv Gx) \ \supset \ [(x)Fx \equiv (x)Gx]$ | ❌ 反之不然！ |

### 💡 Q1、Q2、Q3、Q7 標準無前提證明精選
```text
【Q1 證明：⊢ (x)(Fx ⊃ Gx) ⊃ [(x)Fx ⊃ (x)Gx]】  【Q2 證明：⊢ (x)(Fx ⊃ Gx) ⊃ [(∃x)Fx ⊃ (∃x)Gx]】
  | 1. (x)(Fx ⊃ Gx)         AP                   | 1. (x)(Fx ⊃ Gx)         AP
  | | 2. (x)Fx              AP                   | | 2. (∃x)Fx             AP
  | | 3. Fx ⊃ Gx            1 UI                 | | 3. Fx                 2 EI (先做 EI！)
  | | 4. Fx                 2 UI                 | | 4. Fx ⊃ Gx            1 UI (後做 UI！)
  | | 5. Gx                 3, 4 MP              | | 5. Gx                 3, 4 MP
  | | 6. (x)Gx              5 UG (x 未在 AP 自由出現!) | | 6. (∃x)Gx             5 EG
  | 7. (x)Fx ⊃ (x)Gx        2–6 CP               | 7. (∃x)Fx ⊃ (∃x)Gx      2–6 CP
  8. (x)(Fx ⊃ Gx) ⊃ [(x)Fx ⊃ (x)Gx]  1–7 CP      8. (x)(Fx ⊃ Gx) ⊃ [(∃x)Fx ⊃ (∃x)Gx]  1–7 CP

【Q7 證明：⊢ [(∃x)Fx ⊃ (∃x)Gx] ⊃ (∃x)(Fx ⊃ Gx)（使用外層 CP + 內層 IP）】
  | 1. (∃x)Fx ⊃ (∃x)Gx      AP
  | | 2. ~(∃x)(Fx ⊃ Gx)     AP (內層開啟 IP)
  | | 3. (x)~(Fx ⊃ Gx)      2 QN
  | | 4. ~(Fx ⊃ Gx)         3 UI
  | | 5. Fx · ~Gx           4 Impl, DeM, DN
  | | 6. Fx                 5 Simp
  | | 7. (∃x)Fx             6 EG
  | | 8. (∃x)Gx             1, 7 MP
  | | 9. ~Gx                5 Simp
  | | 10. (x)~Gx            9 UG (x 未在任何 EI 列或 AP 中自由出現，合法做 UG！)
  | | 11. ~(∃x)Gx           10 QN
  | | 12. (∃x)Gx · ~(∃x)Gx  8, 11 Conj (導出矛盾！)
  | 13. (∃x)(Fx ⊃ Gx)       2–12 IP
 14. [(∃x)Fx ⊃ (∃x)Gx] ⊃ (∃x)(Fx ⊃ Gx)  1–13 CP
```

---

## 二、 第二類：量詞移入與移出括弧定理（Q11 ～ Q22，設 $P$ 不含自由變元 $x$）

當複合句的一側是**不含變元 $x$ 的閉合語句 $P$**（如「橋會倒塌」）時，量詞可以自由移入或移出括弧；**唯獨當量詞進出「條件句的前件」時（Q17 與 Q18），全稱 $(x)$ 與存在 $(\exists x)$ 必須翻轉互換**！

| 定理編號 | 述詞邏輯量詞移位定理（$P$ 不含自由變元 $x$） | 量詞是否翻轉？ |
| :---: | :--- | :---: |
| **Q11** | $\vdash (x)(P \cdot Gx) \ \equiv \ [P \cdot (x)Gx]$ （對稱形式為 Ex 10-12 第 11 題） | 不翻轉（雙向等值） |
| **Q12** | $\vdash (\exists x)(P \cdot Gx) \ \equiv \ [P \cdot (\exists x)Gx]$ | 不翻轉（雙向等值） |
| **Q13** | $\vdash (x)(P \lor Gx) \ \equiv \ [P \lor (x)Gx]$ | 不翻轉（雙向等值） |
| **Q14** | $\vdash (\exists x)(P \lor Gx) \ \equiv \ [P \lor (\exists x)Gx]$ （即 Ex 10-12 第 15 題） | 不翻轉（雙向等值） |
| **Q15** | $\vdash (x)(P \supset Gx) \ \equiv \ [P \supset (x)Gx]$ （量詞在條件句**後件**） | 不翻轉（雙向等值） |
| **Q16** | $\vdash (\exists x)(P \supset Gx) \ \equiv \ [P \supset (\exists x)Gx]$ （量詞在條件句**後件**） | 不翻轉（雙向等值） |
| **⭐ Q17** | **$\vdash (x)(Fx \supset P) \ \equiv \ [(\exists x)Fx \supset P]$** （量詞在**前件**：任何人移動橋就倒！Ex 10-12 第 13 題） | **🔄 $(x) \leftrightarrow (\exists x)$ 翻轉！** |
| **⭐ Q18** | **$\vdash (\exists x)(Fx \supset P) \ \equiv \ [(x)Fx \supset P]$** （量詞在**前件**：所有人移動橋才倒！） | **🔄 $(\exists x) \leftrightarrow (x)$ 翻轉！** |
| **Q19** | $\vdash (x)(Fx \equiv P) \ \supset \ [(x)Fx \equiv P]$ | 單向蘊含 |
| **Q20** | $\vdash (x)(Fx \equiv P) \ \supset \ [(\exists x)Fx \equiv P]$ | 單向蘊含 |
| **Q21** | $\vdash [(x)Fx \equiv P] \ \supset \ (\exists x)(Fx \equiv P)$ | 單向蘊含 |
| **Q22** | $\vdash [(\exists x)Fx \equiv P] \ \supset \ (\exists x)(Fx \equiv P)$ （附錄二 25 步經典 CD 證明） | 單向蘊含 |

### 💡 Q17（橋倒定理，Ex 10-12 第 13 題）雙向等值完整證明
```text
  | 1. (x)(Fx ⊃ P)          AP         (第一段 CP：證左至右)
  | | 2. (∃x)Fx             AP
  | | 3. Fx                 2 EI
  | | 4. Fx ⊃ P             1 UI
  | | 5. P                  3, 4 MP
  | 6. (∃x)Fx ⊃ P           2–5 CP
  7. (x)(Fx ⊃ P) ⊃ [(∃x)Fx ⊃ P]  1–6 CP
  | 8. (∃x)Fx ⊃ P           AP         (第二段 CP：證右至左)
  | | 9. Fx                 AP         (假設 Fx 以證 Fx ⊃ P)
  | | 10. (∃x)Fx            9 EG
  | | 11. P                 8, 10 MP
  | 12. Fx ⊃ P              9–11 CP    (消去第 9 列 AP，x 成功解毒！)
  | 13. (x)(Fx ⊃ P)         12 UG      (對已解毒的 x 合法做 UG！)
 14. [(∃x)Fx ⊃ P] ⊃ (x)(Fx ⊃ P)  8–13 CP
 15. {(x)(Fx ⊃ P) ⊃ [(∃x)Fx ⊃ P]} · {[(∃x)Fx ⊃ P] ⊃ (x)(Fx ⊃ P)}  7, 14 Conj
 16. (x)(Fx ⊃ P) ≡ [(∃x)Fx ⊃ P]  15 Equiv (Q.E.D.)
```

---

## 三、 第三類：非空論域定理、拘束變元改名與德摩根推廣（Q23 ～ Q33）

| 定理編號 | 述詞邏輯定理標準公式 | 核心邏輯意義 |
| :---: | :--- | :--- |
| **Q23** | $\vdash (\exists x)[(\exists x)Fx \supset Fx]$ | 內外同名量詞以最內層拘束為準，等價於 $(\exists x)Fx \supset (\exists x)Fx$ |
| **Q24** | $\vdash (\exists x)[Fx \supset (x)Fx]$ （著名的**飲酒者定理 Drinker Paradox**！） | 在任何非空酒吧裡，都存在一個人 $x$，使得「如果 $x$ 喝酒，則所有人都在喝酒」！ |
| **Q25** | $\vdash (x)Fx \ \equiv \ (y)Fy$ | 全稱拘束變元換名等值 |
| **Q26** | $\vdash (\exists x)Fx \ \equiv \ (\exists y)Fy$ （即 Ex 10-12 第 3 題） | 存在拘束變元換名等值 |
| **Q27** | $\vdash (x)Fx \ \supset \ (\exists x)Fx$ （反之不然！） | 現代邏輯預設**論域 $D$ 非空**（至少有 1 個個體），故全稱 $(x)Fx$ 可推得 $(\exists x)Fx$（注意：此非定言 A 命題 $(x)(Sx \supset Px)$！） |
| **Q28** | $\vdash (x)[Fx \supset (Gx \lor Hx)] \ \supset \ [(x)(Fx \supset Gx) \lor (\exists x)(Fx \cdot Hx)]$ | 附錄二 20 步 IP 證明 |
| **Q29** | $\vdash \sim(x)(Fx \supset \sim Gx) \ \equiv \ (\exists x)(Fx \cdot Gx)$ | 對當方陣 **E 命題的否定 $\equiv$ I 命題**（17 步證明） |
| **Q30** | $\vdash \sim(\exists x)(Fx \cdot \sim Gx) \ \equiv \ (x)(Fx \supset Gx)$ | 對當方陣 **O 命題的否定 $\equiv$ A 命題** |
| **Q31** | $\vdash (x)Fx \ \equiv \ (x)(y)(Fx \cdot Fy)$ | 單量詞擴展為雙量詞連言（15 步證明） |
| **Q32** | $\vdash [(\exists x)Fx \cdot (\exists x)Gx] \ \supset \ \{[(x)(Fx \supset Hx) \cdot (x)(Gx \supset Jx)] \equiv (x)(y)[(Fx \cdot Gy) \supset (Hx \cdot Jy)]\}$ | 附錄二 42 步大型定理證明 |
| **Q33** | $\vdash \{[(\exists x)Fx \equiv (\exists x)Gx] \cdot (x)(y)[(Fx \cdot Gy) \supset (Hx \equiv Jy)]\} \ \supset \ [(x)(Fx \supset Hx) \equiv (x)(Gx \supset Jx)]$ | 附錄二 40 步大型定理證明 |

### 💡 Q24（飲酒者定理 Drinker Paradox）10 步 IP 驚艷證明
```text
  | 1. ~(∃x)[Fx ⊃ (x)Fx]     AP         (開啟 IP 假設結論的否定)
  | 2. (x)~[Fx ⊃ (x)Fx]      1 QN
  | 3. ~[Fx ⊃ (x)Fx]         2 UI
  | 4. ~[~Fx ∨ (x)Fx]        3 Impl
  | 5. Fx · ~(x)Fx           4 DeM, DN
  | 6. Fx                    5 Simp     (注意：此處 x 是由第 3 列 UI 產生，完全沒有經過 EI！)
  | 7. (x)Fx                 6 UG       (因此對第 6 列 Fx 竟然可以合法做 UG 得 (x)Fx！)
  | 8. ~(x)Fx                5 Simp
  | 9. (x)Fx · ~(x)Fx        7, 8 Conj  (與第 8 列形成直接矛盾！)
 10. (∃x)[Fx ⊃ (x)Fx]        1–9 IP     (定理得證！ Q.E.D.)
```

---

## 四、 第四類：多重量詞順序交換與關係述詞定理（Q34 ～ Q55）

- **核心鐵律**：
  1. **同種量詞相鄰（皆全稱 $(x)(y)$ 或皆存在 $(\exists x)(\exists y)$）可以自由雙向交換順序（Q36, Q38）**！
  2. **異種量詞相鄰：由「存在在前、全稱在後 $(\exists x)(y)Fxy$」可以單向推導出「全稱在前、存在在後 $(y)(\exists x)Fxy$」（Q39），但絕對不可逆推**！（「有某一個人被所有人愛」可以推出「每個人都有所愛的人」；但「每個人都有所愛的人」推不出「有某人被所有人愛」！）。

| 定理編號 | 多重量詞與關係述詞定理公式 | 核心性質說明 |
| :---: | :--- | :--- |
| **Q34 & Q35** | $\vdash (x)(y)Fxy \equiv \sim(\exists x)(\exists y)\sim Fxy$ ； $\vdash (\exists x)(\exists y)(\exists z)Fxyz \equiv \sim(x)(y)(z)\sim Fxyz$ | 多層量詞否定 (QN) |
| **Q36** | $\vdash (x)(y)Fxy \ \equiv \ (y)(x)Fxy$ （即 Ex 10-12 第 1 題） | 雙全稱量詞交換順序雙向等值 |
| **Q37** | $\vdash (x)(y)Fxy \ \equiv \ (y)(x)Fyx$ | 雙全稱量詞同時調換變元位置等值 |
| **Q38** | $\vdash (\exists x)(\exists y)Fxy \ \equiv \ (\exists y)(\exists x)Fxy$ | 雙存在量詞交換順序雙向等值 |
| **⭐ Q39** | **$\vdash (\exists x)(y)Fxy \ \supset \ (y)(\exists x)Fxy$ （反之不然！）** | **先 $\exists$ 後 $\forall$ $\implies$ 先 $\forall$ 後 $\exists$（單向！）** |
| **Q40 ~ Q42** | $\vdash (x)(y)Fxy \supset (x)(y)(Fxy \lor Fyx)$ ； $\vdash (y)(\exists x)(Fxy \supset Fxx)$ ；<br>$\vdash (z)(\exists y)(x)[Fxy \supset (Fxz \cdot Fxx)] \supset (z)(x)Fxz$ | 二元關係反身性衍生定理 |
| **Q43 & Q44** | $\vdash (y)(\exists x)(Fx \equiv Fy) \ \equiv \ [(\exists x)Fx \cdot (\exists x)\sim Fx]$ （當關係改為 $\sim(Fx \equiv Fy)$ 時，即論域既有 $F$ 也有非 $F$） | 附錄二 44 步雙向證明 |
| **Q46** | $\vdash [(\exists x)Fx \supset (x)Gx] \ \equiv \ (x)(y)(Fx \supset Gy)$ | 前束範式雙全稱提取（31 步證明） |
| **Q48** | $\vdash \{(\exists x)Fx \supset [(\exists x)Gx \supset (x)Hx]\} \ \equiv \ (x)(y)(z)[(Fx \cdot Gy) \supset Hz]$ | 前束範式三全稱提取（30 步證明） |
| **Q51 & Q52** | $\vdash (\exists x)(y)(Fx \supset Gy) \ \equiv \ (y)(\exists x)(Fx \supset Gy)$ | 當二元式為**分離變元 $Fx \supset Gy$** 時，$(\exists x)(y)$ 與 $(y)(\exists x)$ 例外可雙向等值！ |
| **Q53 ~ Q55** | $\vdash (y)(\exists x)(Fx \lor Gy) \equiv (\exists x)(y)(Fx \lor Gy)$ ； $\vdash (y)(\exists x)(Fx \cdot Gy) \equiv (\exists x)(y)(Fx \cdot Gy)$ ；<br>$\vdash (x)(\exists y)(z)[(Fx \cdot Gy) \supset Hz] \equiv (\exists y)(z)(x)[(Fx \cdot Gy) \supset Hz]$ | 分離變元下的前束量詞自由交換 |

### 💡 Q39（$\vdash (\exists x)(y)Fxy \supset (y)(\exists x)Fxy$）6 步無懈可擊證明
```text
  | 1. (∃x)(y)Fxy            AP         (假設前件)
  | 2. (y)Fxy                1 EI       (先脫去外層 (∃x)，此時 x 是由 EI 引進的！)
  | 3. Fxy                   2 UI       (再脫去內層 (y)，注意：y 是由第 3 列 UI 引進，並未在任何 EI 列出現！)
  | 4. (∃x)Fxy               3 EG       (先把受 EI 限制的 x 用 EG 包起來消掉！此時第 4 列只剩純潔的自由變元 y！)
  | 5. (y)(∃x)Fxy            4 UG       (對未受任何 EI 汙染的 y 合法做 UG！)
  6. (∃x)(y)Fxy ⊃ (y)(∃x)Fxy 1–5 CP     (定理得證！ Q.E.D.)
```
