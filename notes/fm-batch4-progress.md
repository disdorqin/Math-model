# F/M 第四批进度（高校逐校挖 + 仓库扩扫）

- 开工：2026-11-22。范围：2022–2025 F/M；核实标准与前批一致（队号对 notes/comap_lookup.json 的年份/题号/奖项/学校，≥8 页、%PDF 校验）。
- 与第三批分工：第三批 repos.json 的 872 仓不重复扫；本批用多方法（新关键词/话题/短语/队号/滚雪球/精选清单）发现新仓 + 高校逐校挖。
- 仓库扩扫目标：新扫 300+ 仓。高校线目标：40–60 所重点高校逐校三查（数学院官网 / 建模协会 / 校内文库与教师页）。
- 重要发现：共享对照表 comap_lookup.json 缺 2022 年 ICM D/E/F 三题名单（2022 只有 MCM A/B/C）；2022-ICM 候选若出现需另行补名单核实。

## 各发现法实测（持续更新）
| 方法 | 结果 |
|---|---|
| kw 新关键词（美赛 F奖/M奖/一等奖/获奖论文、COMAP Finalist、Mathematical Contest in Modeling 全称等） | 有效。repos4 累计已超 1000 仓（与第三批 872 仓去重后）；首个命中即来自 "COMAP Finalist" |
| topic 话题枚举（mcm/icm/mathematical-modeling/comap/math-modeling/mcm-icm） | 有效，量大（topic:mcm 155、topic:icm 150、topic:mathematical-modeling 528），逐页收录中 |
| name 年份词 in:name（mcm2025/icm2024 等） | 有效，每词 4–39 仓，多为单队仓 |
| phrase 短语搜 README | 有效（修正初判）：裸短语仓搜仅 2 仓，但 in:readme 变体很产——"Team Control Number" total=37（+26 新）、"Summary Sheet" MCM total=57（+36）、美赛 控制号 total=15（+8）、美赛 摘要 total=168（+103）。README 里引了论文结构件的仓值得扫 |
| teamnum 队号搜 | 弱（已实测）：裸队号搜已知 F 队仓（2209383）得 0；OR 批量只匹配到名字含数字串的无关仓（印度编号仓）。F 全量 + M 前 2400 号的 OR 批次已在后台跑，命中以收获核实为准 |
| code 代码搜 | 未认证 API 返回 401，不可用（如实记） |
| gitee 搜索 API | 不可用：未认证调用恒返回空数组（MCM/美赛/数学建模三词皆然），与第一批“Gitee 无成体系 F/M 仓”结论一致 |
| curated 精选清单外链 | 近乎无效：awesome-math-modeling + Math_Model 两清单共 132 条 GitHub 外链、95 条为新仓，但几乎全是国赛（CUMCM）工具/技能仓，无 2022–2025 美赛 F/M 论文仓 |
| snowball 滚雪球 | 待收获命中后执行（仓主其他仓/组织仓） |
| site: 搜索引擎站内查询 | 并入高校线记录（见下） |

## 仓库扩扫进度
- discover4.py（kw+name+topic+phrase）：**完成，新仓 1605 个**（目标 300+，与第三批 872 仓零重叠）。
- harvest4.py（zip→PDF→队号核对→入库）：双分片并行中（主片 554 仓快照 + B 片 repos4 第 550 号后 + extra_repos）。
- discover_num.py（队号 OR 批次）：首轮因 OR 超 5 个布尔算子被 API 422 全拒，已改 6 号一批 + in:readme 重跑（实测裸号搜=0、带 in:readme 能搜到已知 F 队仓，队号确实写在 README 里）；snowball.py 排在其后。
- 已命中 4 篇（见下表）。

## 高校逐校进度（官网/协会/文库/教师页）
已查 22 所（按官方 F/M 队数排序），**全文命中 0**（高校线收口；其余清单学校改由仓库线+队号搜覆盖同一批队员）：
- 西安电子科技大学（深挖）：教师主页平台（贾纪腾）挂有获奖附件，实测下载为**获奖证书 PDF**（2217425（M）.pdf 为证书），非论文全文；其余年份附件同制式。
- 上海交通大学、西安交通大学、北京航空航天大学、华中科技大学、电子科技大学、华南理工大学（仅名单：姓名+奖级，无论文）、武汉大学、重庆大学、哈尔滨工程大学、宁波大学、东南大学、中山大学、大连理工大学（创新创业学院有“获奖作品证书下载”，为证书且多为 2022 前）、西北工业大学、北京师范大学（含珠海校区名单）、南京大学、河海大学：均只有新闻/名单/认定文件，无论文全文下载。
- 补查 4 所同为零：上海大学（教师页有 2022 F 队名册，无论文）、杭州电子科技大学、南开大学、厦门大学（均为奖励名单/新闻）。
- 结论：高校官网线对 F/M 全文近乎零产出（与第二批国际线结论一致）；队员个人页/GitHub 才是全文来源，已由仓库线覆盖。

## 已入库（本批）
| 队号 | 年-题 | 奖 | 学校 | 渠道 |
|---|---|---|---|---|
| 2204128 | 2022-C | F | Donghua University | GitHub greerrrr5/2022COMAP-C-Finalist（kw: COMAP Finalist） |
| 2314669 | 2023-D | F | XIDIAN UNIVERSITY | GitHub LeslisXu/Finalist_Interdisciplinary-Contest-in-Modeling（kw: 全称） |
| 2204796 | 2022-A | M | Beihang University | GitHub RuBing-Yang/2022_A_bicycle（kw: 美赛 M奖） |
| 2510255 | 2025-E | M | Wuhan University | GitHub Xiong-z-x/agroecosystem-evolution-stability-model（topic: icm / mathematical-modeling） |
| 2404224 | 2024-E | M | Shanghai Lixin University of Accounting and Finance | GitHub b-bzy/distributed-pv-index-insurance（phrase: 美赛 摘要 in:readme） |
| 2201766 | 2022-A | F | Southeast University | GitHub changyuying/2201766-changyuying（teamnum: 仓名即队号，关键词法不可见） |
