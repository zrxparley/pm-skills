---
name: skillopt-sleep
description: "Microsoft SkillOpt-Sleep adapted for WorkBuddy — offline self-evolution through a 'sleep cycle'. Harvests past PM skill usage sessions, mines recurring tasks, replays offline, consolidates validated improvements behind a held-out gate, and stages proposals for review. Use when the user wants their PM skills to self-improve through nightly/offline consolidation cycles, or says things like 'make my skills learn from usage', 'run a sleep cycle', 'consolidate what you learned', 'self-improve over time'."
agent_created: true
location: user
source: "https://github.com/microsoft/SkillOpt"
license: MIT
---

# SkillOpt-Sleep: Offline Self-Evolution for PM Skills

> Give your PM skills a **sleep cycle**. While you're away, it reviews past PM skill usage, re-runs recurring tasks, and consolidates what it learns into **validated, gated improvements** to your skills. Your skills get measurably better the more you use them — no prompt-engineering required.

It synthesizes three powerful ideas:

| Idea | Contribution |
|------|-------------|
| **SkillOpt** | Skill document = trainable text; bounded add/delete/replace edits; **held-out gate** keeps only changes that help |
| **Claude Dreams / WorkBuddy offline consolidation** | Review past sessions; never mutate input; output reviewed then adopted |
| **Agent sleep** | Periodic offline replay turns short-term usage into long-term skill improvement |

## When to Use

Trigger when the user wants any of:
- "Make my PM skills learn from how I use them"
- "Make my skills better the more I use them"
- "Run a sleep / dream / offline consolidation cycle"
- "Review my past PM skill usage and suggest improvements"
- "Self-evolve my skills based on my work history"
- "Schedule nightly skill improvement"
- "Adopt a staged skill proposal"

## The Sleep Cycle (Six Stages)

```
Harvest → Mine → Replay → Consolidate → Gate → Stage → Adopt
```

### Stage 1: Harvest 📡
Read the user's **past PM skill usage history** from WorkBuddy sessions or the `.workbuddy/memory/` directory. This is **read-only** — nothing is modified.

What to harvest:
- `.workbuddy/memory/YYYY-MM-DD.md` — daily work logs (which skills were used, what tasks were done)
- `.workbuddy/memory/MEMORY.md` — project notes and conventions
- Any available session transcripts or skill invocation records

**Output**: Session digests — structured summaries of what skills were invoked and how well they performed.

### Stage 2: Mine ⛏️
From the harvested session digests, identify **recurring tasks**, **usage patterns**, and **pain points**:

```markdown
## Mining Results
- **Most-used skills**: [create-prd: 12x, swot-analysis: 8x, user-stories: 6x]
- **Recurring task types**: [Writing PRDs for mobile features, Competitive analysis for SaaS tools]
- **Identified pain points**: [PRD always misses success metrics, SWOT lacks actionable recommendations]
- **User preferences detected**: [Prefers quantitative data over qualitative, likes concise bullet-point format]
- **New task types**: [Tasks the user does that no existing skill covers well]
```

### Stage 3: Replay 🔄
Re-run the recurring tasks **offline** using the **current** versions of the relevant PM skills:

1. Select 3-5 representative tasks from the mined patterns
2. Run each task against the current skill
3. Score each outcome (0.0 - 1.0) on a rubric:
   - **Completeness**: Did it cover all necessary aspects?
   - **Accuracy**: Was the output correct and relevant?
   - **Actionability**: Can the user act on the output?
   - **User-friendliness**: Is the output well-structured and clear?

**Output**: Baseline scores for the current skill versions.

### Stage 4: Consolidate 🧠
This is the core optimization step:

1. **Reflect** — analyze the replay trajectories. What went wrong? What succeeded?
2. **Propose bounded edits** — for each skill, propose 1-3 small, targeted edits:
   - **Add**: Insert new instructions (e.g., "Always include a 'Success Metrics' section")
   - **Delete**: Remove ineffective instructions (e.g., delete vague "Consider user needs")
   - **Replace**: Swap weak content with stronger alternatives
