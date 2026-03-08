# Spec Template — Spec-Driven Development

Use this template before handing off any feature to Claude Code, Lovable, or engineering. The more context you provide, the better the output.

**How to use:**
1. Duplicate this file and rename it to `spec-[feature-name].md`
2. Fill in every section — leave nothing blank, write "N/A" if truly not applicable
3. Share the completed spec with Claude Code or your engineering team
4. Update the spec as decisions are made (treat it as a living doc during build)

---

## Feature: [Feature Name]

**Status:** `Draft` / `In Review` / `Approved` / `In Build` / `Shipped`
**Author:** [Your name]
**Last updated:** [Date]
**Stakeholders:** [PM, Eng Lead, Design, Compliance, etc.]
**Target release:** [Quarter or sprint]

---

## 1. Problem

> What problem does this solve, for whom, and why does it matter now?

**User segment:** [Who specifically experiences this problem]

**Current situation:** [What users do today — workarounds, pain points, friction]

**Impact of not solving it:** [What happens if we do nothing — churn risk, revenue impact, compliance risk, etc.]

**Why now:** [What makes this the right time — market signal, strategic priority, regulatory deadline, user feedback volume]

---

## 2. Goals

> What does success look like? Be specific and measurable.

**Primary metric (North Star impact):**
- [ ] [Metric]: from [current] → [target] by [date]

**Secondary metrics:**
- [ ] [Metric]: [target]
- [ ] [Metric]: [target]

**Guardrail metrics (must not degrade):**
- [ ] [Metric]: must stay above [threshold]
- [ ] [Metric]: must stay below [threshold]

---

## 3. User Stories

> Written from the user's perspective. Prioritize by impact.

**Primary user story:**
> As a **[user type]**, I want to **[action]** so that **[benefit]**.

**Additional stories:**

| # | As a... | I want to... | So that... | Priority |
|---|---------|--------------|------------|----------|
| 1 | [user] | [action] | [benefit] | P0 |
| 2 | [user] | [action] | [benefit] | P1 |
| 3 | [user] | [action] | [benefit] | P1 |
| 4 | [user] | [action] | [benefit] | P2 |

---

## 4. Acceptance Criteria

> Gherkin format. These are the tests for "done." Be exhaustive.

### Happy Path

```gherkin
Given [initial context]
When [user action]
Then [expected result]
And [additional expected result]
```

### Edge Cases

```gherkin
Given [edge case context]
When [user action]
Then [expected behavior]
```

```gherkin
Given [another edge case]
When [user action]
Then [expected behavior]
```

### Error States

```gherkin
Given [error context]
When [failure occurs]
Then [user sees error message: "..."]
And [system does: ...]
```

### Permissions

```gherkin
Given [user without required permission]
When [they attempt the action]
Then [they see: ...]
And [the action is blocked]
```

---

## 5. Functional Requirements

> What the system must do. Be precise. Numbered for traceability.

**FR-01:** [Requirement]
**FR-02:** [Requirement]
**FR-03:** [Requirement]
**FR-04:** [Requirement]
**FR-05:** [Requirement]

---

## 6. Non-Functional Requirements

> How the system must behave, not what it does.

**Performance:**
- [ ] [Action] must complete in under [X]ms at [P95/P99]
- [ ] System must handle [N] concurrent users without degradation

**Security:**
- [ ] [Data type] must be encrypted at rest and in transit
- [ ] [Action] requires [authentication method]
- [ ] Audit log must capture [events] with [fields]

**Compliance (Fintech):**
- [ ] Feature must comply with [regulation: PSD2 / GDPR / AML / KYC / local law]
- [ ] Data residency: [specify requirements]
- [ ] Retention policy: [specify]
- [ ] Compliance review required: Yes / No → Contact: [name]

**Reliability:**
- [ ] Target uptime: [X]%
- [ ] Degraded mode behavior: [describe what happens if dependencies fail]
- [ ] Data consistency: [eventual / strong]

**Accessibility:**
- [ ] Must meet [WCAG 2.1 AA / other standard]
- [ ] Screen reader support required: Yes / No

---

## 7. Design & UX

> Link to Figma or describe expected behavior clearly enough for an AI to implement.

**Figma link:** [URL or "TBD"]

**Key UX decisions:**
- [Decision and rationale]
- [Decision and rationale]

**Mobile behavior:** [Describe or link]

**Empty states:** [What does the user see with no data?]

**Loading states:** [How does the UI behave while data loads?]

---

## 8. Technical Notes

> For engineering. Constraints, preferred approaches, APIs to use.

**Preferred stack / approach:** [If relevant]

**APIs or services involved:**
- [Service]: [how it's used]
- [Service]: [how it's used]

**Data model changes:** [Describe new tables, fields, or schema changes]

**Breaking changes:** [Yes / No — if yes, describe migration plan]

**Third-party dependencies:** [List any new vendors or SDKs]

---

## 9. Out of Scope

> Explicit list of what we are NOT building in this version. This prevents scope creep.

- [ ] [Feature or capability] — reason: [rationale, e.g., "Phase 2", "separate team", "not validated yet"]
- [ ] [Feature or capability] — reason: [rationale]
- [ ] [Feature or capability] — reason: [rationale]

---

## 10. Edge Cases & Known Risks

| Edge Case | Expected Behavior | Owner |
|-----------|-------------------|-------|
| [Scenario] | [How system handles it] | [Eng/PM/Design] |
| [Scenario] | [How system handles it] | [Eng/PM/Design] |
| [Scenario] | [How system handles it] | [Eng/PM/Design] |

**Top risk:** [Single biggest thing that could go wrong]
**Mitigation:** [What we're doing about it]

---

## 11. Open Questions

> Unresolved decisions that need input before or during build.

| # | Question | Owner | Deadline | Status |
|---|----------|-------|----------|--------|
| 1 | [Question] | [Name] | [Date] | Open |
| 2 | [Question] | [Name] | [Date] | Open |
| 3 | [Question] | [Name] | [Date] | Open |

---

## 12. Launch Plan

**Rollout strategy:** [Feature flag / % rollout / full launch / A/B test]

**Initial rollout:** [X% of users / specific segment]

**Full rollout:** [Date or condition]

**Rollback plan:** [How to disable if something goes wrong]

**Launch comms:**
- [ ] Internal: [Slack announcement / all-hands / team email]
- [ ] External: [In-app notification / release notes / marketing]

---

## Changelog

| Date | Author | Change |
|------|--------|--------|
| [Date] | [Name] | Created spec |
| [Date] | [Name] | [What changed] |

---

*Template maintained in [ai-pm-toolkit](https://github.com/luisaomoncalvo/ai-pm-toolkit) · Luis Moncalvo*
