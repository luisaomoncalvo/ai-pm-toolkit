# 🧰 AI PM Toolkit

My personal stack for running AI-powered product management workflows. Built around Claude, Spec-Driven Development, and structured PM frameworks.

This is a living document. I update it as my workflow evolves.

---

## 🛠️ Core Stack

| Tool | What I use it for |
|------|-------------------|
| Claude Cowork | Autonomous desktop agent for complex PM tasks |
| Claude Code | Spec-to-code execution, agentic workflows |
| Lovable | Rapid prototyping from specs |
| PM Skills Marketplace | Structured PM frameworks inside Claude |
| MCP (Model Context Protocol) | Connecting Claude to GitHub, Gmail, Calendar |
| Figma | Design & wireframing |
| Mixpanel / Looker | Analytics & metrics |

---

## ⚡ Spec-Driven Development

My core methodology for shipping faster with AI.

The idea: Instead of jumping straight to building, I write a detailed spec first — covering the problem, user stories, acceptance criteria, edge cases, and technical constraints. Then I hand that spec to an AI tool (Claude Code, Lovable) to generate production-ready code.

**Why it works:**
- Forces clarity before execution
- AI generates better output with more context
- Reduces back-and-forth and rework
- Turns product ideas into working software in hours, not weeks

**My spec template:**

```markdown
## Feature: [name]

### Problem
[What problem does this solve and for whom?]

### Goals
[What does success look like? Which metrics move?]

### User Stories
- As a [user], I want to [action] so that [benefit]

### Acceptance Criteria
- Given / When / Then

### Edge Cases
- [List edge cases and how to handle them]

### Out of Scope
- [What we're explicitly NOT building]

### Open Questions
- [Unresolved decisions]
```

---

## 🔌 PM Skills Marketplace

I use the PM Skills Marketplace — 65+ structured PM workflows built into Claude.

**Installed plugins and how I use them:**

| Command | What it does | When I use it |
|---------|--------------|---------------|
| `/discover` | Full discovery cycle: ideation → assumptions → experiments | Starting a new feature or product |
| `/write-prd` | 8-section PRD from a feature idea | Before any engineering kickoff |
| `/strategy` | 9-section Product Strategy Canvas | Quarterly planning |
| `/plan-launch` | GTM from beachhead segment to launch plan | Pre-launch preparation |
| `/north-star` | North Star Metric + input metrics | Setting up measurement |
| `/analyze-test` | A/B test analysis with statistical significance | Post-experiment review |
| `/stakeholder-map` | Power × Interest grid + communication plan | Navigating complex orgs |
| `/pre-mortem` | Risk analysis before launching | Before any major release |
| `/review-resume` | PM resume review against best practices | Career toolkit |

---

## 🤖 AI Prompts

See `AI-PROMPTS-FOR-PMS.md` for my full collection of prompts organized by category:

- PRD & Specs
- Discovery & User Research
- Prioritization & Roadmap
- Tickets & User Stories
- Stakeholder Communication
- Metrics & OKRs
- Competitive Analysis
- Fintech-Specific

---

## 🔗 MCP Connections

MCP (Model Context Protocol) lets Claude connect directly to external tools. My current setup:

| MCP Server | What Claude can do |
|------------|-------------------|
| GitHub | Read/write repos, create files, manage issues |
| Gmail | Draft and read emails |
| Google Calendar | Check schedule, create events |

---

## 📁 Repo Structure

```
ai-pm-toolkit/
├── README.md                  ← This file
├── AI-PROMPTS-FOR-PMS.md      ← 30+ prompts by category
├── spec-template.md           ← My Spec-Driven Development template
└── workflows/
    └── discovery-to-prd.md   ← End-to-end workflow example
```

---

## 🔍 How This Fits My Workflow

```
Idea → /discover → /write-prd → Spec → Claude Code / Lovable → Working prototype
                                  ↓
                            /stakeholder-map → Alignment
                                  ↓
                            /plan-launch → GTM
                                  ↓
                            /north-star → Measurement
```

---

*Maintained by Luis Moncalvo · Senior PM · Fintech · AI Builder*
