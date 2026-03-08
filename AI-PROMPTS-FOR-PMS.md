# 🤖 AI Prompts for PMs

My personal collection of high-leverage prompts for product management work. Built for Claude, optimized for fintech.

**How to use:** Copy the prompt, fill in the `[brackets]`, and paste into Claude. Most prompts work best with additional context about your product and users.

---

## 📋 PRD & Specs

### Write a PRD from a feature idea
```
You are a senior product manager at a fintech company. Write a comprehensive PRD for the following feature:

Feature: [feature name]
Context: [brief description of the product and users]
Problem: [what problem this solves]

The PRD should include:
1. Executive Summary
2. Problem Statement & User Pain Points
3. Goals & Success Metrics
4. User Stories (at least 5, written as "As a [user], I want to [action] so that [benefit]")
5. Functional Requirements
6. Non-Functional Requirements (performance, security, compliance)
7. Out of Scope
8. Open Questions
9. Dependencies & Risks

Format it as a professional document with clear headers. Be specific and actionable.
```

### Turn a vague idea into a crisp one-pager
```
I have a rough product idea. Help me sharpen it into a clear one-pager.

Raw idea: [describe your idea in plain language]

Create a one-pager with:
- The problem (1-2 sentences, quantified if possible)
- The proposed solution (2-3 sentences)
- Who it's for (specific user segment)
- Why now (market timing or internal trigger)
- How we'll know it worked (2-3 measurable outcomes)
- Biggest risk / open question

Keep it under 300 words. Be direct and cut anything vague.
```

### Generate acceptance criteria
```
Write Gherkin-style acceptance criteria for the following user story:

User Story: [paste user story]

Generate at least 6 scenarios covering:
- Happy path (main success flow)
- Edge cases
- Error states
- Permissions/access control (if applicable)
- Mobile/responsive behavior (if applicable)

Format: Given / When / Then
```

### Critique a PRD
```
Review this PRD and give me honest, critical feedback. Be specific about what's missing, what's vague, and what would make an engineer or designer push back.

[paste PRD]

Evaluate:
1. Clarity of the problem statement
2. Quality of success metrics (are they measurable?)
3. Completeness of requirements
4. Edge cases and error handling
5. What a skeptical engineer would question
6. What a skeptical designer would question
7. Overall recommendation: ship / revise / kill
```

---

## 🔍 Discovery & User Research

### Synthesize user interview notes
```
I conducted [N] user interviews about [topic]. Here are my raw notes:

[paste notes]

Synthesize this into:
1. Top 3 recurring pain points (with supporting quotes)
2. Key user needs (ranked by frequency)
3. Surprising or unexpected findings
4. Assumptions that were validated
5. Assumptions that were invalidated
6. Recommended next steps for discovery

Format as a research readout I can share with stakeholders.
```

### Generate discovery questions
```
I'm doing discovery for [feature/problem area] targeting [user segment] at a [fintech product type, e.g. neobank, lending platform, payment gateway].

Generate 20 discovery interview questions that:
- Start with broad context questions
- Progressively narrow to the specific problem
- Uncover workarounds and current solutions
- Identify emotional drivers and frustrations
- Avoid leading the interviewee

Include 3 follow-up probes for the most important questions.
```

### Create a Jobs-to-be-Done statement
```
Based on the following context, write a Jobs-to-be-Done statement and map it to functional, emotional, and social dimensions.

Context: [describe the user and situation]
Current behavior: [what they do today]
Desired outcome: [what they're trying to achieve]

Format:
- Core JTBD statement: "When [situation], I want to [motivation], so I can [expected outcome]"
- Functional job: [practical task]
- Emotional job: [how they want to feel]
- Social job: [how they want to be perceived]
- Competing solutions: [what they use today]
```

### Assumptions mapping
```
I'm working on [feature/product]. Help me map all assumptions we're making before we build.

Context: [brief description]

Categorize assumptions into:
1. Desirability (do users want this?)
2. Feasibility (can we build it?)
3. Viability (is it good for business?)
4. Regulatory/Compliance (fintech-specific risks)

For each assumption, rate:
- Confidence level: Low / Medium / High
- Risk if wrong: Low / Medium / High
- Suggested validation method

Prioritize the top 5 riskiest assumptions to test first.
```

---

## 🗺️ Prioritization & Roadmap

