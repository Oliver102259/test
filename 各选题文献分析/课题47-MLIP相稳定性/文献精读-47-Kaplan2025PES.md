---
title: 文献精读报告：A Foundational Potential Energy Surface Dataset for Materials
date: 2026-08-21
version: V1.0
audience: 毕设文献精读档案（NUS 311 MSE）
---

# 文献精读报告：A Foundational Potential Energy Surface Dataset for Materials

> **元信息**：Aaron D. Kaplan, Runze Liu, Ji Qi, Tsz Wai Ko, Bowen Deng, Janosh Riebesell, Gerbrand Ceder, Kristin A. Persson & Shyue Ping Ong（通讯 ongsp@ucsd.edu）｜本 PDF 为 arXiv 预印本 arXiv:2503.04070v1（6 Mar 2025）｜精读日期 2026-08-21
> 证据分级：R0=原文事实（附页码/章节锚点）｜R1=外部背景知识｜R2=推断/评价

## 一、文献速览总结

一句话定位：本文发布 **MatPES**——一个面向材料的**基础势能面（PES）数据集**，用"数据质量优先于数量"的策略挑战"越大越好"的通用 MLIP（UMLIP）训练范式（R0，摘要 p1）。

核心内容：MatPES v2025.1 含 434,712 个 PBE 与 387,897 个 r2SCAN 高收敛单点计算的能量/力/应力（共 504,811 个结构），这些结构用 2DIRECT 采样从 2.81 亿个 MD 快照（160 亿原子环境）中精选而来；并首次给出覆盖周期表的 r2SCAN 泛函 PES 数据（R0，p1、p5–6）。

主要结论：仅用约 40 万个结构的 MatPES 训练的 UMLIP，在平衡、近平衡与 MD 性质基准（MatCalc）上**匹敌甚至超过**用 MPtrj（约 100 万）与 OMat24（约 1 亿）训练的模型；在测试集能量 MAE 上比 MPRelax/OMat24 模型低 4–10 倍（R0，摘要 p1、p8–9）。

## 二、课题关联分析

本文是课题 47 的**"判稳精度来源"**：相稳定性判定的可靠性最终取决于 MLIP 在非平衡构型上的 PES 描述，而 MatPES 正是为修复 MPRelax 数据的系统性缺陷而生。

- **直接可借鉴**：①课题 47 若用 MPtrj/MPF 训练的 M3GNet/CHGNet 做判稳，可能继承"力被系统性低估、声子过软、非平衡外推差"的缺陷；改用 MatPES 训练的 UMLIP（如 TensorNet-MatPES-PBE-v2025.1）可显著改善（R0，p3、p6）；②MatPES 的 r2SCAN 数据改善了弱离子键/范德华键描述，对含卤素、多价态的 SSE 体系相稳定性更可靠（R0，p3–4）；③"用 MD 快照 + 超胞采样覆盖非平衡构型"的思路，可指导毕设自建小规模判稳数据集（R0，p5–6）。
- **对 7 志愿整体**：文中用 MVL-batt 的 172 个电池材料 AIMD 评估离子电导率（TensorNet-MatPES 显著优于 TensorNet-MPF），直接服务课题 23/24/50 的 SSE 离子输运模拟（R0，p14）。

## 三、内容深度解读

**1. 动机：MPRelax 的三大缺陷（p2–4）**：①几乎全为近平衡结构，只能刻画极小值附近 PES；②PBE 与 PBE+U 混用且形成能做经验修正，而力/应力未修正，跨化学空间出现 PES 不光滑；③计算设置随十年方法演进，含系统/非系统噪声。Deng et al. 发现现有 UMLIP 低估大振幅力、声子过软；Qi et al. 证明替换单点高精度数据可改善 UMLIP（R0 p2–3）。

**2. 数据构建（p4–6，Fig. 1）**：对 MP（v2022.10.28）281,572 个基态结构与超胞用预训练 M3GNet（MP-2021.2.8-DIRECT）做 300K/1atm NpT-MD，生成 2.81 亿结构/160 亿原子环境；用 2DIRECT 采样（先结构 PCA 聚类、再原子环境 PCA 聚类，每簇取原子数最少结构）精筛；补充 <100 原子的 MP 基态结构；最终对 504,811 结构做严格收敛的单点 PBE/r2SCAN 计算（R0 p4–5）。除惰性气体、放射性元素与稀土外，每个元素 ≥7,000 结构（p5）。

