---
title: 文献精读报告：Highly efficient anion exchange membrane water electrolyzers via chromium-doped amorphous electrocatalysts（铬掺杂非晶电催化剂实现高效阴离子交换膜水电解槽）
date: 2026-09-18
version: V1.0
audience: 毕设文献精读档案（NUS 311 MSE）
---

# 文献精读报告：Highly efficient anion exchange membrane water electrolyzers via chromium-doped amorphous electrocatalysts（铬掺杂非晶电催化剂实现高效阴离子交换膜水电解槽）

> **元信息**：Sicheng Li, Tong Liu, Wei Zhang, Mingzhen Wang, Huijuan Zhang, Chunlan Qin, Lingling Zhang, Yudan Chen, Shuaiwei Jiang, Dong Liu, Xiaokang Liu, Huijuan Wang, Qiquan Luo, Tao Ding, Tao Yao（S. Li 与 T. Liu 共同第一作者；通讯作者 Wei Zhang、Tao Ding、Tao Yao）｜*Nature Communications* 2024, 15, 3416（11 页）｜DOI: 10.1038/s41467-024-47736-0｜精读日期 2026-09-18
> 证据分级：R0=原文事实（附页码锚点，本文锚点＝PDF 页＝文章页 1–11）｜R1=外部背景知识｜R2=我的推断
> 术语中英对照：OER（析氧反应 oxygen evolution reaction）｜AEMWE（阴离子交换膜水电解槽 anion exchange membrane water electrolyzer）｜MEA（膜电极组件 membrane electrode assembly）｜vtc-XES（价-芯 X 射线发射谱 valence-to-core X-ray emission spectroscopy）｜XANES/EXAFS（X 射线吸收近边／扩展边谱）｜RDS（决速步 rate-determining step）｜ECSA（电化学活性面积）｜GDE（气体扩散电极 gas diffusion electrode）｜PGM（铂族金属）｜SR-IR（同步辐射红外）

## 一、文献速览总结

本文解决 AEMWE 阳极 OER 的活性与稳定性兼顾问题，并给出可推广的电子结构调控判据（R0, p.1）。作者称 AEM 路线可用非铂族金属（non-PGM）阳极、膜更便宜、无氟基聚合物、无需耐酸栈材料；短板是合成未面向工业放大、Ni/Fe 基材料稳定性差（R0, p.1）。

核心做法是**一步液相还原法**：NaBH₄ 与混合金属氯化物溶液搅拌反应，洗涤干燥得非晶 FeCrOₓ、CoCrOₓ、NiCrOₓ（R0, p.2）。CoCrOₓ 最优：η₁₀=268 mV，优于 CoOₓ（323 mV）与商业 RuO₂（314 mV）（R0, p.3）；η=400 mV 下电流密度为 FeCrOₓ/NiCrOₓ/RuO₂ 的 10.7/3.4/2 倍，比 CoOₓ 高 192%；Tafel 斜率 101.6 mV dec⁻¹（CoOₓ 146.6、RuO₂ 196.0）（R0, p.4）。器件层面以 CoCrOₓ 为阳极组装 AEMWE，2.1 V 达 1.5 A cm⁻²，60 °C、0.5 A cm⁻² 连续 120 h，衰减 <4.9 mV h⁻¹（R0, p.1、p.4–5）。

机制证据链：Cr 掺杂**拉低** Co 平均价态（Cr 为 +3，与 Cr₂O₃ 重合）（R0, p.5）；反应中 Co 价态升高（Co L 边高能移 1.9 eV），原位 EXAFS 显示 Co–O 配位数由 4 增至 6 以上，vtc-XES 的 Kβ″ 峰（约 7690 eV）增强、Co–O 键收缩至约 1.92 Å（R0, p.5）；DFT 得 CoCrOₓ 的 RDS 为 *OH→*O，能垒 0.50 eV（FeCrOₓ 0.76、NiCrOₓ 0.63 eV）（R0, p.6）。

## 二、课题关联分析（与"电沉积 MnO₂ 稳定 Ru 酸性 OER"的关联：可从"非晶/掺杂催化剂的稳定性策略、电解槽器件级验证、局部反应环境调控、MnO₂/含锰物种的角色"切入）

