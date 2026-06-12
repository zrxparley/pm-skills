<p align="center">
  <img src="assets/logo.png" alt="PM Skills Logo" width="200">
</p>

<h1 align="center">PM Skills 🏪</h1>

> **WorkBuddy 的一站式产品管理技能合集** — 133 个 PM 技能，即装即用。

[![GitHub stars](https://img.shields.io/github/stars/zrxparley/pm-skills)](https://github.com/zrxparley/pm-skills)
[![License](https://img.shields.io/badge/license-MIT%20%2B%20CC%20BY--NC--SA%204.0-blue)](https://github.com/zrxparley/pm-skills)
[![Skills](https://img.shields.io/badge/skills-133-brightgreen)](https://github.com/zrxparley/pm-skills/skills)
[![WorkBuddy](https://img.shields.io/badge/WorkBuddy-ready-purple)](https://www.codebuddy.ai/docs/workbuddy/Overview)
[![中文](https://img.shields.io/badge/lang-中文-red)](README.md)
[![English](https://img.shields.io/badge/lang-English-blue)](README.en.md)

让你的 AI 助手具备产品经理的完整思维框架。从用户发现、战略规划到执行落地、上市增长——覆盖产品全生命周期。

---

## 📦 快速安装

```bash
# 一键安装所有技能
git clone https://github.com/zrxparley/pm-skills.git /tmp/pm-skills
cp -R /tmp/pm-skills/skills/* ~/.workbuddy/skills/
rm -rf /tmp/pm-skills
```

或在 WorkBuddy 中直接说：

> **「安装 https://github.com/zrxparley/pm-skills 这个技能」**

---

## 🚀 使用方式

### 方式一：自然对话

直接聊你的需求，技能自动匹配触发：

| 你说 | WorkBuddy 自动调用 |
|------|------------------|
| "帮我写个 PRD" | → `create-prd` |
| "做一个 SWOT 分析" | → `swot-analysis` |
| "设计用户访谈提纲" | → `interview-script` |
| "估算市场规模" | → `market-sizing` 或 `tam-sam-som-calculator` |
| "做用户画像" | → `user-personas` 或 `proto-persona` |
| "给我竞争对手分析" | → `competitor-analysis` |
| "排优先级" | → `prioritization-frameworks` 或 `prioritize-features` |

### 方式二：`/pm` 聚合入口

输入 **`/pm`** 查看完整技能菜单，选择方向后自动路由：

```
/pm

🎯 想做什么？
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 1. 产品发现    — brainstorm、访谈、假设验证
 2. 产品策略    — SWOT、PESTLE、商业模式
 3. 执行        — PRD、OKR、Sprint、回顾
 4. 市场研究    — 用户画像、旅程图、竞品
 5. 数据分析    — SQL、Cohort、A/B 测试
 6. GTM         — 上市策略、ICP、战卡
 7. 营销增长    — 定位、北极星指标
 8. 行业分析    — 企业调研、生态图谱
 9. SaaS 指标   — 营收、CAC、LTV
10. PM 职场     — 简历、面试、晋升
...
```

---

## 🗂️ 技能全景图

| 分类 | 数量 | 核心技能 |
|------|:---:|---------|
| 🎯 **Product Discovery** | 15 | brainstorm, OST, 假设验证, 访谈, 功能排优 |
| 📋 **Product Strategy** | 13 | SWOT, PESTLE, 五力, 商业模式, 定价策略 |
| 🚀 **Execution** | 19 | PRD, OKR, Sprint, 故事拆分, 测试场景 |
| 🔬 **Market Research** | 11 | 用户画像, 旅程图, 竞品, 市场估算 |
| 📊 **Data Analytics** | 5 | SQL, Cohort, A/B 测试, SaaS 财务指标 |
| 🏪 **Go-to-Market** | 6 | GTM 策略, ICP, 战卡, 增长飞轮 |
| 📈 **Marketing & Growth** | 9 | 定位, 北极星指标, 营销创意, 新闻稿 |
| 🧰 **Toolkit & Templates** | 10 | NDA, 隐私政策, 简历, 问题陈述 |
| 🤖 **AI Shipping & AI Product** | 5 | 文档化, 差距分析, AI 就绪度 |
| 🎯 **JTBD & Problem Framing** | 3 | JTBD 框架, 问题框架, 问题陈述 |
| 📊 **SaaS Finance & Metrics** | 4 | 营收指标, 单位经济, 财务参考 |
| 🏆 **PM Career & Leadership** | 7 | 总监/VP 转型, 面试, 高管入职 |
| 🔬 **Workshops & Facilitation** | 5 | 旅程图/故事图/定位工作坊 |
| 🎯 **End-to-End Workflows** | 7 | 发现流程, PRD 开发, 策略 session |
| 🔬 **Industry Analysis** | 4 | 头部企业, 生态图谱, 数字化方案 |
| 📊 **Business Strategy & Analysis** | 8 | BCG 矩阵, 价值链, 情景分析, 赢单分析 |
| 🏆 **KPMG Framework** | 1 | KPMG 7 心智模型 + 5 决策启发式 |
| 🎯 **Lead Scoring** | 2 | 线索打分 |
| 🏠 **pm-hub (聚合入口)** | 1 | `/pm` 路由导航 |

---

## 📜 技能来源

本仓库整合了以下项目，每个 skill 的 `SKILL.md` 前端元数据都标注了来源和许可协议：

| 来源 | 许可 | 贡献 |
|------|:----:|:----:|
| [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | MIT | 68 |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 45 |
| [Digidai/Product-Manager-Skills](https://github.com/Digidai/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 1 |
| [business-decision-tool](https://github.com/zrxparley/business-decision-tool) | MIT | 11 |
| [industry-analyzer-skill](https://github.com/zrxparley/industry-analyzer-skill) | MIT | 4 |
| [lead-scoring](https://github.com/zrxparley/lead-scoring) | MIT | 2 |
| [kpmg-strategy-framework](https://github.com/zrxparley/kpmg-strategy-framework) | MIT | 1 |
| 自定义 | MIT | 1 (pm-hub) |

> ⚠️ 来自 **deanpeters** 和 **Digidai** 的技能采用 **CC BY-NC-SA 4.0** 许可，使用时需遵守非商业性要求及署名义务。自建项目来源的技能均为 MIT。

---

## 🏗️ 仓库结构

```
pm-skills/
├── LICENSE                    # MIT（仅适用 phuryn 来源技能）
├── README.md                 # 本文件
└── skills/                   # 所有技能扁平目录
    ├── pm-hub/               # 聚合入口 ← 输入 /pm 进入
    ├── create-prd/           # 写 PRD
    ├── swot-analysis/        # SWOT 分析
    ├── jobs-to-be-done/      # JTBD 框架
    ├── kpmg-strategy-framework/  # KPMG 战略框架
    ├── ...                   # 共 133 个技能
```

每个技能对应一个目录，内含 `SKILL.md` 文件。直接复制到 `~/.workbuddy/skills/` 即可使用。

---

## 💡 亮点技能速览

### 来自 phuryn/pm-skills
| 技能 | 用途 |
|------|------|
| `opportunity-solution-tree` | Teresa Torres 机会解决方案树 |
| `interview-script` | JTBD 客户访谈脚本 |
| `create-prd` | 8 段 PRD 模板 |
| `outcome-roadmap` | 结果导向路线图 |
| `strategy-red-team` | 对抗性压力测试策略 |

### 来自 deanpeters/Product-Manager-Skills
| 技能 | 用途 |
|------|------|
| `jobs-to-be-done` | 结构化 JTBD 需求探索 |
| `press-release` | Amazon Working Backwards 新闻稿 |
| `saas-economics-efficiency-metrics` | CAC/LTV/Rule of 40 计算 |
| `altitude-horizon-framework` | PM→总监思维转型 |
| `storyboard` | 6 格叙事故事板 |
| `discovery-process` | 3-4 周完整发现流程 |

### 来自自有项目
| 技能 | 用途 |
|------|------|
| `kpmg-strategy-framework` | KPMG 7 个心智模型 |
| `bcg-growth-share-matrix` | BCG 产品组合矩阵 |
| `win-loss-analysis` | 赢单/丢单原因分析 |
| `industry-ecosystem-mapper` | 行业生态图谱绘制 |
| `lead-scoring-starter` | 线索打分 |

---

## 🔧 贡献指南

欢迎提交 Issue 或 PR 来完善技能库：

- **新增技能**：将 `SKILL.md` 放入 `skills/<技能名>/` 目录，确保前端元数据包含 `agent_created: true` 和 `location: user`
- **修正内容**：发现某个 skill 的内容有误，直接提交 PR 修正
- **更多来源**：推荐其他优秀的 PM skill 仓库

---

## 📄 许可证

- **来自 phuryn/pm-skills 的技能**：MIT License
- **来自 deanpeters 和 Digidai 的技能**：CC BY-NC-SA 4.0（每个 skill 的 SKILL.md 中标注）
- **来自自建项目的技能**：MIT License
- **pm-hub 入口 skill**：MIT License

---

<p align="center">
  <sub>Built from <a href="https://github.com/phuryn/pm-skills">phuryn/pm-skills</a> · <a href="https://github.com/deanpeters/Product-Manager-Skills">deanpeters/PM-Skills</a> · <a href="https://github.com/Digidai/Product-Manager-Skills">Digidai/PM-Skills</a> · and more.</sub>
</p>