**3. 数据分布对比（p6–7，Fig. 2）**：MatPES 的 E_coh 近高斯、|F_i| 近对数正态，覆盖远宽于 MPtrj；OMat24 偏重高能/大受力但欠采样近平衡构型；MatPES 在平衡与非平衡之间更均衡（R0 p6–7）。

**4. PES 基准（p8，Table 1）**：在 MatGL 中用 M3GNet/CHGNet/TensorNet 三种架构训练；MatPES UMLIP 的测试 MAE（21,737 结构，5%）能量误差比 MPRelax/OMat24 低 4–10 倍，且训练/验证/测试 MAE 接近（几乎无过拟合）；MPtrj CHGNet 能量误差高源于 PBE/PBE+U 混用；OMat24 TensorNet 因欠采样近平衡而误差大、且稀土/氧元素误差偏高（R0 p8）。

**5. 平衡/近平衡基准（p10–13）**：MatPES UMLIP 结构弛豫的 CrystalNN 指纹距离更低更稳；形成能 MAE 与 MPRelax 相当或略优；剪切模量 G_VRH 与离平衡力 |F_i| 显著改善，体模量 K_VRH 与热容 C_V 相当（MPRelax 因近平衡结构多而 K_VRH 略优；OMat24 因 Boltzmann 采样而 C_V 最优）；等变 TensorNet（838k 参数）略优于不变模型，MatPES 基本纠正了 MPRelax 对 PES 曲率的系统性低估（R0 p10–13）。

**6. MD 基准（p13–14）**：用 MVL-batt 的 172 个电池材料 AIMD 评估。稳定性上，1500 K 时 TensorNet-MatPES-PBE/r2SCAN 终止率 <10%，而 TensorNet-OMat24 约 55%、TensorNet-MPF 约 65%；等变模型优于不变模型，r2SCAN 优于 PBE（R0 p13–14）。离子电导率上 TensorNet-MatPES 显著优于 TensorNet-MPF（后者高估 σ、R² 为负），TensorNet-OMat24 与之相当但训练数据大 250 倍（p14）。

**7. 讨论：数据质量 > 数量（p14–15）**：TensorNet 在 MatPES（~40 万）上单卡 RTX A6000 约 15 分钟/epoch，OMat24（~1 亿）需 16 卡 A100 约 20 小时/epoch；呼吁开放数据、多维基准（MatCalc），未来纳入高温/高压 MD、缺陷等（R0 p14–15）。

## 四、技术难点识别

1. **非平衡构型采样**：仅靠 DFT 弛豫无法覆盖远离极小值的 PES，需 MD 快照 + 超胞（超胞比单胞覆盖更宽，R0 p5–6）。
2. **采样效率**：2.81 亿结构不能全算 DFT，需 2DIRECT 这类降维分层采样（R0 p5–6）。
3. **泛函不一致噪声**：PBE/PBE+U 混用 + 未修正的力/应力导致 PES 不光滑，是历史数据集的核心病灶（R0 p2–3）。
4. **更高阶泛函数据缺失**：此前无跨周期表 r2SCAN PES 数据，制约了键描述精度的提升（R0 p3–4）。

## 五、可借鉴点

1. 判稳弛豫优先选用 **MatPES 训练的 UMLIP**（TensorNet-MatPES-PBE-v2025.1 等），避免 MPtrj/MPF 模型在非平衡构型与力上的系统性偏差（R0 p8、p13–14）。
2. 采用 MatCalc 式多维基准（结构指纹距离、G_VRH、|F_i|、MD 稳定性 T_term、离子电导率）而非只看形成能，来验证毕设所选 MLIP 是否胜任判稳任务（R0 p10–14）。
3. "数据质量 > 数量"与"小模型 + 好数据"两条经验，可用于毕设训练/微调 MLIP 的预算决策（R0 p14–15）。

## 六、延伸思考

1. MatPES 直击 M3GNet/CHGNet 一代模型的软肋（MPRelax 数据缺陷），说明课题 47 若沿用 M3GNet 判稳，需清醒认知其"近平衡 + 噪声"的适用边界（R2）。
2. r2SCAN 数据与 MP 的 r2SCAN 升级（Horton 2025 所述）同向，未来判稳参照与 MLIP 势面都将向 meta-GGA 靠拢，毕设应留意版本一致性问题（R2）。
3. MatPES 是 MatGL 中 TensorNet-MatPES 系列 FP 的数据底座，与 MatGL、DPA4 构成"数据 → 库 → 模型"的完整供应链，四篇可串成一条技术主线（R2）。

*报告完 · 证据优先（R0/R1/R2 分级，结论可回溯至 PDF 页码/章节）*
