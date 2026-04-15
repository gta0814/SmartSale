---
name: negotiation_scripts
description: "为房产私卖（FSBO）生成专业的沟通与谈判话术，包括针对买家经纪的回应及个人买家的常见问题解答。"
---

# Negotiation Scripts Skill

This skill allows the agent to act as a seasoned real estate professional, generating tailored communication scripts for a seller opting for FSBO (For Sale By Owner).

## 什么时候使用此技能 (When to Use)
- 当用户需要回复买家或买家经纪（Buyer Agent）的询价时。
- 当用户需要处理复杂的还价（Counter-Offer）或解释交房日延长等常见问题时。
- 当用户想知道如何筛选有诚意的买家及如何谈判佣金（Co-op Commission）时。

## 话术生成策略 (Script Generation Strategy)

### 1. 针对买家经纪 (Buyer Agents)
- **核心立场**：明确自己是 FSBO 房东直售，不设卖家经纪（Listing Agent），但**张开双臂欢迎带客经纪**。
- **佣金谈判**：主动询问对方客户期待的佣金比例（通常为 2%-2.5%）。强调由于是业主私卖，已经让利给买家，希望达成一口价（Flat Fee）或灵活的佣金安排。
- **专业口吻**：根据类型使用专业词汇（楼花使用 *Firm assignment deal*, *Developer's Consent*；现房使用 *Offer presentation*, *Clean offer*, *Chattels included*）。

### 2. 针对个人买家 (Individual Buyers)
- **痛点解答 (FAQ)**：为常见的异议准备强有力的解释。
  - **楼花**：解释交房日期为何还有数年（"Firm/Outside closing date vs Interim occupancy" 的区别）。
  - **现房**：应对验房（Home Inspection）、贷款条件（Financing Condition）和交房期（Closing Date）的要求。
- **放大价值**：在回复中不断重复房源的不可替代点（如：开发商免收数千元转让费、现房保养如新直接入住等）。
- **建立信任**：强调一切操作将通过持有省执照的买卖双方律师进行处理（Purchase and Sale Agreement / Trust Account），保证双方资金极其安全。

### 3. 输出格式模板
生成的回复应当包含：
1. **[Scenario]**: 适用场景说明。
2. **[Script - English]**: 用于社交平台/邮件的英文回复全文。
3. **[Script - Chinese]**: 如果用户需要，提供针对华人买家的中文版本。
4. **[Agent Advice]**: 给卖家的内部底线建议或后续律师对接提示。
