# 精读卡 · 2025 MCM C 题（奥运奖牌预测）O 奖 18 篇

读法（2026-11-22）：pdftotext 全文提取后逐篇读 Summary + 目录 + 模型/检验章节。只记文中实有内容；提取不到的如实标注。
我们题目（借招对象）：1028 城强/弱连接资源共享网——问题1 单源失真约束最小成本、问题2 多源修正、问题3 随机失效应急。C 题为预测题，主要借不确定性量化、置信区间、概率型 headline、检验设计。

---

## 2500759 — Olympic Multi-dimensional Predictive Integrator
- **模型与算法**：PCA 降维去噪 + LSTM 时序特征 + 双通道 XGBoost-Bootstrap 预测（输出 95% CI），SHAP/主成分做项目重要性；教练效应用 DID（含平行趋势检验）。
- **检验/灵敏度**：专节 Sensitivity Analysis（主成分个数扰动）+ 10 折交叉验证 R² 图；非参数符号秩和检验识别突破国家。
- **作图风格**：图多且密（17 图）——小提琴-雨云混合图、Spearman 热力图、SHAP 瀑布/混合图为主，图题简短名词式。
- **Summary 亮点**：概率型 headline 扎堆：圣马力诺/科威特金牌突破概率 84.7%/68.4% 直接进摘要。
- **可借招**：Bootstrap 给每个预测配 CI 的做法可移植到问题3——失效重连成本也报区间不报单点。

## 2501869 — Medal Prediction Based on Tobit and Hurdle Models and Great Coach Effect Insights
- **模型与算法**：Hurdle-Tobit 融合（logit 两阶段解零膨胀 + Tobit 处理删失，引入 RCA 指数），与 RF/XGBoost 对比后按国家类型分工（Hurdle 管强国、Tobit 管弱国）；教练效应用贝叶斯变点检测 + 2SLS 因果回归。
- **检验/灵敏度**：灵敏度专节换一阶段分类器（RF/决策树/logit 轮换）看系数稳定性；模型选择用 MSE 与预测覆盖率对比表。
- **作图风格**：以对比图与热力图为主（四方法预测 vs 真实、RCA 热力图、变点类型图），图题多为完整描述句。
- **Summary 亮点**：按问题分段，每段先讲模型为何适配数据特征（离散、零膨胀、异质性），再给数字。
- **可借招**：「按对象类型分工用模型」——问题1 可按距离/失真余量把城市分层，长程用强连接逻辑、短程用弱连接逻辑，分别建模再拼。

## 2503389 — Olympic Medal Prediction Model Based on Regression and Machine Learning
- **模型与算法**：MLR-FNN Bootstrap 集成区间模型（多元线性回归 + 前馈神经网络加权融合）；首奖预测用 Logistic 回归–随机森林混合；自创 SIAMOS 项目战略重要性评估（PCA 定权）；教练效应用断点回归。
- **检验/灵敏度**：Monte Carlo 模拟验证首奖国数量（95% CI 1.00–8.00）；预测表带置信区间；有优缺点专节（正文未见独立灵敏度专节，以 MC + 区间代替）。
- **作图风格**：Sankey 奖牌流向图开篇抢眼，配相关矩阵、融合结构示意图与 MC 分布图。
- **Summary 亮点**：小标题式分段（Medal Forecasting: / First-Time Medalists: …），每个模型都起了名字，评委扫读友好。
- **可借招**：给子模型起品牌名（SIAMOS 式）——我们的问题2 融合规则也应命名并在 Summary 里一句话说清。

## 2505964 — 标题未提取（Summary 页文本未提取到，正文提取自第 2 页目录开始）
- **模型与算法**：运动员层随机森林二分类（MedalBinary / GoldBinary 两模型）聚合到国家奖牌数，§3.1.7 Monte Carlo 模拟与不确定性量化；后续 Random Forest（Task 2）、Poisson 回归（项目分析）、Great Coach 模型。
- **检验/灵敏度**：其「Sensitivity Analysis」实为分类召回率口径——用 ROC/PR/校准曲线逐折分析（Fold AUC 0.974/0.983 等）；奖牌数给 95% CI 图。
- **作图风格**：流程图先行（全工作流、Task 1 流程），图题带结论性短语（如 "95% CI for Medals"）。
- **Summary 亮点**：未提取（见标题注），无法评价。
- **可借招**：提醒型反例——「灵敏度」一词被借用为召回率，术语口径必须与所做检验一致；我们写 Sensitivity 时只指参数扰动，别混用。