### Prioritize a backlog with RICE
```
Score the following features using the RICE framework (Reach, Impact, Confidence, Effort).

Features:
[list your features]

Context:
- Product: [product name/type]
- Current user base: [size]
- Team capacity: [size and composition]
- Strategic focus this quarter: [OKR or theme]

For each feature provide:
- Reach (users/month): [estimate]
- Impact (0.25 / 0.5 / 1 / 2 / 3): [score]
- Confidence (%): [score]
- Effort (person-weeks): [score]
- RICE Score: Reach × Impact × Confidence / Effort
- Recommendation: Build now / Next quarter / Deprioritize

Output as a ranked table with rationale for top 3.
```

### Build a narrative roadmap
```
Turn this list of features into a narrative roadmap for the next 3 quarters.

Features: [list]
Company strategy: [1-2 sentences]
Team: [size and type]
Current product state: [brief description]

Format:
- Q[X] Theme: [one phrase that captures the quarter]
- Bets: [3-5 initiatives, each with a 1-sentence rationale]
- Expected outcomes: [what changes for users and the business]

Make it story-driven, not a feature list. The reader should understand the "why" behind each quarter.
```

### Run a pre-mortem
```
We're about to launch [feature/product]. Run a pre-mortem.

Context: [brief description of what we're launching, when, and to whom]

Imagine it's 6 months after launch and the feature failed completely. Generate:
1. Top 5 reasons it failed (be brutally honest)
2. Early warning signals we should monitor
3. Mitigation actions we can take now
4. The single most likely failure mode
5. Go / No-go recommendation based on this analysis
```

---

## 🎫 Tickets & User Stories

### Break an epic into stories
```
Break this epic into individual user stories ready for sprint planning.

Epic: [describe the epic]
Users involved: [list user types]
Technical constraints: [any known limitations]

For each story:
- User story (As a / I want / So that)
- Acceptance criteria (Gherkin format)
- Story points estimate (1/2/3/5/8)
- Dependencies
- Open questions

Aim for stories completable in 1-3 days. Flag anything that should be a spike.
```

### Write a bug report
```
Write a clear, actionable bug report from these notes:

Raw notes: [paste your notes]
Severity: [Critical / High / Medium / Low]
Environment: [prod / staging / device type]

Format:
- Title: [short, descriptive]
- Steps to reproduce: [numbered list]
- Expected behavior
- Actual behavior
- Impact: [who is affected and how many]
- Screenshots/evidence: [placeholder]
- Suggested fix (if known)
```

### Generate edge cases
```
I'm building [feature]. Generate a comprehensive list of edge cases the engineering team needs to handle.

Feature description: [describe it]
User types: [list them]
Platform: [web / mobile / API]

Categories to cover:
- Empty states
- Maximum/minimum values
- Concurrent actions
- Network failures
- Permission edge cases
- Internationalization (currency, dates, language)
- Regulatory/compliance scenarios (for fintech)
- Fraud or abuse scenarios
```

---

## 📢 Stakeholder Communication

### Write a product update email
```
Write a concise product update email for [audience: exec team / engineering / sales / all-hands].

What happened: [key updates this week/month]
Metrics: [relevant numbers]
What's next: [upcoming priorities]
Blockers or asks: [anything you need from them]

Tone: [professional / casual / urgent]
Length: under 200 words
Include a clear subject line.
```

### Prepare for a difficult stakeholder conversation
```
I need to have a difficult conversation with [stakeholder: CEO / CTO / investor / sales lead].

Situation: [describe what's happening — delay, pivot, bad metric, disagreement]
Their likely concern: [what they care about]
My position: [what I want to communicate]

Help me:
1. Frame the message using Pyramid Principle (conclusion first, then rationale)
2. Anticipate their top 3 objections and prepare responses
3. Identify what I need from them (decision, resources, alignment)
4. Suggest the right channel and timing
5. Draft the opening 3 sentences of the conversation
```

### Write a decision memo
```
Write a decision memo for [decision we need to make].

Context: [background]
Options considered:
1. [Option A]
2. [Option B]
3. [Option C — often "do nothing"]

Criteria for decision: [what matters most]
Recommendation: [what you think we should do]
Risks of recommended option: [be honest]
Who needs to sign off: [list stakeholders]

Format as a 1-page memo. Bottom line up front.
```

---

## 📊 Metrics & OKRs

### Design a metrics framework
```
Design a metrics framework for [feature/product].

Product description: [what it does]
User goal: [what users are trying to achieve]
Business goal: [what the company needs]

Provide:
1. North Star Metric (1 metric that best captures value delivered to users)
2. Input metrics (3-5 leading indicators that drive the North Star)
3. Guardrail metrics (what we must not break)
4. Diagnostic metrics (for debugging drops in the North Star)
5. How to instrument each metric (event names, properties)

For each metric: name, definition, target, measurement frequency.
```

