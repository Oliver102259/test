---
title: CSC-4 · 课题接口与 pre 用处（已填 · 2026-09-21 读完）
date: 2026-09-22
version: V1.0
audience: 毕设文献精读档案（NUS 311 MSE）
---

# CSC-4 · 课题接口与 pre 用处（已填 · 2026-09-21 读完）

> 对应 10 页版 PPT 的映射：见 `FYP/9.24-pre-PPT骨架.md` 顶部「10 页映射方案」
> 证据分级：R0=原文事实（附页码，**期刊页 = PDF 页 + 2195**）｜R1=外部背景｜R2=推断

## 一、这篇文献在课题里的"三个用途"

| 用途 | 具体内容 | 页码 |
|---|---|---|
| ① **论证"为什么必须做酸性"** | PEM 制造局部酸性环境（Nafion ≈ 1 M 质子）；碱性路线受 OH⁻ 迁移率/扩散系数比质子低 1.75 倍限制；基准 **IrO₂ 在酸碱中都会溶**（生成水溶性 IrO₄²⁻）；成稿时唯一兼顾活性与酸稳定的仍是 Ir 基，而 Ir 极稀缺 | p.2208（R0） |
| ② **论证"为什么可以用 MnO₂"** | **γ-MnO₂ 在 pH 2 下电解 8000 h 几乎不失活**；掺入 **Ti、Ge** 等杂原子可稳定 MnO₂ 的反应终止态、带来更多配位不饱和位点；同时警告"**为过渡金属氧化物寻找合适的电位工作窗口是必要的**" | p.2208（R0） |
| ③ **提供"为什么 Mn 能改 Ru"的设计学** | Ni/Co 取代 RuO₂ 活化**桥位氧**作质子受体 → HOO\*–HO\* 差降到 **3.2 eV 以下**；Ni、Co 取代后最大自由能步 **1.49 / 1.33 eV**（过电位 **0.26 / 0.10 eV**）**远低于火山顶 0.37 eV**；Mn³⁺ 恰提供 **e_g = 1** 的最优占据 | pp.2203–2204、p.2200（R0） |

## 二、逐页对应（10 页版）

| 页 | 用它的什么 | 怎么用 |
|---|---|---|
| **P2** Background | p.2208 三句：PEM 局部酸性 / Ir 稀缺且 IrO₂ 也溶 / 碱性受 OH⁻ 迁移率限制 | 开场铺垫"为什么做酸性 + 为什么要稳定化" |
| **P3** Ru 的活性-稳定悖论 | **p.2202：O p 带中心越靠近费米能级 → 活性越高、稳定性越低** | 一句话把课题定性为"受稳定性约束的设计问题" |
| **P5** 文献综述（MnO₂ 可否用于酸） | p.2208：γ-MnO₂ 8000 h + Ti/Ge 掺杂稳定 | 与偏 AEM-5 §6 的 Ru/α-MnO₂ 先例并列，形成"MnO₂ 在酸里站得住"的双证据 |
| **P6** Gap & hypothesis | pp.2203–2204 的质子受体设计学 | 论证"Mn 作为同族桥位氧活化剂"的合理性（R2） |
| **P7** Risk | p.2202（trade-off）+ p.2208（工作窗口是硬约束） | 为 go/no-go 实验提供文献依据 |
| **P9/P10** 对比表与判据 | **Table 1（pp.2207–2208，23 个催化剂的设计参数与活性位；1–19 AEM、20–23 LOM）** | 做文献对比表时引用；也用于"我们的判据对标谁" |

## 三、可直接说的英文（3 句，背下来）

1. *"Acidic OER is not only a catalysis problem but a stability-constrained design problem: the O p-band centre trade-off means higher activity usually costs stability (Chem. Soc. Rev. 2020, p. 2202)."*
2. *"MnO₂ is not merely an alkaline catalyst — γ-MnO₂ has been reported to operate for 8000 hours at pH 2, and Ti or Ge doping stabilises its reaction terminus (p. 2208). The same work warns that finding a suitable potential window is essential."*
3. *"Breaking the scaling relation with proton acceptors is the design logic we borrow: Ni or Co substitution in RuO₂ activates bridging oxygen and lowers the potential-determining step to 0.26–0.10 V, below the 0.37 V volcano limit (pp. 2203–2204). Manganese is our candidate for the same role."*

## 四、读完自检（口头 30 秒/题）
- [ ] **0.37 V** 是怎么来的？（HO\* 与 HOO\* 吸附能被近似常数耦合 → 四步不能同时最优 → 火山顶理论最低过电位）
- [ ] **3.2 eV** 指什么？质子受体策略怎么把它压下去？
- [ ] 为什么 **Mn³⁺** 有资格扮演"桥位氧活化剂"？（同族过渡金属 + e_g = 1 最优占据 + AEM-5 把它列为 **OER 惰性掺杂元素**，不抢活性位）

## 五、缺口（写 pre 时要绕开）
- **2020 年成文** → 不含 2021 年后的 Ru/MnO₂ 直接先例（Lin 2021、JACS 2026、Nat. Commun. 2026）。
- **无定量溶出数据**（无 S-number、无 ICP-MS 溶出速率）→ 稳定性量化仍要另找原始文献（Cherevko 组；Li et al. *Angew.* 2019, 58, 5054）。
- 对 MnO₂ 只是顺带两句话，**不是**系统综述 → "MnO₂ 在酸性 OER 中的行为"须自建基线。
