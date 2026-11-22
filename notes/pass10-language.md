# Pass 10 · 语言层（证据文件）

日期：2026-11-22。样本 12 篇：O 8（1924801、2116496、2215444、2516219、2504188、2107870、2401298、2300348）+ F 2（2522170、2401540）+ M 2（2308357、2504020）。
口径声明：计数为正则词形统计（pdftotext 文本），不是句法解析——时态计数统计目标动词的过去式/现在式词形，被动计数统计 `be + 过去分词` 搭配，均为量级指标。原定样本 2022-B-2200084 的存档 PDF 为纯图版（提取 0 字节），替换为 2022-D-2215444；该篇版式使标题锚定失败、"we" 动词几乎检不出，未进入逐节计数，只进全篇动词谱。双栏论文（2522170 等）的结论节锚定会串栏，结论句式以人工实看的 6 篇为准。

## 1. 时态：方法节现在时压倒性占优，但「我们」动词有两种方言

标题锚定的方法节（10 篇锚定成功）目标动词词形计数：

| 篇号 | 过去式词形 | 现在式词形 | 被动/千词 |
|---|---|---|---|
| 1924801 (O) | 74 | 309 | 3.0 |
| 2116496 (O) | 10 | 113 | 7.2 |
| 2516219 (O) | 7 | 27 | 1.3 |
| 2504188 (O) | 28 | 96 | 2.2 |
| 2107870 (O) | 11 | 15 | 7.4 |
| 2401298 (O) | 1 | 4 | 4.2 |
| 2300348 (O) | 21 | 35 | 2.0 |
| 2522170 (F) | 12 | 85 | 6.4 |
| 2401540 (F) | 30 | 66 | 3.5 |
| 2308357 (M) | 21 | 80 | 4.6 |
| **合计** | **215** | **910** | 1.3–7.4 |

方法节现在式∶过去式 ≈ **4∶1**——模型陈述用现在时是主流语法（"The framework employs…", "we propose…", "X is defined as…"）。

但限定到主语为 we 的承重动词时，全篇合计 we+现在 131 vs we+过去 108，接近平分，呈**两种方言**：
- **现在时方言**（多数）：2116496 we+现在 26∶过去 1；2401298 17∶5；2308357 15∶5；2504020 11∶4——"we propose / develop / construct" 贯穿全篇。
- **过去时叙事方言**（少数但同样拿 O）：2300348 we+过去 38∶现在 8；2107870 16∶5——"we formulated / produced / modeled" 把全篇写成已完成的研究报告。两篇均为美国队风格。
结论节两种时态都合法：1924801 用过去时复盘（"we designed a highly interpretable two-part model…"），2116496/2401298 用现在时复盘（"we design models…", "we establish our momentum predictor through a two-step process"）。**时态不构成奖级信号，篇内一致即可**；混用（同段内 propose/proposed 乱跳）才是真扣分项，但本样本无法量化混用率，只作判断。

## 2. 语态：主动为主，被动是配角

方法节被动搭配密度 1.3–7.4 次/千词，中位约 3.5/千词——按平均句长折算约每 15–25 句才出现 1 次典型被动。被动集中在三类固定搭配：定义（"X is defined as…", "is denoted by"）、数据处理（"data are collected / normalized"）、模型指称（"the model is constructed / is employed to"）。作者动作本身几乎全用主动 we 句。
变体：2516219（O）近乎无 "we"（we 动词仅 2 次检出），全篇用「模型/框架作主语」的非人称现在时（"a fuzzy comprehensive evaluation model is developed to quantify…", "a multimodal network model is proposed to evaluate…"）——被动密度反而最低（1.3/千词），因为它用的是主动非人称句（"The framework employs entropy-weighted aggregation…"）。即存在第三种合法声部：**模型主语主动句**。

## 3. 承重动词谱（11 篇全篇合计，词形归并）

use 236 ≫ based on（base 词形，绝大多数是 "based on / base on"）170 > calculate 94 > obtain 79 > optimize 44 > develop 37 > simulate 32 > construct 31 > introduce 30 > present 26 ≈ establish 26 > conduct 25 > propose 22 ≈ evaluate 22 > describe 21 > design 20 > employ 14 ≈ integrate 14。

解读：真正的高频是**操作动词**（use/calculate/obtain）与**衔接性结构**（based on）；自我标榜型的 propose/develop/construct/establish 合计约 116 次、篇均约 10 次，密度并不高——每节出现 1–2 次即可，多了像广告。employ/utilize 是 use 的正式变体（篇均 1–4 次，点缀用）。F/M 与 O 的动词谱无系统差异（2522170 的 use 高达 42 次为全样本最高，属个人习惯非奖级特征）。

## 4. 衔接词谱（11 篇合计，句首/分句首检出）

however 58 ≫ therefore 42 > finally 21 > thus 20 > additionally 18 > for example 16 > in addition 13 > as a result 11 > specifically 9 > in particular 8 ≈ moreover 8 > furthermore 6 > in fact 5 ≈ subsequently 5 ≈ consequently 5 > nevertheless / in contrast / on the other hand 各 ≤3。

结构：转折（however）+ 因果（therefore/thus/as a result/consequently 合计 78）是两大主力；递进堆叠词（moreover/furthermore/additionally/in addition 合计 45）存在但不滥用——**moreover+furthermore 合计仅 14 次、篇均约 1.3 次**，与中文学术英语爱堆 moreover 的习惯相反。例证词（for example/for instance）篇均约 1.5 次。序数词（first/second/finally）主要出现在步骤枚举与信件正文。

## 5. 结论句式实看（6 篇原文）

1. **复盘开场式**："In our paper, we designed a highly interpretable two-part model that is able to accurately evaluate…"（1924801）——In our paper/In this paper + 一句话重述模型 + 自评形容词（highly interpretable）。
2. **步骤枚举式**："We develop our modelling in four steps: Forecast…, Decision…, Deployment…, Design…"（2116496）——冒号后把全文骨架列一遍，后文逐step一句结论。
3. **利益相关方落点式**："In this paper we formulated a model that the Washington State Department of Agriculture can apply to prioritize…"（2107870）——复盘句直接点名谁能用、用它干什么。
4. **过程重述式**："In this paper, we establish our momentum predictor through a two-step process. Initially, we develop… Subsequently, the residual … is utilized as the label…"（2401298）——现在时 + Initially/Subsequently 串两步。
5. **局部结论句**（无独立复盘段时的替代）："Therefore, we conclude that the score of words does not…" / "it is reasonable to conclude that…"（2300348）——we conclude that / it is reasonable to conclude that 是每问末尾的收口句式。
6. **评价式收束**："In conclusion, the WLPCM model represents a strategic and proactive approach to addressing…"（2401540，memo 内）——In conclusion, + 模型名 + represents/is + 评价性名词短语。

共同点：结论节首句必含**模型自指**（we / our model / 模型名），且几乎都带一个自评或落点（形容词、应用者、或关键数字）；纯目录式复述（只列做了什么、无评价无数字）在本样本未见于 O 篇。

## 6. 本节结论（供专册）

1. 时态规则一句话：方法节现在时为默认（≈4∶1），过去时叙事是合法变体但须全篇一致；结论节首句用 "In this paper, we propose/establish/formulated…" 复盘式开场。
2. 语态配比：主动 we 句（或模型主语句）为骨架，被动只留给定义、数据处理、模型指称三类固定搭配，密度约 3–4 次/千词即够。
3. 动词与衔接词都是「少量高频」结构：承重动词每节 1–2 次、moreover/furthermore 全篇个位数、however+therefore 承担绝大部分逻辑转接——照谱配给，别自创花样。
