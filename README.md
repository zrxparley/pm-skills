# PM Skills 🏪

> 基于 [phuryn/pm-skills](https://github.com/phuryn/pm-skills) 改编，适配 **WorkBuddy** 的 69 个产品管理技能合集。

## 概览

一站式产品管理技能包，覆盖产品全生命周期——从发现、策略、执行到上市、增长。每个技能都是一个独立的 `SKILL.md`，在 WorkBuddy 中根据你的对话自动匹配触发。

## 🗂️ 技能分类

| 分类 | 数量 | 覆盖领域 |
|------|:---:|---------|
| 🎯 **Product Discovery** | 13 | brainstorm、访谈、假设验证、OST、功能优先级 |
| 📋 **Product Strategy** | 12 | SWOT、PESTLE、波特五力、商业模式、定价策略 |
| 🚀 **Execution** | 16 | PRD、OKR、Sprint、回顾、发布、红队测试 |
| 🔬 **Market Research** | 7 | 用户画像、旅程图、竞品分析、市场估算 |
| 📊 **Data Analytics** | 3 | SQL、Cohort、A/B 测试 |
| 🏪 **Go-to-Market** | 6 | GTM、ICP、战卡、增长飞轮 |
| 📈 **Marketing & Growth** | 5 | 定位、北极星指标、营销创意 |
| 🧰 **Toolkit** | 4 | NDA、隐私政策、简历评审、语法检查 |
| 🤖 **AI Shipping** | 2 | 代码文档化、实现差距分析 |
| **🏠 pm-hub (聚合入口)** | 1 | 输入 `/pm` 浏览所有技能并路由导航 |

**总计：69 个技能**

## 安装到 WorkBuddy

### 方式一：克隆到 skills 目录

```bash
# 将所有技能安装到 WorkBuddy 用户技能目录
git clone https://github.com/zrxparley/pm-skills.git /tmp/pm-skills
cp -R /tmp/pm-skills/skills/* ~/.workbuddy/skills/
rm -rf /tmp/pm-skills
```

### 方式二：选择安装

```bash
# 只安装你需要的技能
cp -R ~/pm-skills/skills/create-prd ~/.workbuddy/skills/
cp -R ~/pm-skills/skills/swot-analysis ~/.workbuddy/skills/
# ...
```

### 方式三：在 WorkBuddy 中说这句话

> 「安装 https://github.com/zrxparley/pm-skills 这个技能」

## 使用方式

安装后，WorkBuddy 会自动识别这些技能。你可以：

1. **直接聊**：说"帮我写个 PRD"、"做一个 SWOT 分析"——自动匹配对应技能
2. **用 `/pm`**：输入 `/pm` 查看完整菜单，选择方向自动路由
3. **用 `/pm-hub`**：同上

## 与原版的区别

本仓库在 [phuryn/pm-skills](https://github.com/phuryn/pm-skills) 基础上做了以下适配：

- ✅ 添加 `agent_created: true` / `location: user` 前端元数据（WorkBuddy 兼容）
- ✅ 替换 `$ARGUMENTS` 为 `{user_input}`（WorkBuddy 变量语法）
- ✅ 新增 `/pm` 聚合入口 skill（pm-hub）——带智能路由表
- ✅ 所有技能直接放在 `skills/` 扁平目录下，即拷即用

## 许可证

MIT License — 基于 [phuryn/pm-skills](https://github.com/phuryn/pm-skills) (MIT) 改编。
