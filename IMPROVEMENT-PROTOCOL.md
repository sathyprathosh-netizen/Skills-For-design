# Continuous Improvement Protocol — `/improve`

This protocol applies after an initial delivery has been accepted or whenever the user requests a refinement. It is a cross-skill capability: `/improve` can target one skill, several skills, or the whole product.

## 1. Command grammar

Recognize natural-language commands and slash-style commands:

- `/improve design` → UI/UX design quality, visual hierarchy, interaction, responsive behavior.
- `/improve frontend` → frontend architecture, implementation quality, state, component structure, responsive behavior.
- `/improve backend` → API design, business logic, reliability, observability.
- `/improve database` → schema, integrity, query efficiency, migrations, data access.
- `/improve security` → threat model, vulnerabilities, authorization, secrets, abuse resistance.
- `/improve seo` → technical, content, on-page, and local SEO as applicable.
- `/improve accessibility` → WCAG-oriented audit and remediation.
- `/improve performance` → measured loading, runtime, rendering, and Core Web Vitals improvements.
- `/improve code` or `/improve code-review` → review the current implementation and remediate approved findings.
- `/improve all` → coordinated cross-functional audit of the whole product.
- `/improve <skill> <specific area>` → focus the improvement on the named area.

Treat “make it 10x better” as a request for a materially higher-quality iteration, not a literal measurable promise. Never claim a 10x improvement unless a metric demonstrates it.

## 2. Improvement is not a blind redesign

When invoked:
1. **Re-establish context:** inspect the current repository, latest implementation, prior approved decisions, and current user request.
2. **Preserve what works:** identify approved elements and stable behavior. Do not discard them merely to make the result look different.
3. **Baseline:** capture the current state with screenshots, tests, metrics, architecture notes, or code review findings appropriate to the target.
4. **Find leverage:** identify the few changes most likely to improve user outcomes, quality, safety, or maintainability.
5. **Prioritize:** rank findings by user impact, risk, effort, and confidence. Fix critical/high-risk issues before cosmetic polish.
6. **Plan:** state the proposed changes and any material trade-offs. Ask before destructive, expensive, breaking, or brand-changing actions.
7. **Execute:** make focused, coherent changes using the relevant skill(s).
8. **Verify:** compare against the baseline and run relevant checks. Do not invent results.
9. **Report:** state what improved, evidence, what was preserved, and remaining limitations.

For small, reversible improvements, proceed without unnecessary approval once the user's goal is clear. Ask one concise question only when an essential decision is missing.

## 3. Improvement scorecard

Evaluate only dimensions relevant to the request. Score each 1–5 with evidence, not vibes.

| Score | Meaning |
|---|---|
| 1 | Broken, unsafe, confusing, or materially below baseline |
| 2 | Significant gaps; inconsistent or fragile |
| 3 | Functional baseline; important opportunities remain |
| 4 | Strong, coherent, verified quality |
| 5 | Exceptional within the stated constraints; evidence supports the result |

Never inflate scores. A score of 5 requires meaningful verification and should be rare. If evidence is unavailable, mark “Not measured” rather than guessing.

## 4. Cross-skill improvement routing

| Command | Required skill(s) |
|---|---|
| `/improve design` | UI/UX + frontend + accessibility |
| `/improve frontend` | Frontend + accessibility + performance + code review |
| `/improve backend` | Backend + security + database + code review |
| `/improve database` | Database + backend + performance + security |
| `/improve security` | Security + backend + database + code review |
| `/improve seo` | SEO + frontend + performance + accessibility |
| `/improve accessibility` | Accessibility + UI/UX + frontend |
| `/improve performance` | Performance + frontend + backend/database where bottlenecks indicate |
| `/improve code` | Code review + the skill responsible for each finding |
| `/improve all` | All nine skills, sequenced by risk and dependency |

A target skill must not work in isolation if the improvement creates consequences for another discipline. For example, a visual redesign must preserve accessibility and performance; an API change must preserve authorization and data integrity.

## 5. The improvement loop

Repeat only while useful and authorized:

**Observe → Diagnose → Prioritize → Propose → Improve → Verify → Compare → Record**

Each iteration must produce a meaningful improvement or explain why no change is justified. Avoid churn, novelty for its own sake, and repeated rewrites that do not improve outcomes.

## 6. Improvement log

Maintain `IMPROVEMENT-LOG.md` in the project when the user wants ongoing iteration. Each entry should include:
- Date / iteration
- Command and target skill(s)
- Baseline and evidence
- Findings with severity / impact
- Approved changes
- Files changed
- Verification and comparison
- Regressions / trade-offs
- Remaining highest-value opportunity

Do not store secrets or sensitive user data in the log.

## 7. Completion standard

An improvement is complete only when:
- The requested target was addressed.
- Existing approved behavior and brand decisions were preserved unless change was authorized.
- Relevant tests / checks were run and results reported.
- Regressions were checked in adjacent disciplines.
- The user can understand what changed and why.
- Unverified claims are clearly labelled.

If the current product is already strong in a dimension, say so and recommend a smaller evidence-based improvement—or no change. Do not invent work to satisfy the command.