## 2507817 — Olympic Medals Unveiled: A Mathematical Exploration of Achievement Trends
- **模型与算法**：Grid-Search Random Forest（GSRF，交叉验证 r=0.710/0.784）+ ARIMA 初预测，t 分布算预测区间；首奖用 Logistic 回归（L1 + sigmoid）；教练效应用 Lasso 回归建分。
- **检验/灵敏度**：第 10 章 Error Analysis and Sensitivity Analysis 专章（扰动后稳定性）；残差直方图、SW 检验、10 折 CV 示意图齐备。
- **作图风格**：图型杂而全（ROC、混合矩阵热力图、径向直方图、误差棒），图注多为名词短语。
- **Summary 亮点**：逐 Task 编号推进，每 Task 一段、段末必落数字或图表索引（as shown in Figure 9/Table 11）。
- **可借招**：Summary 里给关键结果标图表出处，评委可按图索骥——我们的强连接点名单也应在 Summary 里指到具体表号。

## 2510006 — 2028 LA Olympics: Who Will Dominate the Medal Count?
- **模型与算法**：分层打法——线性回归 + ARIMA + 随机森林按国家类型（东道主/美国/有牌国/无牌国）分工，新项目用 Monte Carlo 分配，Poisson 分布推 90% CI；教练效应 Fisher 精确检验。
- **检验/灵敏度**：灵敏度专节（7.1）把置信水平 60/80/90/95/99% 与相关阈值 r 联动重算区间，并排五档区间图对比。
- **作图风格**：不确定性可视化最重——多档置信水平区间图成组出现，ACF/PACF、Ljung-Box 等诊断图齐全。
- **Summary 亮点**：概率措辞克制且量化：「美国至少 95% 概率奖牌增长」，同时明说小国预测不确定性大。
- **可借招**：多档置信水平并排展示可直接用于问题1——同一阈值 δ 下画多档成本/失真区间，显示结论对口径的依赖。

## 2510185 — Maximizing Medal Performance: Athlete and Event Potential Indices
- **模型与算法**：自创 Athlete Potential Index（API，奖牌加权指数衰减函数）做特征，GridSearchCV 调参随机森林（R²=0.8792）+ Bootstrap 生成 95% CI；无牌国用 BP 神经网络分类（AUC 0.94）；教练效应用 Event Potential Index（EPI）量化。
- **检验/灵敏度**：灵敏度做法是变数据集规模看预测与信息增益变化（图 12–13），变化小即称鲁棒；多模型对比选型表在前。
- **作图风格**：流程图密度高（每个 Task 一张流程/框架图），拟合曲线对比图收尾。
- **Summary 亮点**：数字颗粒度细：超参数、R²、AUC、首奖概率（关岛 0.153）全部进摘要。
- **可借招**：「变样本规模验稳定性」可移植为问题3 的「变失效抽样规模（10/20/40 城）验应急方案稳定性」。

## 2510862 — 2028 Olympic Medal Predictions: Multi-Effect Analysis and Strategic Insights
- **模型与算法**：Stacking 集成（R²=0.88）预测奖牌 + Bootstrap 95% CI；项目分析 Pearson 相关 + SHAP；教练效应用 PSM-DID（2000 干预年，+3.213 块/届，2% 显著），K-Means 选受益国。
- **检验/灵敏度**：第 9 章 Model Testing 专章——Stacking 做 10 折 CV，PSM-DID 做平衡检验 + 灵敏度检验，检验与模型一一对应。
- **作图风格**：结构图/原理图多（Stacking 原理、PSM-DID 步骤推导图），SHAP Top10 分组条图。
- **Summary 亮点**：每 Task 段末有「方法 + 数字 + 稳健性一句」的固定收尾，末段专讲检验结论。
- **可借招**：检验专章按模型逐个对应（而非笼统一节）——我们三问各配各的检验，结构照此。

## 2513314 — A Glimpse of Olympics Medals through Bayesian Model
- **模型与算法**：Bayesian Hierarchical Dirichlet-Multinomial（BHDM）——奖牌数服从 Dirichlet-Multinomial、国家系数分层先验、Gamma 集中参数，MCMC 后验推断，直接输出 95% 可信区间与「破冰」概率。
- **检验/灵敏度**：对弱信息先验与等分布假设做灵敏度分析（换先验/换分布后预测仅小幅偏离）；与基线模型 R² 对比（总牌 0.85、金牌 0.80）。
- **作图风格**：图极少而精（正文仅约 6 图），靠后验汇总表扛论证（9 张表，多为 posterior summary）。
- **Summary 亮点**：区间型 headline 范本：美国 146 枚（95% CI: 136–156）、金牌 53（50–56），点估计必带区间。
- **可借招**：失真本身是乘积型不确定量——问题1 可学 BHDM 的口径，把每城累计失真报成区间/可信带而非单值。

