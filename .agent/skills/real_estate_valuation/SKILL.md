---
name: real_estate_valuation
description: "提供房产估值与定价策略，特别是针对多伦多地区的楼花转让（Assignment Sales）和现房出售（Resale）。"
---

# Real Estate Valuation Skill

This skill enables the agent to evaluate and price real estate properties, with a strong focus on assignment sales in the GTA (Greater Toronto Area).

## 什么时候使用此技能 (When to Use)
- 当用户询问某个房产（现房或楼花）的合理定价时。
- 当用户提供财务数据（如原始合同价或当前买入成本）并希望制定“急需套现”或“追求利润”的挂牌叫价（Asking Price）时。
- 当需要评估车位（Parking）、储物间（Locker）或房屋升级（Upgrades）对整体价格的影响时。

## 估值模型与执行步骤 (Valuation Model & Execution)

### 1. 核心数据解析
你需要从用户输入或 `property_details.md` 中提取以下数据并**判断房产类型（期房/现房）**：
- 房产类型：楼花转让（Assignment Sale）还是现房/二手房（Resale）？
- 房产位置（如：Etobicoke, Downtown Toronto, Markham等）
- 房产状态与类型（如：Condo, Townhouse, Detached；临近入住/已入住）
- 户型与硬件参数（几室几卫，层数，朝向，地块大小 Lot Size 若为 House）
- **附属资产与卖点**：是否带车位（Parking）、Locker、近期翻新（Renovations/Upgrades）
- **价格数据**：
  - 若为楼花：原始合同价（Original Purchase Price）、已付定金（Deposit Paid）、开发商转让费（Assignment Fee）
  - 若为现房：当前市场估值基准、未偿还贷款（Mortgage Balance, 若提供）

### 2. 市场基准线设定 (Market Baseline)
- 通过 `search_web` 搜索对应区域同类型房产（现房及近期成交的楼花转让）的市场均价。
- **调整项（Adjustments）**：
  - 加分项：带车位（+$50k-$70k）、无转让费（+$5k-$10k）、高楼层无遮挡（+$10k-$20k）、著名开发商。
  - 减分项：低楼层、奇葩户型、无车位一室、高额开发商转让费。

### 3. 定价策略输出 (Pricing Strategy Output)
根据用户的出售动机（Motivation）和房产类型，给出具体的叫价建议：
- **急售套现 (Urgent Liquidation)**：
  - 楼花：建议采取“原价平转（At Pars）”甚至亏本策略，或免转让费以求快速找回定金。
  - 现房：建议定价低于周边近期真实成交价 (Recent Sold Comparables) 的 3%-5%，或设定一个诱导性低价（Underpricing）吸引多方竞价（Multiple Offers / Bidding War）。
- **利润最大化 (Profit Maximization)**：建议定价在市场公允价值的上限区间，并预留 2%-3% 的议价空间。
- **财务清晰度**：必须明确向用户列出：
  - 楼花买家接手时所需的垫资总额（已付定金总额 + 原价与叫价之间的差价利润）。
  - 现房买家的预计首付要求和市场流动性评估。
