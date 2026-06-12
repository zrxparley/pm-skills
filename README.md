# PM Skills 🏪

> 一站式产品管理 (PM) 技能合集，适配 **WorkBuddy**。
>
> 基于多个顶级开源 PM 技能仓库 + 自有项目技能整合而成，覆盖产品全生命周期。

## 概览

**133 个 PM 技能**，来自 7 个来源，共 18 个分类。

| 分类 | 数量 | 来源 |
|------|:---:|------|
| 🎯 **Product Discovery** | 15 | phuryn + deanpeters |
| 📋 **Product Strategy** | 13 | phuryn + deanpeters |
| 🚀 **Execution** | 19 | phuryn + deanpeters |
| 🔬 **Market Research** | 11 | phuryn + deanpeters |
| 📊 **Data Analytics** | 5 | phuryn + deanpeters |
| 🏪 **Go-to-Market** | 6 | phuryn |
| 📈 **Marketing & Growth** | 9 | phuryn + deanpeters |
| 🧰 **Toolkit & Templates** | 10 | phuryn + deanpeters |
| 🤖 **AI Shipping & AI Product** | 5 | phuryn + deanpeters |
| 🎯 **JTBD & Problem Framing** | 3 | deanpeters |
| 📊 **SaaS Finance & Metrics** | 4 | deanpeters |
| 🏆 **PM Career & Leadership** | 7 | deanpeters |
| 🔬 **Workshops & Facilitation** | 5 | deanpeters |
| 🎯 **End-to-End Workflows** | 7 | deanpeters + digidai |
| 🔬 **Industry Analysis** | 4 | industry-analyzer-skill |
| 📊 **Business Strategy & Analysis** | 8 | business-decision-tool |
| 🏆 **KPMG Strategy Framework** | 1 | kpmg-strategy-framework |
| 🎯 **Lead Scoring** | 2 | lead-scoring |
| 🏠 **pm-hub (聚合入口)** | 1 | 自定义 |

## 技能来源

| 来源 | 许可协议 | 贡献技能数 |
|------|---------|:---------:|
| [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | MIT | 68 |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 45 |
| [Digidai/Product-Manager-Skills](https://github.com/Digidai/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 1 |
| [business-decision-tool](https://github.com/zrxparley/business-decision-tool) | MIT | 11 |
| [industry-analyzer-skill](https://github.com/zrxparley/industry-analyzer-skill) | MIT | 4 |
| [lead-scoring](https://github.com/zrxparley/lead-scoring) | MIT | 2 |
| [kpmg-strategy-framework](https://github.com/zrxparley/kpmg-strategy-framework) | MIT | 1 |
| [pm-hub (自定义)](https://github.com/zrxparley/pm-skills) | MIT | 1 |

> **注**：来自 deanpeters 和 Digidai 的技能标记为 `CC BY-NC-SA 4.0`，使用时请注意非商业性要求及署名义务。自建项目来源的技能均为 MIT。

## 安装到 WorkBuddy

```bash
git clone https://github.com/zrxparley/pm-skills.git /tmp/pm-skills
cp -R /tmp/pm-skills/skills/* ~/.workbuddy/skills/
rm -rf /tmp/pm-skills
```

或在 WorkBuddy 中直接说：

> 「安装 https://github.com/zrxparley/pm-skills 这个技能」

## 使用方式

1. **直接聊**：说"帮我写个 PRD"、"做一个 SWOT 分析"——自动匹配对应技能
2. **`/pm`**：输入 `/pm` 查看完整菜单，选择方向自动路由

## 与原始仓的区别

- ✅ WorkBuddy 前端元数据适配（`agent_created: true`、`location: user`）
- ✅ 替换 `$ARGUMENTS` 为 `{user_input}`
- ✅ 新增 `/pm` 聚合入口 skill —— 133 技能智能路由
- ✅ 整合三大开源 PM 仓库 + 四个自有项目技能，去重合并
- ✅ 所有技能 `skills/` 扁平目录，即拷即用

## 许可证

- **来自 phuryn/pm-skills 的技能**：MIT License
- **来自 deanpeters 和 Digidai 的技能**：CC BY-NC-SA 4.0
- **来自自建项目的技能**：MIT License
- **pm-hub 入口 skill**：MIT License
