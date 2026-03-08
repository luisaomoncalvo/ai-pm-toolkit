# Workflow: Discovery → PRD

**End-to-end workflow for shipping a well-defined feature using AI + structured PM frameworks.**

This workflow takes you from a raw idea or user signal all the way to a PRD ready for engineering kickoff. Estimated time with AI assistance: **2–4 hours** (vs. 2–3 days manually).

---

## Overview

```
Signal / Idea
    ↓
[Step 1] Frame the problem
    ↓
[Step 2] Run discovery (/discover)
    ↓
[Step 3] Map assumptions & risks
    ↓
[Step 4] Define success metrics (/north-star)
    ↓
[Step 5] Write the PRD (/write-prd)
    ↓
[Step 6] Write the spec (spec-template.md)
    ↓
[Step 7] Stakeholder alignment (/stakeholder-map)
    ↓
Engineering Kickoff
```

---

## Step 1 — Frame the Problem (15 min)

Before doing anything, write one paragraph that answers:
- What user pain are we addressing?
- What business outcome are we driving?
- What evidence do we have that this matters?
- What's the opportunity cost of not building it?

**If you can't write this clearly in 5 sentences, you're not ready for discovery.**

**Claude prompt:**
```
Help me sharpen this problem statement for a fintech PM audience.

Raw problem: [your rough description]
Evidence I have: [data points, user quotes, support tickets]
Business context: [why this matters strategically]

Write a 3-sentence problem statement: clear, specific, evidence-backed.
```

---

## Step 2 — Run Discovery (30–60 min)

Use `/discover` in the PM Skills Marketplace to run a structured discovery cycle.

The `/discover` command generates:
- Ideation across multiple solution directions
- Key assumptions behind each direction
- Experiment designs to validate the most critical assumptions
- Recommended path forward

**After `/discover`, you should have:**
- [ ] 3–5 solution directions explored
- [ ] Top 3 assumptions identified per direction
- [ ] At least 1 validation experiment designed
- [ ] A preferred direction with clear rationale

**If you did real user interviews**, synthesize them first:
```
I conducted [N] user interviews about [topic]. Here are my notes:
[paste notes]

Synthesize into: top pain points, validated assumptions, invalidated assumptions,
surprising findings, and recommended direction.
```

---

## Step 3 — Map Assumptions & Risks (20 min)

For your chosen direction, map all assumptions before building.

**Claude prompt:**
```
I'm building [feature] for [user] at a fintech company ([product type]).
Chosen direction: [describe]

Map all assumptions into:
- Desirability (do users want this?)
- Feasibility (can we build it?)
- Viability (is it good for business?)
- Regulatory/Compliance (fintech-specific)

For each: confidence level, risk if wrong, and suggested validation method.
Highlight the top 3 riskiest assumptions.
```

**Go / No-go check:**
- If a P0 assumption has Low confidence + High risk → validate before building
- If most assumptions are Medium/High confidence → proceed to metrics

---

## Step 4 — Define Success Metrics (20 min)

Use `/north-star` to define your measurement framework.

The `/north-star` command generates:
- North Star Metric for this feature
- Input metrics (leading indicators)
- Guardrail metrics (what you must not break)

**Output template:**

| Metric | Type | Definition | Current | Target | Measurement |
|--------|------|------------|---------|--------|-------------|
| [Name] | North Star | [Definition] | [X] | [Y] | Weekly |
| [Name] | Input | [Definition] | [X] | [Y] | Daily |
| [Name] | Input | [Definition] | [X] | [Y] | Daily |
| [Name] | Guardrail | [Definition] | [X] | >[Y] | Real-time |

**Fintech-specific guardrails to always consider:**
- Fraud rate
- False positive rate on risk scoring
- Compliance incident count
- Customer complaint rate
- Regulatory SLA adherence

---

## Step 5 — Write the PRD (30–45 min)

Use `/write-prd` to generate the first draft, then refine.

**Input you need ready:**
- Problem statement (from Step 1)
- Discovery findings (from Step 2)
- Chosen direction and rationale
- Success metrics (from Step 4)
- Known constraints (tech, compliance, timeline)

**After `/write-prd`, review checklist:**
- [ ] Problem is clearly stated with evidence
- [ ] Success metrics are specific and measurable
- [ ] User stories cover primary and edge-case users
- [ ] Non-functional requirements include security and compliance
- [ ] Out of scope is explicit
- [ ] Open questions are listed

**Claude critique prompt:**
```
Review this PRD and give me honest feedback. What would a skeptical
engineer, designer, or compliance officer push back on?

[paste PRD]
```