## 2514362 — Unveiling 2028 Glory: Data-Driven Predictions and Strategic Insights via Advanced Statistical Models
- **模型与算法**：混合效应负二项回归（计数 + 国家异质性）为主模型，零膨胀模型管首奖概率，多层嵌套集成；教练效应用贝叶斯修正熵 + Laplace 平滑 + 信息增益/效应强度比双验证；自加「冷战修正因子」。
- **检验/灵敏度**：全批最全——4.5 与 5.5 两处灵敏度：排名波动分析、模型对比、参数灵敏度、消融实验（Ablation Study）四件套。
- **作图风格**：25 图，含排名波动图、单因素消融图、黑天鹅情景图（巴西），图题多带分析对象名。
- **Summary 亮点**：主数字全带 95%CI（美国金牌 42 [37,46]、总牌 122 [113,131]），首奖概率三连（58.2%/42.1%/33.5%）。
- **可借招**：消融实验可移植——问题2 分别去掉「多源修正」「强连接」各跑一遍，用成本/失真差证明每个机制的必要性。

## 2514461 — Sketch an Olympic Vision
- **模型与算法**：四模型链——SVR 预测各项目设项数 → LSTM 试错后改用 XGBoost 预测奖牌份额（东道主 +15% 修正归一化）；首奖数用 Cox 比例风险 + Monte Carlo（最可能 3 国、概率 22.73%）；教练效应用阈值法 + Isolation Forest 异常检测交叉验证（一致率 89%）。
- **检验/灵敏度**：用 2024 年回测验证，9 个典型国家 95% CI 全部覆盖真实值；第 9 章灵敏度分析 + 阈值-预测关系图。
- **作图风格**：玫瑰图（项目重要性）、拟合线与过/欠拟合对照图（中国跳水/乒乓），图题直白。
- **Summary 亮点**：罕见地在 Summary 里写失败过程（LSTM 过/欠拟合 → 转 XGBoost），诚实感强。
- **可借招**：Summary 里交代被否方案及原因（与 2021-C 诚实范例同路）——我们可写明为何不用纯最短路/纯 MST。

## 2515235 — From Models to Medals: The Winning Formula Behind the Data
- **模型与算法**：SARIMAX/ARIMA 预测设项数；TMH-OMP 模型 = Mundlak 修正 Tobit + Hurdle 管截断/零牌（>10 牌国准确率 79.3%）；教练效应用动态 DID + 事件研究 + IPW 双重稳健估计（DRD-CE，R²=0.756，教练系数 3.1084）。
- **检验/灵敏度**：第 8 章灵敏度用「金银铜求和总牌 vs 直接输入总牌」的平均误差 8.0783% 做自洽误差分析（口径偏误差分析，非参数扰动）。
- **作图风格**：概览图 + 数据处理步骤图靠前，分类-建议图收尾（按国家类型给建议）。
- **Summary 亮点**：首奖概率只给两位（安道尔 0.39、马尔代夫 0.32），不堆名单；模型名（TMH-OMP、DRD-CE）成串出现。
- **可借招**：自洽误差校验法可移植——问题1 用「逐边失真乘积 vs 路径端到端重算」双口径核对累计失真，误差入文。

## 2516178 — 标题未提取（提取文本自 Introduction 起，Summary 页未提取到）
- **模型与算法**：双阶段 XGBoost——一阶段 XGBoost 分类器判有无奖牌，二阶段 TPE 优化的 XGBoost 回归器（TPE-XGBoost）预测数量；教练效应用 DID；SHAP 做项目贡献新洞见。
- **检验/灵敏度**：以回测检验为主——2020/2024 两届预测精度表 + 预测区间覆盖率（PICP）对比表；1000 轮 Bootstrap 算 95% CI。无独立参数灵敏度专节。
- **作图风格**：ROC 三模型对比、双阶段工作流图、SHAP 分布/瀑布图（美国银牌预测）为主，图题带国别与奖牌色。
- **Summary 亮点**：未提取，无法评价。
- **可借招**：PICP（区间覆盖率）是评价区间质量的硬指标——我们报失真/成本区间时应同时报覆盖率校准，而非只画区间。

## 2516695 — "Golden Dynamics: Bayesian-AI Olympic Forecasting with Geopolitics & Coaching"
- **模型与算法**：三模型品牌矩阵——HARMONIE（三层贝叶斯 HAR + MCMC，SBN-DBN 动态贝叶斯网络）、CHAMPS（Cox 风险 + Monte Carlo 首奖预测）、GCIQ（DID-GAN 教练效应量化），另用 GNN 建教练流动网络、LSTM 做窗口分析。
- **检验/灵敏度**：全批最硬核——Sobol 全局灵敏度指数（图 22 堆叠条）、GDP 弹性表（β±20%）、极端情景转移概率表、时间窗灵敏度，95% 误差棒。
- **作图风格**：24 图，含全球教练流动热力图、金牌分布概率密度图、Sobol 堆叠条，图注带读图结论（如 box-plot 展示增量分布不对称）。
- **Summary 亮点**：单设「Sensitivity Analysis:」段进摘要（GDP 弹性 0.18、极端情景美中跌幅 -12.7%/-9.3%），把灵敏度当卖点卖。
- **可借招**：Sobol 全局灵敏度可用于问题1 失真公式三参数（距离指数、出度系数、封顶值）的贡献分解；灵敏度进 Summary 值得学。

