---
name: lead-scoring-report
description: Convert the planning package from 线索打分 into a formal 100-point scoring report for enterprise digital transformation opportunities. Use only after the starter has exposed the scoring input summary.
source: "https://github.com/zrxparley/lead-scoring"
agent_created: true
location: user
---

# Lead Scoring Report

This skill generates the formal scoring report for enterprise lead qualification.

Use it only after the discovery workflow has already surfaced:

1. 线索理解
2. 已知事实提取
3. 关键缺口与追问计划
4. 评分输入摘要

## Core scoring philosophy

This scoring model is designed for PMs supporting enterprise digital transformation solutions, not for generic B2C or SMB sales leads.

It favors:

- real business urgency
- scenario clarity
- credible sponsor and decision chain
- plausible budget path
- workable delivery conditions
- observable commitment

It penalizes:

- vague transformation slogans
- no clear owner
- no budget path
- no implementation path
- contradictory statements
- no next-step commitment

## Report positioning

The report should feel like a formal lead health-check report, not a casual assistant answer.

The final output must resemble an executive diagnostic report with:

- customer profile
- original customer demand record
- normalized demand summary
- customer-type judgement
- dimension scoring
- chart-style score presentation
- evidence statements
- final conclusion and action advice

Do not output only a score table.

## Customer-type judgement

The report must classify the opportunity into one primary type:

1. `一线招标询价型`
2. `中间商刷方案型`
3. `潜在真实合作型`

### Type definitions

#### 一线招标询价型

Typical signals:

- asks for broad quotations early
- asks for standard proposal material before problem definition is clear
- decision chain is unclear
- budget path is weak or procurement-led
- business owner engagement is low

#### 中间商刷方案型

Typical signals:

- requester is not the real end-customer owner
- repeatedly asks for proposals, decks, or quotations for collection purposes
- cannot explain the actual business workflow in detail
- has weak access to decision makers
- next steps are vague or repeatedly postponed

#### 潜在真实合作型

Typical signals:

- real business problem is concrete
- sponsor or business owner is visible
- scene, timeline, and constraints can be discussed
- budget path is plausible even if not fully approved
- there is a concrete next step such as workshop, technical alignment, or POC

### Type output rule

The report must provide:

- primary type
- confidence level: `高 / 中 / 低`
- 3-5 evidence bullets supporting the type judgement

If the evidence is mixed, state the main type first and then note the secondary risk tendency.

## 100-point scoring framework

### 1. 转型驱动力与业务紧迫性：15 分

- 是否有真实业务问题或管理压力：8 分
- 为什么是现在推进：4 分
- 不做的代价是否明确：3 分

### 2. 场景清晰度与业务价值：20 分

- 场景是否具体而非泛概念：8 分
- 使用对象和流程是否明确：6 分
- 预期价值与成功标准是否明确：6 分

### 3. 决策链与关键角色成熟度：15 分

- 发起人与 sponsor 是否明确：5 分
- 最终决策人与关键影响者是否明确：5 分
- 业务、IT、采购关系是否清楚：5 分

### 4. 预算与商务可推进性：15 分

- 是否存在预算或明确争取路径：7 分
- 预算归属与审批方式是否明确：4 分
- 商务与采购阶段是否清晰：4 分

### 5. 数据与系统落地基础：15 分

- 关键系统边界是否明确：5 分
- 数据来源、质量、权限是否具备基础：5 分
- 合规、部署、安全约束是否可判断：5 分

### 6. 交付复杂度与变革承接能力：10 分

- 跨部门协同和流程改造复杂度是否可控：5 分
- 客户是否具备内部承接资源：5 分

### 7. 行业匹配度与战略价值：5 分

- 是否符合目标行业方向或可复制战略价值：5 分

### 8. 下一步承诺与线索真实性：5 分

- 是否存在明确下一步动作：3 分
- 信息一致性和真实推进意愿：2 分

## Scoring rules

- Score only from evidence already available
- Missing information should reduce confidence and score
- Explicit contradictions must be called out
- If assumptions are required, mark them clearly

## Standardized report output contract

For consistency, always render the final report in the same section order.

Do not rename the sections.
Do not skip a required section.
If a field is unknown, say `未确认` or place it in `信息完整度声明`.

