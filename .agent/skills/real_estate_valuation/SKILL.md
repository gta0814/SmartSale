---
name: real_estate_valuation
description: "提供房产估值与定价策略，特别是针对多伦多地区的楼花转让（Assignment Sales）和现房出售（Resale）。"
---

# Real Estate Valuation Skill

This skill enables the agent to evaluate and price real estate properties, with a strong focus on assignment sales in the GTA (Greater Toronto Area).

## 什么时候使用此技能 (When to Use)
- 当用户询问某个楼花转让项目的合理定价时。
- 当用户提供原始购房合同价（Original Purchase Price）并希望制定“急需套现”或“追求利润”的转让叫价（Asking Price）时。
- 当需要评估车位（Parking）或储物间（Locker）对整体转让价格的影响时。

## 估值模型与执行步骤 (Valuation Model & Execution)

### 1. 核心数据解析
你需要从用户输入中提取以下数据：
- 房产位置（如：Etobicoke, Downtown Toronto, Markham等）
- 开发商名称及项目状态（如：Lanterra, 临近入住/已入住）
- 户型参数（几室几卫，层数，朝向）
- **附属资产**：是否带车位（Parking）、Locker
- **价格数据**：原始合同价（Original Purchase Price）、已付定金（Deposit Paid）、开发商转让费（Assignment Fee）

### 2. 市场基准线设定 (Market Baseline)
- 通过 `search_web` 搜索对应区域同类型房产（现房及近期成交的楼花转让）的市场均价。
- **调整项（Adjustments）**：
  - 加分项：带车位（+$50k-$70k）、无转让费（+$5k-$10k）、高楼层无遮挡（+$10k-$20k）、著名开发商。
  - 减分项：低楼层、奇葩户型、无车位一室、高额开发商转让费。

### 3. 定价策略输出 (Pricing Strategy Output)
根据用户的出售动机（Motivation），给出具体的叫价建议：
- **急售套现 (Urgent Liquidation)**：建议定价等于或微低于当前市场公允价值，甚至采用“原价平转（At Pars）”策略（即 Asking Price = Original Purchase Price），以确保快速找回定金。
- **利润最大化 (Profit Maximization)**：建议定价在市场公允价值的上限区间，并预留 2%-3% 的议价空间。
- 必须明确向用户列出：买家接手时需要支付给卖家的首付款总额（通常 = 已付定金总额 + 原价与叫价之间的差价利润）。
