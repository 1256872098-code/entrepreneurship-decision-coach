---
name: entrepreneurship-simulation-decision
description: Analyze nationwide entrepreneurship simulation market reports and historical competitor decisions, then produce a complete, auditable decision-form recommendation for the current period. Use for first-period decisions based on market background alone and later-period decisions that also depend on prior-period competitor actions and results.
---

# 全国创业决策仿真

为全国创业决策仿真生成当期决策表。首期依据市场形势报告；第二期起还要结合上一期其他企业的决策、经营结果和本企业状态。

## 工作原则

- 先判断当前期次，再区分“本期外部背景”“本企业状态”“上一期竞争信息”。
- 原样保留单位、百分比或千分比、产品型号、数量和价格，不擅自换算含义不明确的数据。
- 输出完整的 24 个决策字段；没有依据的值标为“待规则确认”，不要伪造精确结论。
- 每项建议都给出简短依据，并区分已知事实、规则推导和策略判断。
- 检查产销采购是否衔接、人员增减是否冲突、资金用途是否超过可用资金，以及投标或特殊订单条件是否满足。
- 当用户补充新规则时，将其写入 `references/rules.md`，并优先使用明确规则而非经验猜测。

## 执行流程

1. 读取 [references/simulation-spec.md](references/simulation-spec.md)，按其中的字段和单位整理输入。
2. 若 `references/rules.md` 已含适用规则，读取并逐条应用；若规则尚未提供，只整理事实、风险和待确认项。
3. 首期只依据当期背景和已给出的初始状态。第二期及以后，把上一期各企业决策与结果作为竞争信号，分析价格、广告、产量、人员、研发、融资等变化。
4. 生成“推荐值、单位、依据、置信度/待确认项”四列的完整决策表。
5. 在表后列出关键假设、约束校验结果，以及下一期需要继续保存的数据。

## 输出要求

默认用中文。数值建议应可直接抄入仿真系统；若当前信息不足以计算可靠数值，先输出可填部分和最少的待确认问题，不把图示值误当作已验证的最优决策。
