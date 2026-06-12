---
name: skillopt-optimizer
description: "Microsoft SkillOpt inspired PM skill optimizer — treats PM skill documents as trainable state. Runs the full training loop: rollout → reflect → aggregate → select → update → evaluate. Bounded add/delete/replace edits with validation-gated improvement. Use when the user wants to systematically improve a PM skill (SKILL.md) through iterative self-optimization cycles, or says things like 'optimize this skill', 'train this PM skill', 'make this skill better', 'run a training epoch on this skill'."
agent_created: true
location: user
source: "https://github.com/microsoft/SkillOpt"
license: MIT
---

# SkillOpt Optimizer: Train PM Skills Like Neural Networks

> Apply Microsoft SkillOpt's [self-evolving agent skill methodology](https://github.com/microsoft/SkillOpt) to your PM skills. Treat any SKILL.md as trainable state and iteratively improve it through **rollout → reflect → aggregate → select → update → evaluate** cycles, with **validation-gated** bounded edits.

## What This Does

This skill guides you through the SkillOpt training loop to optimize any PM skill document. The key insight: **a skill document is trainable text** — like neural network weights, but in natural language. A separate optimizer examines trajectories, proposes bounded edits, and only accepts changes that strictly improve held-out validation performance.

### Core Loop (One Epoch)

```
Rollout → Reflect → Aggregate → Select → Update → Evaluate
```

| Stage | What Happens | PM Context Example |
|-------|-------------|-------------------|
| **Rollout** | The agent executes tasks using the current skill | Ask the skill to produce 3 PRDs / SWOTs / user personas |
| **Reflect** | An optimizer analyzes trajectories → feedback | What worked? What was missed? Where did it go wrong? |
| **Aggregate** | Multiple trajectory reflections are combined | Merge insights across 3-5 rollouts into coherent patterns |
| **Select** | Bounded edit operations are proposed | Add a checklist item / Delete vague instruction / Replace weak example |
| **Update** | Edit accepted **only if it strictly improves** a held-out score | Run validation tasks → compare before/after quality score |
| **Evaluate** | Measure final performance against the validation gate | Final score report: did this epoch actually improve the skill? |

## When to Use

Trigger when the user wants any of:
- "Optimize / train / improve this PM skill"
- "Run a training epoch on this skill document"
- "Make this SKILL.md more effective"
- "Self-evolve this skill through iterative refinement"
- "Systematically improve a skill based on real usage data"
- "Validate that a skill change actually helps"

## How to Run the SkillOpt Training Cycle

### Phase 1: Setup

1. **Identify the target skill** — which SKILL.md do you want to optimize?
2. **Define validation tasks** — create 5-10 representative PM tasks the skill should handle:
   - **Training set (70%)**: Used for reflection and edit generation
   - **Validation set / held-out (30%)**: Used for the gate — **never seen during editing**
3. **Establish a baseline** — run the validation set against the current skill, score each result (0.0 - 1.0)

### Phase 2: Training Epoch

Run one complete epoch:

#### Step 1: Rollout
Execute the training set tasks using the current version of the skill document. Capture **full trajectories** (not just outcomes):
- What did the agent produce?
- What reasoning path did it follow?
- Where did it hesitate or go wrong?

#### Step 2: Reflect
Using an optimizer model (a separate LLM call), analyze each trajectory:
```markdown
## Reflection Template
- **What worked**: Specific instructions that led to good outputs
- **What failed**: Instructions that were confusing, missing, or counterproductive
- **Root cause**: Why did the failure happen? (ambiguous wording? missing step? wrong example?)
- **Improvement idea**: What bounded edit would fix this?
```

#### Step 3: Aggregate
Combine reflections across all training rollouts. Look for:
- **Recurring failure patterns** (top 3)
- **Recurring success patterns** (top 3) — protect these from edits
- **Gaps** — capabilities the skill should have but doesn't

#### Step 4: Select Bounded Edits
Propose 1-3 **bounded edits** using only these operations:

| Operation | Rules | Example |
|-----------|-------|---------|
| **Add** | ≤50 tokens; insert new instruction/checklist/example | Add: "Always include an explicit 'Assumptions' section" |
| **Delete** | Remove ≤30 tokens of ineffective content | Delete: "Consider market trends" (too vague) |
| **Replace** | Swap ≤60 tokens with improved version | Replace: vague instruction with structured template |

**Important**: Set a **textual learning-rate budget** — limit total changes to ~10% of the skill document per epoch. Small, safe edits compound better than big rewrites.

#### Step 5: Gate — Validate Against Held-Out
Run the candidate skill against the **held-out validation set** (tasks never used in training):
- Score each output (0.0 - 1.0) using a rubric
- Average the held-out score
- **Accept the edit ONLY if the held-out score strictly improves** over the baseline
- If score drops → **reject** the edit and log it in the **rejected-edit buffer**

#### Step 6: Evaluate & Report
```markdown
## Epoch Report
- **Skill**: [name]
- **Epoch**: [number]
- **Training score**: [before] → [after] (±Δ)
- **Held-out score**: [before] → [after] (±Δ]
- **Edits accepted**: [n] (list)
- **Edits rejected**: [n] (list, with reasons)
- **Gate verdict**: ✅ ACCEPTED / ❌ REJECTED
- **Rejected-edit buffer**: [n] stored failures (prevents repeating bad edits)
```

### Phase 3: Multi-Epoch Training

Run multiple epochs. Each epoch uses the best skill from the previous epoch.

Key mechanisms that make multi-epoch training stable:

1. **Textual learning-rate budget** — limit per-epoch change magnitude
2. **Rejected-edit buffer** — store failed edits; block them from being re-proposed
3. **Slow / Meta update** — every 3-5 epochs, do a broader "meta-reflection" on overall skill trajectory
4. **Monotonic acceptance** — never accept a regression; skill can only improve or stay flat

### Phase 4: Deploy

Once training converges (held-out score plateaus for 3+ epochs), the optimized skill artifact (`best_SKILL.md`) is ready for deployment. Typically 300-2,000 tokens.

## Skill Transfer

An optimized skill transfers across:
- **Different models** (GPT → Claude → Qwen) without re-optimization
- **Similar PM tasks** (e.g., a PRD skill partially transfers to a Feature Spec skill)
- **Different execution contexts** (direct chat → agentic loop) with minor adaptation

## Quick Start Template

```
User: "I want to optimize my create-prd skill"
You: "Great! Let's run a SkillOpt training epoch on create-prd.

Step 1: Let's set up 6 PRD tasks (4 training + 2 held-out):
- Training: [task1, task2, task3, task4]
- Held-out: [task5, task6]

Step 2: Let's establish a baseline by running the current skill...

[Proceed through the training cycle]
"

---

## ⚠️ Hard Rules

- **Validation gate is strict**: Accept edits ONLY if held-out score strictly improves. No exceptions.
- **Bounded edits only**: Never rewrite a skill from scratch. Add/delete/replace small chunks.
- **Rejected-edit buffer**: Log every rejected proposal and check it before proposing similar edits.
- **Baseline before anything**: Always establish a quantitative baseline before making changes.
- **Evidence before action**: Show the user held-out scores and exact proposed diffs before applying.
- **Backup before applying**: Always save `{skill}.bak` before overwriting.
