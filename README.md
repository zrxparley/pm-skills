# PM Skills 🏪

> 一站式产品管理 (PM) 技能合集，适配 **WorkBuddy**。
>
> 基于多个顶级开源 PM 技能仓库整合而成，覆盖产品全生命周期。

## 概览

**114+ 个 PM 技能**，来自三大开源仓库，共 14 个分类。

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
| **🏠 pm-hub (聚合入口)** | 1 | 自定义 |

## 技能来源

本仓库整合了以下开源项目：

| 来源 | 许可协议 | 贡献技能数 |
|------|---------|:---------:|
| [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | MIT | 68 |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 45 |
| [Digidai/Product-Manager-Skills](https://github.com/Digidai/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 1 (pm-operator-digidai) |

> **注**：来自 deanpeters 和 Digidai 的技能标记为 `CC BY-NC-SA 4.0`，使用时请注意非商业性要求及署名义务。详细信息见各 skill 的 SKILL.md 前端元数据。

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

## 与原版的区别

- ✅ WorkBuddy 前端元数据适配（`agent_created: true`、`location: user`）
- ✅ 替换 `$ARGUMENTS` 为 `{user_input}`
- ✅ 新增 `/pm` 聚合入口 skill —— 114+ 技能智能路由
- ✅ 整合三大 PM 技能仓库，去重合并
- ✅ 所有技能 `skills/` 扁平目录，即拷即用

## 许可证

- **来自 phuryn/pm-skills 的技能**：MIT License
- **来自 deanpeters 和 Digidai 的技能**：CC BY-NC-SA 4.0（每个 skill 的 SKILL.md 前端元数据中标注了 license 和 source 字段）
- **pm-hub 入口 skill**：MIT License
