# Pass 9 · 交付物与附录格式（证据文件）

日期：2026-11-22。样本：全库 230 篇全文扫描（pdftotext -layout）+ 20 篇细看。
口径声明：附录/Memo 的全库计数是**标题行检测的下限**——检测式为行首 `Appendix/Appendices`、`Memorandum/Memo` 标题行、`Dear …` 敬称、`To:/From:` 块。两个已知的计数污染：①2024–2025 的「Report on Use of AI」会整段引用 ChatGPT 给的 memo 模板（含 "To: The recipient(s) of the memo."），使 memo 检出虚高；②少数论文附录无标题行或标题被版式打散，检不出。故全库比率只作量级参考，格式结论以 20 篇细看的实锤为准。

## 1. 全库扫描（n=230）

| 形态 | 检出 | 比率 |
|---|---|---|
| 有 Appendix 标题 | 42/230 | 18% |
| 附录中含代码迹象 | 21/230（占附录篇 50%） | 9% |
| 附录中含补充数据表迹象 | 4/230 | 2%（检测弱，细看实际更高） |
| 附录中含证明/推导迹象 | 1/230 | <1% |
| Memo/Letter 检出（含污染） | 39–43/230 | ≈17% |
| 含 "summary sheet" 字样（多为第 1 页 COMAP 页眉） | 181/230 | 79% |
| "Report on Use of AI" 标题 | 2024: 16/46；2025: 21/61；2023 及以前 0 | 见 §5 |

按奖级：附录率 O 16%（30/184）、F 26%（6/23）、M 19%（4/21）、H 2/2。按题型：附录率 D 29% 最高、E 9% 最低；Memo/Letter 检出 B/C/F 约 28–30%、A/E 约 3%——与「题目是否要求给利益相关方写信/备忘录」的分布一致（见 §4）。附录篇幅：检出篇的附录段中位约 2 页、最长约 6 页（页数为版面估算）。

与 pass4 旧数对照：pass4 在 72 篇 O 奖框内记附录 9/72≈12.5%，本遍全库 18%（O 子集 16%），同框可比、互相印证：**附录是少数派形态，不是标配**。

## 2. 附录内容构成（细看实锤）

附录一律位于 **References 之后**（1924801：References 在正文第 1106 行、Appendix A 在 1150 行；其余细看篇同序）。内容构成按出现频次：

1. **代码清单（最主流）**。标题常直名 "Appendix: Code"（2006782 O、2401132 M）、"Appendix 2 —— Code"（2104673 O）、"Appendices: Core Code of LSTM"（2416613 F，带行号的 Python 源码）、R 代码（2003723 O）、MATLAB 代码（2013140 O 附录末尾 "Programs:" 段；2315379 O 的 Appendix 3 是 Dijkstra 的 MATLAB 实现，代码与注释双栏排版）。
2. **补充数据/结果表**。1924801（O）：Appendix A 只放一张边权数据表（Local Section Model 算出的边容量，喂给 Global Flow Model）——正文放不下的**模型输入数据**。2215557（F）：附录是逐月交易模拟日志全文——正文只给汇总、附录给**全量结果**。2315379（O）：正文注 "Specific data values are detailed in the Appendix"。
3. **补充推导/解释**。2224021（O）：Appendix A/B 放 Cobb-Douglas 估计与需求函数的推导细节；保留了模板的 "First appendix / Second appendix" 占位式标题（模板痕迹未清，见 §6 反面）。
4. **伪代码**。2425559（H）：Appendices 放 Monte Carlo 的 Algorithm 1 完整伪代码——算法太长不进正文时的去处。
5. **证明（极罕见）**。2508861（O）：Appendices 是 "Proof 1" + Lemma 1/2 的完整证明，全库仅此一例检出。美赛附录基本不承担证明功能。

## 3. 20 篇细看登记表

| 篇号 | 奖 | 附录 | Memo/Letter | Summary Sheet / 其他交付物 |
|---|---|---|---|---|
| 2019-D-1924801 | O | A：边权数据表 1 张 | 无 | 官方表格页（T1–F4 办公室栏 + 说明文字），正文另有 "Summary of Policy Recommendations" 节 |
| 2020-D-2006782 | O | "Appendix: Code" | 无 | — |
| 2020-D-2013140 | O | 判断矩阵全量 + MATLAB 程序 | 无 | — |
| 2020-D-2003723 | O | 网络汇总 + R 代码 | 无 | — |
| 2021-B-2104673 | O | "Appendix 2 —— Code" | 无 | — |
| 2022-F-2224021 | O | A/B：推导细节（模板标题未清） | 无 | — |
| 2023-B-2315379 | O | Appendix 3：Dijkstra 代码 | 无 | — |
| 2025-E-2508861 | O | Appendices：证明+引理 | 无 | 含 AI 使用报告 |
| 2024-C-2416613 | F | Appendices：LSTM 核心代码 | 无 | 含 AI 使用报告 |
| 2025-A-2524491 | F | 代码（经 AI 报告转述） | 无 | AI 报告整段粘贴，含与建模无关的 LaTeX 提问（反面，§6） |
| 2022-C-2215557 | F | 逐月交易模拟日志 | 无 | — |
| 2022-C-2205329 | F | 有（代码迹象） | **Memo "To: Trader"**，在 References 之前 | Summary 第 1 页 + Keywords 页脚 |
| 2024-D-2401540 | F | 无独立附录 | **Memo 致 IJC**，在 References 之后、独立页 | 末尾 "Report on Use of AI"（Query/Output 体） |
| 2023-C-2308357 | M | 无 | **Letter 致 NYT Puzzle Editor**，正文末、References 之前 | Summary 第 1 页 + Keywords 页脚 |
| 2025-D-2504020 | M | 无 | **Letter "Dear Mayor,"**，在 References 之后 | — |
| 2024-A-2401132 | M | "Appendix: Code" | 无 | — |
| 2022-D-2209617 | M | 有（正文指路 "see the appendix"，模拟程序） | 无 | — |
| 2024-D-2425559 | H | Appendices：MC 伪代码 | 无 | — |
| 2025-D-2516219 | O | 无 | 无 | Summary Sheet 为第 1 页，Keywords 在第 1 页末（line 59） |
| 2025-D-2510374 | H | 有 | 无 | 含 ChatGPT 提及 |