---

## Step 6 — Write the Spec (30–45 min)

The PRD is for stakeholders. The spec is for builders (Claude Code, Lovable, engineering).

Use `spec-template.md` and fill in every section.

**Key difference between PRD and spec:**

| PRD | Spec |
|-----|------|
| Answers "what and why" | Answers "what exactly and how" |
| For stakeholders and leadership | For engineers and AI tools |
| Higher level | Granular, with acceptance criteria |
| 1-3 pages | 3-8 pages |

**Tips for AI-ready specs:**
- Write acceptance criteria in Gherkin (Given/When/Then)
- Describe UI behavior precisely — don't rely on "see Figma"
- List all API dependencies and data models explicitly
- Write error messages exactly as they should appear
- Include constraints as hard requirements, not suggestions

---

## Step 7 — Stakeholder Alignment (20 min)

Use `/stakeholder-map` to identify who needs to be involved and how.

The `/stakeholder-map` command generates:
- Power × Interest grid for your stakeholders
- Communication plan (who, what, when, how)
- Risks from misaligned stakeholders

**For fintech, always include:**
- Compliance / Legal → before finalizing scope
- Risk / Fraud → before any transaction-related feature
- Finance → if revenue model changes
- Operations → if it affects support or ops workflows

**Pre-kickoff checklist:**
- [ ] Compliance signed off on regulatory requirements
- [ ] Engineering estimated and flagged blockers
- [ ] Design has reviewed UX requirements
- [ ] Leadership has approved resource allocation
- [ ] Success metrics agreed by all stakeholders

---

## Step 8 — Engineering Kickoff

**Kickoff agenda (60 min):**

1. **Context** (10 min) — PM presents problem + business case
2. **Walkthrough** (20 min) — PM walks through spec section by section
3. **Technical Q&A** (15 min) — Engineering asks clarifying questions
4. **Estimation** (10 min) — High-level effort and timeline
5. **Open questions** (5 min) — Log and assign owners

**Deliverables from kickoff:**
- [ ] Confirmed timeline
- [ ] Open questions assigned with deadlines
- [ ] Tech lead owns the technical design
- [ ] PM owns keeping spec updated during build

---

## Worked Example — Instant Payments Feature

Here's how this workflow applied to a real fintech feature: **Instant Account-to-Account Transfers**.

**Step 1 — Problem framing:**
> Users of our neobank frequently abandon the transfer flow when they see 1-3 business day settlement times. 34% drop-off at the settlement screen. Competitors (Revolut, N26) offer instant transfers. Estimated revenue impact: $2.1M ARR from retained users.

**Step 2 — Discovery output:**
- Direction chosen: Instant transfers via real-time payment rails (FPS/SEPA Instant)
- Key assumption: Users will pay a small fee (€0.50) for instant settlement
- Validation: A/B test showing fee option in current flow → 2-week sprint

**Step 3 — Top risks:**
1. Regulatory: real-time rails have new AML obligations → compliance review needed (High risk, Low confidence)
2. Technical: fraud detection latency must be <500ms for instant auth (High risk, Medium confidence)
3. Business: fee revenue offsets infrastructure cost (Medium risk, Medium confidence)

**Step 4 — Metrics:**
- North Star: Transfers completed per active user per month
- Input: Instant transfer adoption rate (target: 40% of eligible transfers)
- Guardrail: Fraud rate must stay below 0.1% of transaction volume

**Step 5–6 — PRD + Spec:** Written using templates, reviewed by compliance, approved in 3 days.

**Step 7 — Stakeholders:** Compliance (approve), Risk (sign off on fraud controls), Finance (validate fee model), Ops (update support scripts).

**Result:** Feature shipped in 6 weeks. Instant transfer adoption hit 38% in month 1. Transfer abandonment dropped from 34% to 11%.

---

## Time Summary

| Step | Time with AI | Time without AI |
|------|-------------|-----------------|
| Problem framing | 15 min | 30–60 min |
| Discovery | 30–60 min | 3–5 days (interviews + synthesis) |
| Assumption mapping | 20 min | 2–3 hours |
| Metrics definition | 20 min | 1–2 hours |
| PRD | 30–45 min | 1–2 days |
| Spec | 30–45 min | 1 day |
| Stakeholder alignment | 20 min | 2–4 hours |
| **Total** | **~3–4 hours** | **~2–3 weeks** |

---

*Part of [ai-pm-toolkit](https://github.com/luisaomoncalvo/ai-pm-toolkit) · Luis Moncalvo · Senior PM · Fintech*