**1）器件级验证的完整范式。** 本文把论证从半电池推进到 5 cm² AEMWE，并把器件阻抗分解为欧姆电阻 OR、电荷转移电阻 CTR、传质电阻 MTR，以最低的 CTR/MTR 解释活性来源（R0, p.5）。本课题做酸性单电池可沿用"半电池→器件→三电阻分解→mV h⁻¹ 衰减率"框架，差别是必须增加**出口液 Ru/Mn 浓度监测**（R2）。

**2）掺杂与非晶的稳定性策略及其风险。** "高价位掺杂→降低活性金属平均价态→优化中间体吸附→降低 RDS 能垒"是本文的因果主线（R0, p.5–6）。对本课题的启发：若 Mn 掺入 RuO₂（或 Ru 嵌入 MnO₂）能改变 Ru 的价态与配位环境，就可能同时改变活性与**溶出倾向**（R2）。反面警示同样重要：碱性下 Cr 仍部分电解溶解（反应后 EDS 显示 Cr 含量下降），原位下 Co–Cr 散射路径消失、只剩 Co–O 与 Co–Co（R0, p.5、p.9）——"掺杂剂自身溶出"是共性风险，酸性 OER 中 Mn 的溶解风险只会更高（R1/R2）。

**3）非晶结构"准稳定"的证据。** 反应后 HRTEM 显示形貌基本保持，但出现短程晶格条纹与纳米孔，SAED 出现亮点、非晶态大体保留（R0, p.5）。提示：电沉积的非晶/层状 MnO₂ 同样会重构，结构评价须做在"反应后"（R2）。

**4）直系文献线索。** 本文参考文献 40 为 Lin 等《In-situ reconstructed Ru atom array on α-MnO₂ with enhanced performance for acidic water oxidation》（*Nat. Catal.* 2021, 4, 1012–1023）（R0, p.11）——即本课题直系前作（R1：α-MnO₂ 负载 Ru），应继续追踪其引用网络。

## 三、内容深度解读（含关键数据，逐条标 R0 页码）

**（1）合成与结构（R0, p.2、p.8）。** 混合金属氯化物 + NaBH₄ 还原；SEM 多孔；TEM 无序原子结构、约 20 nm 颗粒；HRTEM 与球差 HAADF-STEM 均无晶格条纹；XRD 峰宽而弱；SAED 衍射环（内环明亮＝短程有序）；EDS mapping 显示 Co、Cr、O 均匀、无分相；ICP-AES 显示 M:Cr 原子比接近 1:1。合成细节：CoCl₂·6H₂O 与 CrCl₃·6H₂O 配成 2 M 溶液各取 2 mL 混合，滴加 NaBH₄（3 g/20 mL），搅拌 15 min、静置过夜、冷冻干燥、洗涤后真空干燥。

**（2）半电池电化学（R0, p.3–4、p.8）。** 条件：O₂ 饱和 1 M KOH、三电极、iR 补偿、碳纸载量 0.36 mg cm⁻²、扫速 5 mV s⁻¹；EIS 固定 1.57 V vs RHE；ECSA 取 0.875–0.975 V vs RHE 双电层电容。数据：η₁₀=268 mV（CoCrOₓ）；η=400 mV 下电流密度为 FeCrOₓ/NiCrOₓ/RuO₂ 的 10.7/3.4/2 倍，比 CoOₓ 高 192%；Tafel 101.6、146.6、196.0 mV dec⁻¹（CoCrOₓ/CoOₓ/RuO₂）；R_ct 依次 9.0（CoCrOₓ）、11.1（RuO₂）、20.1（CoOₓ）、21.6（NiCrOₓ）、45.4 Ω（FeCrOₓ）；C_dl 依次 16.45、9.95、12.12、7.56、6.13 mF cm⁻²。半电池稳定性：1.56 V 恒压 50 h 无明显损失，电流先升后稳（归因于活性物质生成与电解液渗入孔道）。

**（3）器件级性能（R0, p.4–5、p.8）。** 组装：不锈钢集流板、PTFE 垫片、钛毡、AEM、碳纸；阳极 CoCrOₓ + PiperION 离聚物，阴极 Pt/C（TANAKA 40 wt%）；喷涂于 AEM（PiperION-A60-HCO₃）或 Pt-Ti 毡成 GDE；膜经 0.5 M KOH 浸泡并冲洗转为 OH⁻ 型；有效面积 5 cm²，夹具扭矩 8 N·m。性能：2.1 V 时 1.5 A cm⁻²；内阻 15/20/22/24 mΩ（CoOₓ/FeCrOₓ/NiCrOₓ/CoCrOₓ）；60 °C、0.5 A cm⁻² 恒流 120 h（图 3h 用箭头标出**更换电解液**时刻）；变电流 operando EIS 显示电阻随电流增大而下降。