### Write quarterly OKRs
```
Write OKRs for [team name] for Q[X] [year].

Company strategy: [1-2 sentences]
Team's focus area: [what this team owns]
Last quarter's performance: [brief summary]
Key initiatives planned: [list]

Format:
Objective: [ambitious, qualitative goal — what we're going for]
KR1: [measurable, binary or numeric — 0 to X]
KR2: [...]
KR3: [...]

Write 1 objective with 3-4 key results. Make KRs measurable and achievable in 90 days.
```

### Diagnose a metric drop
```
Our [metric] dropped [X%] between [date range]. Help me diagnose what happened.

Metric: [definition]
Drop: [from X to Y, between dates]
What changed recently: [releases, campaigns, external events]
Segments available to analyze: [geography, user type, platform, cohort]

Give me:
1. Most likely hypotheses (ranked by probability)
2. Data I need to gather to validate each
3. SQL query logic or dashboard cuts to investigate
4. Timeline for diagnosis
5. Communication I should send while investigating
```

---

## 🏦 Fintech-Specific

### Regulatory impact assessment
```
Assess the regulatory implications of this product feature for a [country/region] fintech.

Feature: [describe it]
Product type: [neobank / lending / payments / investments / crypto / insurance]
Markets: [list countries/regions]

Evaluate:
1. Applicable regulations (e.g., PSD2, GDPR, AML/KYC, CFPB, Open Banking)
2. Compliance requirements this feature must meet
3. Data residency and privacy implications
4. Licensing requirements
5. What legal/compliance review is needed before launch
6. Estimated compliance effort: Low / Medium / High

Note: This is a preliminary assessment, not legal advice. Always validate with your compliance team.
```

### Write fraud risk analysis
```
Analyze the fraud and abuse risks of this fintech feature.

Feature: [describe it]
User base: [type and size]
Transaction types: [if applicable]
Current fraud controls: [what's already in place]

For each risk:
- Attack vector
- Likelihood: Low / Medium / High
- Potential impact (financial and reputational)
- Recommended control or mitigation
- Priority to address: P0 / P1 / P2

End with a summary risk rating and go/no-go recommendation.
```

### Competitive analysis — fintech
```
Run a competitive analysis for [your feature/product] in the [fintech vertical] space.

My product: [brief description]
Markets: [list]
Competitors to analyze: [list 3-5, or ask Claude to identify them]

For each competitor:
1. How they solve this problem
2. Pricing model
3. Key differentiators
4. Weaknesses or gaps
5. Recent product moves (last 12 months)

End with:
- Where we can win (our opportunity)
- Where we're at risk
- 3 strategic recommendations
```

### Design a KYC/onboarding flow
```
Design the optimal KYC and onboarding flow for [product type] targeting [user segment] in [market].

Constraints:
- Regulatory requirements: [list known ones]
- Target completion rate: [X%]
- Mobile-first: [yes/no]
- Existing identity infrastructure: [list what you have]

Provide:
1. Step-by-step onboarding flow with decision points
2. Required vs. optional data at each step
3. Drop-off risk at each step and mitigation
4. Progressive disclosure strategy (what to ask now vs. later)
5. How to handle rejections gracefully
6. Metrics to track success
```

---

## 🧠 Thinking & Frameworks

### First principles breakdown
```
Break down [problem or decision] using first principles thinking.

Context: [describe the situation]

1. What are we actually trying to achieve? (strip away assumptions)
2. What do we know for certain? (facts, not opinions)
3. What are we assuming that might not be true?
4. If we started from scratch with no constraints, what would we build?
5. What's the simplest version that solves the core problem?
6. What would a skeptic say about our reasoning?
```

### Speed up a decision
```
I need to make a decision about [topic] and I'm overthinking it.

Situation: [describe it]
Options: [list them]
What I'm stuck on: [the specific dilemma]
Deadline: [when this needs to be decided]

Use the following to help me decide:
1. What's the worst realistic outcome of each option?
2. Which option is most reversible?
3. What would a confident, senior PM decide — and why?
4. What information would actually change my decision (vs. what's just noise)?
5. Recommendation: [make a call]
```

---

*Last updated: March 2026 · Luis Moncalvo · Senior PM · Fintech*