3. **Gate on held-out tasks** — use a separate set of tasks (never seen during reflection) to validate each edit
4. **Accept only if strictly improves** — the held-out score must go up; flat or down = rejection

**The rejected-edit buffer**: Log every rejected proposal with its failure mode, and check it before proposing similar edits in future cycles.

### Stage 5: Stage 📋
Write the proposed skill improvements into a staging area:
```
.workbuddy/skillopt-staging/{date}/
├── proposed_SKILL.md        # New skill content
├── diff.md                  # What changed (before/after)
├── scores.md                # Held-out baseline → candidate scores
├── report.md                # Full sleep cycle report
└── backup/                  # Previous version backup
```

**Nothing live changes at this point.** The proposal is staged for user review.

### Stage 6: Adopt ✅
The user reviews the staged proposal and decides:
- `/sleep adopt` → apply the changes (with automatic backup of previous versions)
- `/sleep reject` → discard the proposal
- `/sleep modify` → manually adjust before adopting

## How to Drive It

### On-Demand Sleep Cycle

```
User: "Run a sleep cycle on my PM skills"
You: "Starting the SkillOpt-Sleep cycle...

Step 1: Harvesting PM skill usage from your work logs...
  → Found 23 skill invocations across 5 sessions
  → Top skills: create-prd (8), swot-analysis (5), user-stories (4)

Step 2: Mining recurring patterns...
  → Identified 3 recurring task types
  → Found 2 pain points in PRD skill

Step 3: Replaying tasks offline...
  → Baseline scores: PRD 0.65, SWOT 0.72

Step 4: Consolidating improvements...
  → Proposed 2 bounded edits for create-prd
  → Held-out gate: 0.65 → 0.82 ✓ ACCEPTED

Step 5: Staging proposal...
  → Staged at .workbuddy/skillopt-staging/2026-06-12/

Step 6: Ready for review!
  → Run `/sleep view` to see the proposed changes
  → Run `/sleep adopt` to apply them
```

### `/sleep` Commands

| Command | Action |
|---------|--------|
| `/sleep run` | Full cycle: harvest → mine → replay → consolidate → gate → stage |
| `/sleep dry-run` | Safe preview: what it would learn, no changes staged |
| `/sleep status` | Show past sleep cycles + latest staged proposal |
| `/sleep view` | Show the latest staged proposal (diff, scores, report) |
| `/sleep adopt` | Apply staged proposal to skills (with backup) |
| `/sleep reject` | Discard staged proposal |
| `/sleep schedule` | Set up recurring nightly sleep cycle |

### Scheduled Nightly Cycle

For continuous self-improvement, the sleep cycle can be scheduled:

```
/sleep schedule
  → Recommend: nightly at 2 AM
  → Creates a cron job / automation that runs the sleep cycle
  → You review and adopt in the morning
```

## Validation Proof

To demonstrate that SkillOpt-Sleep actually improves skills:

```markdown
## Held-out Score Progression

| Cycle | Skill | Baseline | Candidate | Gate | Accepted? |
|-------|-------|:--------:|:---------:|:----:|:---------:|
| 1 | create-prd | 0.65 | 0.82 | ⬆ +0.17 | ✅ |
| 2 | create-prd | 0.82 | 0.88 | ⬆ +0.06 | ✅ |
| 3 | create-prd | 0.88 | 0.85 | ⬇ -0.03 | ❌ (rejected) |
| 1 | swot-analysis | 0.72 | 0.79 | ⬆ +0.07 | ✅ |
```

The gate ensures **monotonic improvement**: skills can only get better or stay the same, never regress.

## Safety Rules

- **Read-only harvest**: Session logs are read, never modified
- **Staged, never auto-applied**: Proposals always wait for user review
- **Backup before adopt**: Every adopt creates a `.bak` backup of the previous skill
- **Token/task budget**: Never replay more than 10 tasks or generate more than 5 edits per cycle
- **No secrets**: Redact any personally identifiable information from session digests
- **Evidence before adoption**: Always show held-out scores and exact proposed diffs