## 4. Memo / Letter：何时出现、什么格式

**出现条件 = 题目要求**。四个实锤的收信人全是题目设定的利益相关方：交易员（2022-C）、纽约时报 Puzzle Editor（2023-C）、国际联合委员会 IJC（2024-D）、市长（2025-D）。题目不要求时基本不自发写（A/E 题检出率 ≈3%）。

**格式解剖**（2401540 与 2308357 两件全文实看）：
- 页眉块：`To: …` / `From: Team #XXXXXXX` / `Date: …` / `Subject: …` 四行（memo 式，2401540）；或标题 "Letter" + `To:` / `Date:` / `Subject:` 三行 + `Dear Mr. Editor:` 敬称（letter 式，2308357）。共同点：**Subject 行直接写模型名+任务**（"WLPCM model: A DDE-MPC approach to optimize management of the Great Lakes"）。
- 正文 = **把全文按任务顺序用非技术语言重走一遍**，每问一段、嵌 headline 数字：2401540 嵌 54.62% / 2.55% 两个改进率；2308357 按 First of all / Secondly / Then / Finally 走完四问，嵌 14,869 预测值、EERIE 四星结论，并配 1 张小图（"as shown on the right"）。
- 收尾：`Sincerely, / Team #XXXXXXX` 或 `Sincerely yours`。
- 篇幅：**恰好 1 页**（2308357 在第 25/25 页；2401540 在第 26/26 页）。
- 位置：**全文最后 1–2 页**，References 之前（2205329、2308357）或之后（2401540、2504020）各半，无固定规矩；共同点是绝不进正文中间。

## 5. Summary Sheet 的呈现

- **Summary Sheet 就是论文第 1 页**，不是另附的文件：COMAP 页眉块（Problem Chosen / 年 MCM/ICM / Summary Sheet / Team Control Number）→ 标题 → "Summary" 标题 → 摘要正文 → **Keywords 行收尾在第 1 页内**（2516219 Keywords 在文本第 59 行、2308357 第 40 行、2205329 第 38 行，均在第 1 页版面内）。
- 正文（第 2 页起 Introduction）**不重复摘要**：全文检索 "Summary" 标题行，细看篇均只出现 1 次（1924801 的第二次出现是正文的 "Summary of Policy Recommendations" 节，与摘要无关）。这与期刊论文「摘要+正文前再放一段」不同——美赛摘要只出现一次，Summary Sheet 与正文 Summary 是**同一文本、同一位置**，不存在两个版本。
- 旧格式（2019）：官方表格页带 "For office use only T1–F4" 栏与说明文字（"Type a summary of your results on this page…"），2020 后简化为页眉块。
- 例外：2401540 的存档版来自 arXiv，第 1 页是作者名+日期的期刊式排版、无 COMAP 页眉——是存档渠道差异，不是投稿形态。

## 6. 2024 起的新交付物：Report on Use of AI

- 2023 及以前 0 篇；2024 年 16/46、2025 年 21/61 带 "Report on Use of AI" 标题（另有若干篇以其他措辞披露 AI 使用，全库提及 ChatGPT/AI 工具的 2024–2025 篇约 45 篇）。
- 位置：**全文最末**（在 Memo/附录之后，2401540 为第 27 页，论文标注 26 页正文之外）。
- 格式：编号列出工具与版本（"1. OpenAI ChatGPT 4"），每条 `Query:` + `Output:` 摘录——即逐条交代问了什么、用了什么输出。
- 反面实锤：2524491（F）把 AI 报告整段粘贴，连"如何在 LaTeX 附录里放 Python 代码"这种与建模无关的提问都原样保留；2519935（O，深读轮已记）附录整段粘贴 AI 问答原文。披露义务 ≠ 原样倾倒，Output 应摘录与建模相关的部分。

## 7. 本节结论（供专册）

1. 非正文交付物是「题目驱动」的：附录 18% 是少数派、Memo/Letter 只在题目要求时出现、Summary Sheet=第 1 页且全文只出现一次——没有哪一种是无条件标配。
2. 附录的实际功能排序：代码清单 > 补充数据/全量结果表 > 补充推导 > 长伪代码 > 证明（近乎绝迹）；位置恒在 References 之后，中位约 2 页。
3. 2024 起新增固定尾件「Report on Use of AI」（Query/Output 体、全文最末），与 Memo 同为 1 页级短件；两者的共同格式 DNA 是：页眉/编号交代身份、正文只放结论级信息。
