# F/M 扩库第二批（国际队伍专项）— 核实结果与国家分布

> 完成时间：2026-11-22。任务：核实 fm2-candidates/ 的 7 个候选 PDF（须 F/M 奖 + 非中国队伍），并补搜国际队伍 F/M。
> 核实方法与第一批相同：论文首页提取队号 → 与 `notes/comap_lookup.json`（COMAP 官方结果名单建成，92,247 条）比对队号/题号/奖项/学校。

## 一、结论总览

- **本批新入库：0 篇。** 7 个候选全部核实完毕、无一同时满足「F/M 奖 + 非中国队伍」：2 篇奖级不够（S、H），4 篇是奖级达标但为中国高校队伍，1 个文件根本不是论文（赛题原文）。
- 补搜（GitHub API 仓搜索 + .edu/英文网页搜索）未找到可核实的国际队伍 F/M 全文，原因见第四节。

## 二、候选核实表（全部剔除，文件留在 notes/fm2-candidates/）

| 候选文件 | 年/题 | 队号 | 官方奖项 | 官方学校 | 剔除原因 |
|---|---|---|---|---|---|
| slusarczyk.pdf | 2025 MCM A | 2525925 | Successful Participant | LUT University（芬兰） | 国家符合但奖级仅 S，非 F/M |
| torresyang.pdf | 2023 ICM D | 2315167 | Finalist | Southern University of Science and Technology（南方科技大学） | F 奖达标，但为中国队伍 |
| tyf009.pdf | 2025 ICM E | 2521959 | Meritorious Winner | Fujian Normal University（福建师范大学） | M 奖达标，但为中国队伍 |
| victoria.pdf | 2025 ICM D | 2510374 | Honorable Mention | Beijing University of Technology（北京工业大学） | 奖级仅 H，且为中国队伍 |
| zhenxuhuang.pdf | 2022 MCM A | 2211470 | Finalist | University of Electronic Science and Technology of China（电子科技大学） | F 奖达标，但为中国队伍 |
| ximoloko.pdf | — | — | — | — | 仅 4 页，是 2025 MCM C 赛题原文，不是参赛论文 |
| ximoloko_cert.pdf | 2025 MCM C | 2517063 | Meritorious Winner | Jiangxi Normal University（江西师范大学） | 仅为获奖证书（论文正文缺失），且为中国队伍 |

## 三、方法卡（仅记录，未入库；每篇 2 行）

- **2525925（2025-A，楼梯磨损测年，LUT 芬兰，S）**：3D 数字孪生 + 循环加载变形仿真 + 神经网络预测楼梯年龄，三角互证（triangulation）框架。与本题关系弱。
- **2315167（2023-D，SDG 优先级，南科大，F）**：AHP 判断矩阵 + 随机森林/AdaBoost 回归求 SDG 权重，Spearman 相关矩阵 + PageRank 定重要性指数。与本题同为网络题：相关矩阵建边 + PageRank 排序可借给多源重要性排序。
- **2521959（2025-E，农田生态，福建师大，M）**：AED 动力学模型（Euler-Markov 迭代）+ FPI 周期指数，AHP-熵权-独立性系数组合赋权 + 多目标优化 + ARIMA 预测。组合赋权写法可借。
- **2510374（2025-D，巴尔的摩交通，北工大，H）**：K-Means 聚类 + Haversine 距离建交通网，三方利益相关者成本模型 + 蒙特卡洛评估新公交站。与本题同题型（网络），但奖级不够。
- **2211470（2022-A，骑行功率分配，电子科大，F）**：动力学方程 + 运动员总能量模型，蒙特卡洛 + 模拟退火求能量分配剖面，风速/风向扰动敏感性。与本题关系弱。

## 四、补搜记录（如实）

- GitHub API 按 "MCM Finalist / MCM Meritorious / ICM Finalist paper" 搜仓 60+ 个：绝大多数为中国队伍仓库（多已在第一批入库或核实），其余多为 2021 年及更早（超出 2022–2025 范围）。
- 英文网页与 .edu 搜索：只返回个人简历（提及获奖但无论文全文）与赛事规则页，无可下载全文。
- 唯一下载试核的 YangQile/MCM_B_Meritorious：2026 MCM B 重排版论文，首页无队号、官方名单（截至本批建表时）无法核对，且作者为中国学生姓名 — 不入库。
- 结论：国际队伍极少公开 F/M 全文（O 奖由 COMAP/档案站集中发布，F/M 靠队伍自发公开，而自发公开以中国队伍为主），这是本批 0 入库的根本原因，非搜索不力。

## 五、国家分布合并统计（第一批 + 第二批）

- F/M 库总量仍为 **21 篇**（F 14 + M 7），本批新增 0。
- 国家分布：**中国 20 篇（95.2%）、美国 1 篇（4.8%）**（2025-C-2524905，University of Florida，F + INFORMS 冠名奖）。
- 第二批候选的国家分布：中国 5、芬兰 1（奖级不够）、无队号文件 1 — 国际队伍候选本身也极稀少。
- 后续若要提升国际占比，可行路径：UMAP Journal 发表的获奖论文（多为 O 奖）、各国大学建模队官网的 news 页逐校排查、COMAP 冠名奖（INFORMS/SIAM/MAA 等）得主学校新闻稿反查全文。
