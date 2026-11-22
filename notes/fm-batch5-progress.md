# F/M 第五批进度（换思路广撒网，2026-11-22）

- 核实标准不变：候选 PDF 首页队号对 `notes/comap_lookup.json`（92,247 条）年份/题号/奖项/学校一致才入库。
- 开工前库内：F 16 + M 11 = 27 篇。

## 渠道命中台账（进行中）

| 渠道 | 结果 |
|---|---|
| HuggingFace Datasets | 搜 MCM/ICM/COMAP/美赛/math modeling 等：命中 IDEA-FinAI/Mathematical_Modeling_Speciale_Dataset_v0.1（含 MCM 1995–2025 论文集，Markdown 转换版）。逐年逐题枚举其 2022–2025 全部 159 个队号文件夹核对官方表：137 Outstanding + 22 不在官方表（应为赛题/说明文件），**F/M = 0**——与 ModelScope BAO 同源的 O 奖集。另 shcherbakuska/Math_Modeling（语料 CSV）、Beifengdo/Mathematical-Modeling（课程作业）均非论文。命中 0。 |
| ModelScope 其他数据集 | BAO 已由前批证伪（仅 O）；本批未发现其他美赛论文集。命中 0。 |
| grep.app | API 被 Vercel 安全检查拦截（返回验证页），无法使用。命中 0（渠道不可达）。 |
| Sourcegraph 公开代码搜索 | `"Team Control Number"` 全网搜：52 个文件命中、18 个仓，逐一核路径——全部为模板/工具（mcmthesis、easymcm、各类 Agent 模板）与已知 O 奖集（dick20、personqianduixue、HBdingdang 的 2021 M 源文件）。无 2022–2025 F/M 全文。命中 0。 |
| arXiv | 系统搜 "Mathematical Contest in Modeling" / "MCM/ICM" / "Meritorious Winner" + 各年赛题关键词（Wordle、Juneau、Great Lakes、lamprey 等），共检 ~15 篇候选，逐篇验队号：详见下节。暂命中 0（1 篇待定性，见下）。 |
| Semantic Scholar / OpenAlex | 关键词检索无美赛参赛论文全文（S2 返回空、OpenAlex 无相关条目）。命中 0。 |
| Zenodo / archive.org | 各命中个位数，均非美赛 F/M 论文。命中 0。 |
| 校苑数模 / 人人文库 | 搜到的均为 2019 及更早 O 奖论文（如 2019-E-1916777）与赛题汇编，无 2022–2025 F/M。命中 0。 |
| 高校课程资源页 | 宽泛检索多为赛题汇编与 O 奖旧文，无 2022–2025 F/M 全文。命中 0。 |
| 个人博客/经验贴（知乎引流） | 知乎经验贴检索命中福州大学 2025-A F 奖队伍博客（blog.attilio.cc），附录直挂论文 PDF，队号 2522170 核实为 Finalist → **入库 1**。 |
| searchcode API | 返回非 JSON（服务异常），不可用。命中 0。 |
| HBdingdang/math-model（Sourcegraph 顺藤） | 全树 31,676 条逐查：「2-2 美赛 M 奖论文」止于 2021 年、「2-2 收集的美赛代码」只有 2019–2021 的 M/F 条目、按模型整理夹无 2022–2025 PDF。命中 0（再次证实公开合集 F/M 止于 2021）。 |

## arXiv 候选逐篇核验

| arXiv | 内容 | 核验结果 |
|---|---|---|
| 2511.14288 | 中南大学 2025-B 朱诺旅游（自述 Meritorious Winner） | 论文正文与 arXiv comment 均自述 2025 ICM B、M 奖、中南大学；官方表 2025-B 中南大学 M 队有两支（2519248、2524167），正文无队号、无从区分 → **按纪律不入库**（奖级/学校/年份/题号四项吻合，仅队号不可判）。 |
| 2407.08184 | 多波束测线 | 正文自述 2023 **国赛** B 题，非美赛，弃。 |
| 2309.14250 | Wordle 预测 | 首页队号 2321232 → 官方表为 2023-C **Successful Participant**（RPI），弃（再次实证必须验号）。 |
| 2403.19433 / 2305.03502 | Wordle 预测 | 全文无队号、无奖级自述，不可核实，弃。 |
| 2504.04761 | 大湖水位 | 已由第三批入库（2024-D-2401540，复旦 F），不重复。 |

## 已入库（本批）
| 队号 | 年-题 | 奖 | 学校 | 渠道 |
|---|---|---|---|---|
| 2522170 | 2025-A | F | Fuzhou University | 队员博客 blog.attilio.cc 附录直链 PDF（知乎经验贴检索顺藤） |