**（4）价态与局域结构演化（R0, p.5、p.8）。** Cr 掺杂使 Co 平均价态降低（+2/+3 共存），Cr 为 +3（与 Cr₂O₃ 边位重合）；反应后 Co L 边高能移 1.9 eV、Co²⁺ 卫星峰几乎消失。原位 XANES：加压后边位正移；EXAFS 拟合第一壳层 Co–O 配位数由 4 增至 6 以上，且边位与配位数正相关。vtc-XES：Kβ″ 峰增强＝Co–O σ 相互作用增强，差分谱强度与 Co–O 键长负相关，加压后谱形接近 Co₃O₄（R_Co–O=1.92 Å）。原位条件序列：ex situ、OCV、1.42 V、1.67 V vs RHE、反应后。

**（5）中间体与理论（R0, p.6–7、p.10）。** 原位 SR-IR（NSRL BL01B，ZnSe 窗，1.1–1.8 V vs RHE 每 0.1 V 一档）给出三个中间体：*OH 3780、*OOH 1014、*O 930 cm⁻¹（正文表述）；进入 OER 区后 *OH 与 *O 峰增强、*OOH 峰减弱甚至消失；FeCrOₓ、NiCrOₓ 在任何电位下都无 *O 峰。DFT（VASP、PBE、DFT-D3、Hubbard-U：Fe 3.0/Co 3.5/Ni 5.5 eV，(110) 面，截断能 500 eV）：CoCrOₓ 的 RDS 为 *OH→*O（0.50 eV @1.23 V），FeCrOₓ、NiCrOₓ 的 RDS 为 *O→*OOH（0.76、0.63 eV）；CoCrOₓ 向 *OH 转移电荷更少、吸附更弱；TDOS 在费米能级处态密度更高，PDOS 显示导带主要来自 Cr d 轨道。

**（6）EXAFS 拟合的严谨性（R0, p.9）。** 核算独立点数 N_idp（离位/OCV 约 10.9、变量 9–10；工作电位与反应后 ≈10.8、变量 6），S₀² 由 Co 箔固定为 0.71，三壳层模型 Co–O（约 1.5 Å）、Co–Co（约 2.3 Å）、Co–Cr（约 2.8 Å），全部 R-factor ≤0.020。

## 四、技术难点识别

1. **非晶体系"键"的判定困难。** 作者指出 EXAFS 无法区分原子序数相近的配体（C、N、O）或配体的质子化状态，故引入 vtc-XES（R0, p.5）。含义：要证明 Ru–O–Mn 界面耦合，仅靠 Ru K 边 EXAFS 不足以排除 Ru–O–Ru／Ru–OH，需 vtc-XES 或 PDF（差分 PDF）、Ru 与 Mn K 边同时拟合（R1/R2）。
2. **原位数据点稀疏。** 原位 XAFS 仅两个工作电位点（1.42、1.67 V），加压后金属-金属壳层简化为两壳层（R0, p.8–9）；而酸性 OER 失活常发生在最初数十小时，难以捕捉瞬态重构（R2）。
3. **器件耐久的"换液"处理掩盖溶出型失活。** 图 3h 箭头标出更换电解液时刻（R0, p.4），全文未定量反应后电解液金属浓度（仅 ICP-AES 测初始配比，R0, p.8）。对 Ru 的溶解型失活而言，换液＝移除已溶出 Ru，衰减曲线会偏乐观（R2）。
4. **衰减率与工业要求的差距。** 摘要给出 <4.9 mV h⁻¹（R0, p.1）；线性外推 1000 h 漂移达数伏量级（R2，原文未做该外推），与工业电解槽寿命要求仍有数量级差距（R1）。
5. **碱性结论不能直接外推到酸性。** Cr 溶解、Co 价态升高、Co–O 配位数上升均在碱性介质获得；酸性 Ru 的溶解机制与 Co 基氧化物不同（R1/R2）。
6. **图表标注不一致（阅读风险）。** 正文称 *OH 3780、*OOH 1014、*O 930 cm⁻¹，图 5b 图例则标 *O 930、*OH 1014、*OOH 3780 cm⁻¹（R0, p.6）；引用前须回原图核对（R2）。OCR 版另有字符混淆，数值须核原版 PDF。