## 2517690 — Who will dominate the 2028 Olympic Games?
- **模型与算法**：十折 CV 横评 RF/Lasso/XGBoost/神经网络后选随机森林回归（R²=0.92）；无牌国 Logistic 回归给首奖概率（安哥拉 0.81）；项目关联用灰色关联分析；东道主优势用 N 人博弈 + Nash 均衡解释。
- **检验/灵敏度**：第 8 章 Sensitivity Analysis and Error Analysis——以 CV 折数变化做灵敏度（交叉检验变异系数表），属较弱口径。
- **作图风格**：雷达图（项目水平）、决策树数量-误差关系图、N 人博弈构成图，图题口语化。
- **Summary 亮点**：结构规整逐问推进，百分比型 headline（美国金牌 +10%、日本 -5%）。
- **可借招**：多模型同台横评再选型的写法可用于问题1 算法选型（Dijkstra 变体 vs MST 变体同表对比后择一）。

## 2521556 — Beyond Medals: A Predictive Model for Olympic Success and Identifying Opportunities
- **模型与算法**：自下而上 TrueSkill-SARIMAX-RF 链——TrueSkill 评各国单项实力、SARIMAX 预测 2028 实力（含东道主因子）、贝叶斯预测处理误差，再分配奖牌汇总；教练效应用残差异常分析找证据 + LR-SCAD 模型量化。
- **检验/灵敏度**：灵敏度结论为「跨数据集泛化强」（Summary 语），正文另有 2024 预测区间 vs 真实值对比图（图 8）；无参数扰动专节。
- **作图风格**：每 Task 一张总结构图打头，预测概率图成对出现（图 19/20），虚拟奖牌榜图（图 9）做门面。
- **Summary 亮点**：概率分布型 headline——「2028 年恰有 2 个零牌国破冰的概率 0.25」，报的是计数分布而非名单。
- **可借招**：问题3 可学此口径——不报某一次抽样的重连结果，报「失效后仍达标城市数」的分布（如 P(≥1000 城达标)=…）。

## 2522820 — The Best of the Best: Olympic Medal Tables
- **模型与算法**：先 Tobit（MLE），诊断出异方差后换轨：DBSCAN 把国家聚成 3 簇，分层混合线性效应模型 + 负二项回归，低表现簇用 Probit 判零牌概率；项目分析用 SVD + Sport-Point Efficiency + RCA；教练效应用移动平均时间序列异常法。
- **检验/灵敏度**：无独立灵敏度专节；检验靠模型诊断驱动换模（异方差诊断）与历史教练名单交叉核对结果。
- **作图风格**：图最少（6 图）——DBSCAN 聚类图与「上限比例逼近 vs 真实值」对照图扛全场，表极多（18 张）。
- **Summary 亮点**：明说区间宽度（前三名 95% CI 跨度约 30），不掩盖不确定性；排名变化 headline 极端醒目（牙买加 +27、加拿大 -99）。
- **可借招**：DBSCAN 先聚类再分簇建模，与问题1「先按地理/失真聚类城市、再逐簇建树」同构；且「诊断不合就换模型并写明」是可信度加分项。

## 2524070 — From Data to Podiums: A Study for Olympic Medal Forecasting
- **模型与算法**：贝叶斯零膨胀负二项（ZINB）+ MCMC 后验，区分抽样零与结构零算各国首奖概率（毛里塔尼亚 24.8%）；项目因素用 GRI 关联规则模型（支持度 80.56%、置信 >80%、提升 >1）；教练效应用混合效应模型（教练-国家配对为随机区组，点估计 3.74）。
- **检验/灵敏度**：MCMC 收敛诊断当检验门面——全参数 R̂=1、Bulk/Tail ESS 达万级写入 Summary；QQ 图与残差图（Box-Cox 前后）做模型诊断。无参数灵敏度专节。
- **作图风格**：直方图、预测分布图、关联规则结果图与 QQ/残差诊断图并重，图题简洁。
- **Summary 亮点**：按五大关切分段、每段以冒号小标题领起（Predict Medal Standings…:），结构感最强之一。
- **可借招**：「结构零 vs 抽样零」的区分可移植——问题1 里分清「结构上不可达（弱连接必然超限）vs 参数上偶然超限」的城市，两类处置不同（前者必须强连接，后者可调路径）。

---

## 本批共性（18 篇同题打法分布）

**赛题结构**：四问固定——① 2028 奖牌榜预测（含升/降国）② 零牌国首奖概率 ③ 项目重要性/东道主选
...[truncated 3075 chars]