---
name: code-review
description: Perform evidence-based code reviews focused on correctness, security, regressions, maintainability, and user impact.
---

# Code Review Skill

Follow `GLOBAL-OPERATING-SYSTEM.md`. Review the actual diff and surrounding code. Do not rewrite code merely to express personal style preferences.

## 1. Review setup

- [ ] Understand the task, acceptance criteria, architecture, and intended behavior.
- [ ] Inspect the full diff and relevant callers / consumers.
- [ ] Identify framework and dependency versions.
- [ ] Check whether migrations, environment variables, API contracts, or deployment config changed.
- [ ] Run or inspect tests relevant to the change.
- [ ] Separate confirmed defects from questions and suggestions.

## 2. Review priorities

Review in this order:

1. **Correctness:** wrong output, broken flow, edge cases, race conditions, state bugs.
2. **Security / privacy:** auth bypass, IDOR, injection, secret exposure, data leakage, unsafe redirects/uploads.
3. **Data integrity:** invalid states, missing constraints, unsafe migrations, transaction gaps.
4. **Reliability:** error handling, retries, timeouts, duplicate requests, partial failures.
5. **Accessibility / UX:** keyboard traps, missing labels, inaccessible errors, confusing states.
6. **Performance:** unbounded work, N+1 queries, heavy bundles, blocking operations.
7. **Maintainability:** duplication, unclear boundaries, brittle abstractions, poor naming.
8. **Style:** only when it affects consistency or readability materially.

## 3. Finding quality

Every actionable finding must include:
- Severity: Critical / High / Medium / Low
- File and line / symbol
- Concrete scenario that triggers it
- User, business, or system impact
- Recommended remediation

Do not report speculative issues as facts. If uncertain, phrase as a question and explain what evidence is missing.

## 4. Review checklist

- [ ] Does the code satisfy the stated requirement?
- [ ] Are edge cases and invalid inputs handled?
- [ ] Are permissions checked on the server?
- [ ] Are tenant and object ownership boundaries enforced?
- [ ] Are secrets and sensitive values protected?
- [ ] Are errors safe, useful, and observable?
- [ ] Are transactions / concurrency handled where needed?
- [ ] Are API and data contracts compatible?
- [ ] Are migrations safe and reversible / recoverable?
- [ ] Are loading, empty, error, and success states correct?
- [ ] Is the UI responsive and keyboard accessible?
- [ ] Are query and rendering costs bounded?
- [ ] Are tests meaningful and deterministic?
- [ ] Is documentation / configuration updated?
- [ ] Are dependencies justified and maintained?

## 5. Review output format

### Summary
One or two sentences describing overall risk and scope.

### Findings
List findings highest severity first. If none are found, say “No actionable findings identified in the reviewed scope”; do not imply the entire system is defect-free.

### Verification
Commands / tests run and exact observed result. Clearly state checks not run.

### Residual risk
Areas not covered, assumptions, or follow-up tests needed.

## Review discipline

- Do not silently fix unrelated issues during a review.
- Do not praise or criticize based on subjective taste.
- Do not treat formatting preferences as bugs.
- Do not approve a change if a critical concern remains unresolved.
- Never claim exhaustive review when only a partial diff or limited context was available.

## `/improve code` — review and remediation mode

- [ ] Inspect the current diff and relevant surrounding code.
- [ ] Identify confirmed defects and risks; separate questions from findings.
- [ ] Rank by severity and user/system impact.
- [ ] For each finding, give a reproducible scenario, impact, and recommended fix.
- [ ] Ask before broad refactors, breaking API changes, or destructive data changes.
- [ ] Fix approved findings using the owning skill.
- [ ] Add regression tests and run the relevant checks.
- [ ] Re-review the new diff for regressions and unintended scope expansion.
- [ ] Report resolved findings, outstanding findings, and unreviewed areas.

Do not equate “more code changed” with “better code”.