## 五、可借鉴点（对实验设计直接可用：合成（是否含电沉积）、表征、电化学测试、器件级验证、稳定性评价）

**合成（明确不含电沉积）。** 本文为一步液相 NaBH₄ 还原（R0, p.2、p.8），**无电沉积步骤**，参数不能照搬；可迁移的是设计原则：高价位掺杂剂降低活性金属平均价态、非晶化提高位点密度（R2）。可执行对照（R2）：① 空白——纯电沉积 MnO₂、纯 Ru（或 RuO₂）；② 共沉积——Ru–MnO₂，Mn:Ru 设 1:3、1:1、3:1；③ 分层——先电沉积 MnO₂ 再沉积/浸渍 Ru；④ 参比——商业 RuO₂。成分比按性能筛选确定（本文 1:1 最优，R0, p.3）。

**表征。** ① 非晶性多手段交叉：XRD + HRTEM + SAED + 球差 HAADF-STEM（R0, p.2）；② EDS mapping 证明无分相，ICP-AES/MS 测 Ru:Mn 比（R0, p.2、p.8）；③ 原位 XAFS 电位序列照抄五点设计（ex situ、OCV、两个工作电位、反应后），酸性窗口改为 OCV、1.30、1.40、1.50、1.60 V vs RHE（R0, p.8）；④ EXAFS 报告 N_idp、S₀²、R-factor，建立 Ru–O、Ru–Ru、Ru–Mn 三壳层模型（R0, p.9；R2：壳层归属为我的设定）；⑤ 补做 vtc-XES 判定 Ru–O–Mn 配体性质（R0, p.5；R2）。

**电化学测试。** 三电极参数逐项移植（酸性体系替换电解质与参比）：O₂ 饱和电解液、5 mV s⁻¹、iR 补偿、碳纸 0.5×0.5 cm、载量 0.36 mg cm⁻²、催化剂:碳黑=2:1、5 wt% Nafion 50 µL、外覆 0.05 wt% Nafion 7.5 µL（R0, p.8）；EIS 固定电位测（本文 1.57 V vs RHE，建议本课题固定 1.50 V vs RHE 便于横向比较）、ZView 拟合 Rs/R_ct/C_dl（R0, p.8）；ECSA 用非法拉第区双电层电容，并给出 ECSA 归一化比活性（R0, p.8）。

**器件级验证。** 酸性对应方案（R2）：Nafion 膜 + 本课题阳极（Ru–MnO₂）+ Pt/C 阴极，喷涂/热压成 MEA，有效面积 5 cm²，60 °C；沿用本文的三电阻分解（OR/CTR/MTR）与变电流 operando EIS（RMS 交流为直流 10%）（R0, p.5、p.8）。

**稳定性评价。** 双轨制：半电池恒压 50 h（本文 1.56 V）（R0, p.4）+ 器件恒流 120 h @0.5 A cm⁻²（R0, p.4–5），统一用 **mV h⁻¹ 衰减率**与电流保持率两个指标（R0, p.1）；反应后做 XRD/TEM/XPS/EDS 与**电解液 ICP-MS 定量 Ru、Mn 溶出**——本文缺失、本课题必须补齐的关键数据（R2）。

## 六、延伸思考

第一，"高价掺杂剂拉低活性金属价态"与"Ru 因高价态溶解"构成可检验的耦合假设：若 Mn 经 Ru–O–Mn 向 Ru 供电子、抑制其达到易溶高价态，则应有电子结构证据（Ru K 边边位下移、Ru–O 键长/配位数变化），而非仅凭寿命曲线归因（R2）。第二，本文非晶催化剂在反应中**部分晶化并生成纳米孔**（R0, p.5），可见"非晶＝稳定"并非普适结论；电沉积 MnO₂ 多为层状/水合结构，其结晶水与层间阳离子可能是质子/氧交换通道，也可能是溶解起点，值得用原位 XRD/拉曼跟踪（R1/R2）。第三，本文工具链机时门槛高，建议先做可及版本（非原位 XPS/XRD/TEM + 三电极长时 + 反应后 ICP-MS），同步辐射部分申请外部机时（R2）。第四，面向 9.24 组会，本文适合承担"器件级验证与稳定性评价方法论"一页，其"半电池—器件—三电阻分解—衰减率"四段式可作性能展示骨架（R2）。

*报告完 · 证据优先（R0/R1/R2 分级）*