Use these formatting rules:

- Total score must be shown once in `报告首页摘要` and once in `综合评分总览`
- Customer type must be shown once in `报告首页摘要` and once in `客户类型判断`
- Every scoring dimension must include:
  - score
  - evidence
  - deduction reason
  - one-line judgement
- `关键信息不足` must never be hidden inside prose; it must be surfaced in `信息完整度声明`
- If scoring is based on incomplete information, the report must explicitly say:
  - `当前为信息不完整评分`
  - `以下维度基于假设`

## Confidence and completeness rules

### Completeness labels

Always include one completeness label in `综合评分总览`:

- `高`
- `中`
- `低`

Guidance:

- `高` = most scoring-critical fields are confirmed, and next-step action is clear
- `中` = several important fields are known, but at least 2-3 scoring-critical gaps remain
- `低` = multiple core fields are missing, especially around scenario, decision chain, or budget

### Customer-type confidence

Always state customer-type confidence in `客户类型判断`:

- `高`
- `中`
- `低`

If confidence is not high, include one sentence explaining what additional evidence would confirm or overturn the judgement.

## Chart requirement

The report must include at least two text-native chart blocks so the result still works in plain Markdown environments.

Required charts:

1. `综合评分总览`
   - show total score, recommendation level, and type judgement

2. `维度得分分布`
   - show all scoring dimensions with bar-style visualization

Use simple text bars such as:

`场景清晰度与业务价值 16/20 |████████░░|`

## Output structure

The final answer must include:

### 一、报告首页摘要

- 报告名称
- 客户名称
- 报告日期
- 总分：`X/100`
- 等级：`重点推进 / 条件推进 / 谨慎投入 / 暂缓跟进`
- 客户类型：`一线招标询价型 / 中间商刷方案型 / 潜在真实合作型`
- 结论一句话

### 二、客户基础情况

At minimum include:

- 客户名称
- 所属行业
- 企业类型或规模特征
- 对接角色
- 项目主题
- 当前推进阶段
- 信息来源说明

### 三、客户需求原始内容

Preserve the source in a concise but faithful way.

If the user provided meeting minutes, extract the original demand statements and key original expressions.

If the source is too long, summarize it into:

- 原始诉求摘录
- 原始关注点摘录
- 原始顾虑摘录

### 四、梳理后客户需求

Convert the original material into structured demand language:

- 核心业务目标
- 目标场景
- 关键使用角色
- 预期结果
- 时间要求
- 边界条件
- 当前主要障碍

### 五、客户类型判断

Must include:

- 判定类型
- 判定置信度
- 判定依据
- 反向证据或保留意见

### 六、综合评分总览

Include a text-style summary chart for:

- 总分
- 推进等级
- 客户类型
- 信息完整度

### 七、详细评分明细

For each dimension provide:

- 维度
- 满分
- 得分
- 评分依据
- 扣分原因

Each dimension should also have a short narrative judgement, not just a number.

Use this per-dimension micro-format:

- `[维度名称]（X 分）：Y 分`
  - 评分依据：
  - 扣分原因：
  - 判断：

### 八、维度得分分布图

Render all dimension scores with text bars.

### 九、关键判断陈述

Provide 3-6 evidence-based statements in formal report style.

### 十、关键风险

List the top 3-5 risks that most affect deal quality or delivery confidence.

### 十一、销售建议

Choose one clear recommendation:

- 重点推进
- 补信息后推进
- 控制投入推进
- 暂缓或降级

### 十二、下一步动作

Provide 3-5 concrete next actions.

### 十三、最终结论

Close with a formal conclusion paragraph summarizing:

- whether the lead is likely real
- whether near-term follow-up is justified
- what the decisive next validation point is

### 十四、信息完整度声明

If evidence is incomplete, explicitly list:

- 哪些维度基于假设
- 哪些问题必须在下一轮确认

If evidence is mostly complete, still include this section and write:

- 基于假设的维度：无明显基于假设的核心维度
- 下一轮必须确认的问题：如有则列出；如无则写 `无强制缺口`

## Tone

Sound like a strong enterprise presales PM or solution consultant.

Be direct, evidence-based, and calm.

Do not sound like a generic meeting assistant.

Use concise business-report wording rather than conversational chat wording.
