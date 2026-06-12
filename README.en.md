<p align="center">
  <img src="assets/logo.png" alt="PM Skills Logo" width="200">
</p>

<h1 align="center">PM Skills 🏪</h1>

> **One-stop Product Management skill collection for WorkBuddy** — 135 PM skills, ready to use.

[![GitHub stars](https://img.shields.io/github/stars/zrxparley/pm-skills)](https://github.com/zrxparley/pm-skills)
[![License](https://img.shields.io/badge/license-MIT%20%2B%20CC%20BY--NC--SA%204.0-blue)](https://github.com/zrxparley/pm-skills)
[![Skills](https://img.shields.io/badge/skills-135-brightgreen)](https://github.com/zrxparley/pm-skills/skills)
[![WorkBuddy](https://img.shields.io/badge/WorkBuddy-ready-purple)](https://www.codebuddy.ai/docs/workbuddy/Overview)
[![中文](https://img.shields.io/badge/lang-中文-red)](README.md)
[![English](https://img.shields.io/badge/lang-English-blue)](README.en.md)

Empower your AI assistant with a full PM mindset — from product discovery and strategy to execution, launch, and growth.

---

## 📦 Quick Install

```bash
git clone https://github.com/zrxparley/pm-skills.git /tmp/pm-skills
cp -R /tmp/pm-skills/skills/* ~/.workbuddy/skills/
rm -rf /tmp/pm-skills
```

Or just say this in WorkBuddy:

> **"Install the skills from https://github.com/zrxparley/pm-skills"**

---

## 🚀 How to Use

### Method 1: Natural Conversation

Just talk about what you need — the right skill auto-matches:

| You say | WorkBuddy invokes |
|---------|------------------|
| "Write a PRD for me" | → `create-prd` |
| "Run a SWOT analysis" | → `swot-analysis` |
| "Design a customer interview guide" | → `interview-script` |
| "Estimate market size" | → `market-sizing` or `tam-sam-som-calculator` |
| "Create user personas" | → `user-personas` or `proto-persona` |
| "Analyze competitors" | → `competitor-analysis` |
| "Prioritize my backlog" | → `prioritization-frameworks` or `prioritize-features` |

### Method 2: `/pm` Hub Command

Type **`/pm`** to browse the full skill menu and auto-navigate:

```
/pm

🎯 What do you want to do?
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 1. Product Discovery    — brainstorm, interviews, hypothesis testing
 2. Product Strategy     — SWOT, PESTLE, business model canvas
 3. Execution            — PRD, OKR, Sprint, retro, user stories
 4. Market Research      — personas, journey maps, competitive analysis
 5. Data Analytics       — SQL, cohort, A/B testing
 6. Go-to-Market         — launch strategy, ICP, battlecards
 7. Marketing & Growth   — positioning, north star metric
 8. Industry Analysis    — enterprise research, ecosystem mapping
 9. SaaS Metrics         — revenue, CAC, LTV
10. PM Career            — resume, interviews, promotion
...
```

---

## 🗂️ Skill Panorama

| Category | Count | Key Skills |
|----------|:-----:|-----------|
| 🎯 **Product Discovery** | 15 | brainstorm, OST, assumptions, interviews, prioritization |
| 📋 **Product Strategy** | 13 | SWOT, PESTLE, Five Forces, business model, pricing |
| 🚀 **Execution** | 19 | PRD, OKR, Sprint, story splitting, test scenarios |
| 🔬 **Market Research** | 11 | personas, journey maps, competitive research, market sizing |
| 📊 **Data Analytics** | 5 | SQL, cohort, A/B testing, SaaS financial metrics |
| 🏪 **Go-to-Market** | 6 | GTM strategy, ICP, battlecards, growth loops |
| 📈 **Marketing & Growth** | 9 | positioning, north star, marketing ideas, press release |
| 🧰 **Toolkit & Templates** | 10 | NDA, privacy policy, resume review, problem statements |
| 🤖 **AI Shipping & AI Product** | 5 | docs, gap analysis, AI readiness assessment |
| 🎯 **JTBD & Problem Framing** | 3 | JTBD framework, problem framing canvas |
| 📊 **SaaS Finance & Metrics** | 4 | revenue metrics, unit economics, finance quickref |
| 🏆 **PM Career & Leadership** | 7 | Director/VP transition, interviews, exec onboarding |
| 🔬 **Workshops & Facilitation** | 5 | journey/story-mapping/positioning workshops |
| 🎯 **End-to-End Workflows** | 7 | discovery process, PRD development, strategy session |
| 🔬 **Industry Analysis** | 4 | top enterprise, ecosystem map, digital solutions |
| 📊 **Business Strategy & Analysis** | 8 | BCG matrix, value chain, scenario analysis, win/loss |
| 🏆 **KPMG Framework** | 1 | KPMG 7 mental models + 5 decision heuristics |
| 🎯 **Lead Scoring** | 2 | lead scoring starter & report |
| 🏠 **pm-hub (entry hub)** | 1 | `/pm` routing navigation |

---

## 📜 Skill Sources

Every skill's `SKILL.md` frontmatter is annotated with its source and license:

| Source | License | Contributed |
|--------|:------:|:----------:|
| [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | MIT | 68 |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 45 |
| [Digidai/Product-Manager-Skills](https://github.com/Digidai/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 1 |
| [business-decision-tool](https://github.com/zrxparley/business-decision-tool) | MIT | 11 |
| [industry-analyzer-skill](https://github.com/zrxparley/industry-analyzer-skill) | MIT | 4 |
| [lead-scoring](https://github.com/zrxparley/lead-scoring) | MIT | 2 |
| [kpmg-strategy-framework](https://github.com/zrxparley/kpmg-strategy-framework) | MIT | 1 |
| Custom | MIT | 1 (pm-hub) |

> ⚠️ Skills from **deanpeters** and **Digidai** use **CC BY-NC-SA 4.0** — non-commercial use only, with attribution required. All self-built project skills are MIT.

---

## 🏗️ Repository Structure

```
pm-skills/
├── LICENSE                    # MIT (applies only to phuryn-sourced skills)
├── README.md                 # This file (Chinese)
├── README.en.md              # English version
└── skills/                   # All skills in flat directory
    ├── pm-hub/               # Entry hub ← type /pm to use
    ├── create-prd/           # Write PRDs
    ├── swot-analysis/        # SWOT analysis
    ├── jobs-to-be-done/      # JTBD framework
    ├── kpmg-strategy-framework/  # KPMG strategy framework
    ├── ...                   # 135 skills total
```

Each skill is a directory containing a single `SKILL.md`. Just copy to `~/.workbuddy/skills/` to use.

---

## 💡 Highlight Skills

### From phuryn/pm-skills
| Skill | What it does |
|-------|-------------|
| `opportunity-solution-tree` | Teresa Torres' Opportunity Solution Tree |
| `interview-script` | JTBD customer interview script |
| `create-prd` | 8-section PRD template |
| `outcome-roadmap` | Outcome-focused roadmap |
| `strategy-red-team` | Adversarial strategy stress-testing |

### From deanpeters/Product-Manager-Skills
| Skill | What it does |
|-------|-------------|
| `jobs-to-be-done` | Structured JTBD exploration |
| `press-release` | Amazon Working Backwards press release |
| `saas-economics-efficiency-metrics` | CAC/LTV/Rule of 40 calculations |
| `altitude-horizon-framework` | PM→Director mindset transition |
| `storyboard` | 6-frame narrative storyboard |
| `discovery-process` | 3-4 week complete discovery cycle |

### From own projects
| Skill | What it does |
|-------|-------------|
| `kpmg-strategy-framework` | KPMG 7 mental models |
| `bcg-growth-share-matrix` | BCG product portfolio matrix |
| `win-loss-analysis` | Deal win/loss reason analysis |
| `industry-ecosystem-mapper` | Industry ecosystem mapping |
| `lead-scoring-starter` | Lead qualification scoring |

---

## 🔧 Contributing

PRs and Issues are welcome!

- **Add a skill**: Place `SKILL.md` in `skills/<skill-name>/`, ensure frontmatter includes `agent_created: true` and `location: user`
- **Fix content**: Spot an error in a skill? Submit a fix PR
- **More sources**: Recommend other great PM skill repos

---

## 📄 License

- **phuryn/pm-skills sourced skills**: MIT License
- **deanpeters and Digidai sourced skills**: CC BY-NC-SA 4.0 (annotated per-skill SKILL.md)
- **Self-built project skills**: MIT License
- **pm-hub entry skill**: MIT License

---

<p align="center">
  <sub>Built from <a href="https://github.com/phuryn/pm-skills">phuryn/pm-skills</a> · <a href="https://github.com/deanpeters/Product-Manager-Skills">deanpeters/PM-Skills</a> · <a href="https://github.com/Digidai/Product-Manager-Skills">Digidai/PM-Skills</a> · and more.</sub>
</p>
