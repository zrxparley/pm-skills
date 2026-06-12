---
name: lead-scoring-starter
description: Main entry skill for 线索打分. Use when the user says things like /线索打分, 线索评分, 客户需求评估, 会议纪要评分, 需求调研, 预算挖掘, 决策链判断, or asks a PM-style enterprise lead qualification question. This skill must always start with a planning-first discovery workflow before any final score is produced.
source: "https://github.com/zrxparley/lead-scoring"
agent_created: true
location: user
---

# Lead Scoring Starter

This is the main routing skill for `线索打分`.

Use it whenever the user wants to assess an enterprise customer lead, prepare PM discovery questions, or convert meeting notes into a lead score.

## Strong trigger phrases

Activate this skill when the user says things like:

- `/线索打分`
- 线索评分
- 客户需求评估
- 帮我做客户调研
- 帮我挖预算
- 帮我判断客户是真是假
- 根据会议纪要打分
- 判断这个数字化项目值不值得跟
- 帮销售判断这条线索是否真实

## Entry conditions

This skill should activate for all of these:

- user enters `/线索打分`
- user gives only customer background and wants discovery guidance
- user gives a planned question list and wants optimization
- user gives meeting minutes and wants analysis plus scoring
- user gives mixed notes and wants a lead qualification judgement

## Main job

This skill is not a simple router. It is the front desk of the toolkit.

Its job is to:

- identify the input shape
- decide what is already known
- extract usable facts
- identify missing scoring-critical facts
- ask only the next best question
- build a scoring-ready summary
- hand off to the report skill only after the planning package is ready

## Mandatory planning-first rule

Never produce the final scoring report immediately on first entry.

The workflow must first surface these four user-visible gates:

1. `线索理解`
2. `已知事实提取`
3. `关键缺口与追问计划`
4. `评分输入摘要`

Only after gate 4 is visible may final scoring begin.

If the user provided rich meeting notes, gates 2-4 may be completed quickly, but they still must be visible.

## Input-shape detection

The starter should first classify the input into one of these:

1. `blank-entry`
2. `customer-brief`
3. `question-list`
4. `meeting-minutes`
5. `mixed-notes`

Definitions:

- `blank-entry`: user typed only the trigger
- `customer-brief`: company, industry, project direction, but no transcript
- `question-list`: user already wrote discovery questions and wants help refining them
- `meeting-minutes`: structured or semi-structured customer conversation notes
- `mixed-notes`: fragmented notes combining assumptions, observations, and follow-ups

## First-question policy

If the user sends only `/线索打分`, the first question should be:

- `你现在手上是只有客户背景、已经有一版调研问题，还是已经有会议纪要？`

Ask only one question at a time when needed.

## Planning targets

Before scoring, the skill should try to establish these fields:

1. `customer_profile`
   - industry
   - size
   - business model
   - current digital maturity signal

2. `opportunity_context`
   - project theme
   - business driver
   - urgency
   - timeline

3. `scenario_definition`
   - target use cases
   - user roles
   - current workflow
   - expected outcome

4. `commercial_readiness`
   - budget existence
   - budget source
   - procurement stage
   - commercial expectation

5. `decision_map`
   - sponsor
   - decision maker
   - business owner
   - IT owner
   - procurement involvement

6. `delivery_foundation`
   - system integration scope
   - data availability
   - compliance/security constraints
   - process change scope

7. `proof_of_truth`
   - evidence of real demand
   - contradictions
   - next committed action

## Conversational rules

Use natural language. Do not speak in schema names to the user.

Good question examples:

- 这次项目最初是谁推动的，业务部门还是管理层？
- 他们现在最想解决的是效率问题、收入问题，还是管理合规问题？
- 如果项目要继续推进，谁会真正拍板，谁会出预算？
- 这次一定要打通哪些系统，哪些数据是必须用到的？
- 客户有没有给出一个明确的下一步，比如技术对接、POC 或内部汇报？

Bad question patterns:

- what is your commercial_readiness
- provide delivery_foundation
- list proof_of_truth

## Routing rules by input shape

### If `customer-brief`

- summarize what is already known
- produce a focused discovery plan
- ask the next highest-value question

### If `question-list`

- evaluate whether the questions cover business, budget, decision, delivery, and truthfulness
- rewrite the questions into a better PM discovery order
- identify what is still missing

### If `meeting-minutes`

- extract facts first
- separate evidence from assumptions
- identify contradictions and missing fields
- ask the next 3-5 most important follow-up questions
- produce the scoring input summary

### If `mixed-notes`

- normalize the notes into facts, assumptions, open questions, and risks
- then continue like `meeting-minutes`

## Minimal questioning policy

If the user already provided enough evidence, do not over-ask.

Only ask follow-up questions when the missing information materially affects scoring quality in these areas:

- business urgency
- use-case clarity
- decision chain
- budget reality
- delivery feasibility
- next-step commitment

## Required pre-score output

Before calling the report phase, return:

### 一、线索理解

One-paragraph summary of what this opportunity is.

### 二、已知事实提取

List only facts supported by the user's source material.

### 三、关键缺口与追问计划

List the most important missing items and the recommended next questions.

### 四、评分输入摘要

Provide a structured summary that includes at least:

- 客户名称
- 行业
- 项目方向
- 发起背景
- 业务痛点
- 目标场景
- 紧迫性
- 时间要求
- 预算情况
- 决策链
- 采购阶段
- 系统与数据现状
- 合规与部署要求
- 主要风险
- 下一步动作

## Standardized starter output contract

For consistency, always render the pre-score package in the same order and with the same labels.

Do not improvise section names.
Do not skip empty sections.
If a field is missing, write `未确认` instead of omitting it.

Use this exact output shape:

### 一、线索理解

- 线索概述：

### 二、已知事实提取

- 已确认事实 1：
- 已确认事实 2：
- 已确认事实 3：

### 三、关键缺口与追问计划

- 关键缺口 1：
- 为什么重要：
- 建议怎么问：

- 关键缺口 2：
- 为什么重要：
- 建议怎么问：

### 四、评分输入摘要

- 客户名称：
- 行业：
- 企业类型/规模特征：
- 当前对接角色：
- 项目方向：
- 发起背景：
- 核心业务痛点：
- 目标场景：
- 关键使用角色：
- 紧迫性：
- 时间要求：
- 预算情况：
- 决策链：
- 采购阶段：
- 系统与数据现状：
- 合规与部署要求：
- 主要风险：
- 下一步动作：

### 五、当前判断

- 输入类型：
- 当前阶段：
- 当前客户类型倾向：
- 评分准备度：`可直接评分 / 补 1-2 个问题后评分 / 暂不建议评分`
- 说明：

## Standardized starter behavior by input type

### If input is `meeting-minutes`

Prefer this sequence:

1. extract facts
2. separate assumptions
3. identify the 3-5 highest-value missing items
4. produce the standardized pre-score package
5. only then decide whether scoring is ready

### If input is `customer-brief` or `question-list`

Prefer this sequence:

1. summarize what is already known
2. identify which scoring dimensions are currently unsupported
3. ask the next 1-3 highest-value discovery questions
4. produce the standardized pre-score package with `未确认` fields clearly marked

## Final handoff rule

Only after the scoring input summary is visible should the workflow produce the formal scoring report.

If major evidence is still missing, the scoring output must explicitly state:

- `当前为信息不完整评分`
- `以下维度基于假设`

## Output

Return:

1. detected input shape
2. current planning gate
3. extracted facts
4. missing information
5. next questions
6. scoring readiness

In practice, the final visible answer should follow the standardized starter output contract above rather than this terse internal list.
