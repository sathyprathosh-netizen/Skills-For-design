---
name: frontend-development
description: Build robust, responsive, maintainable frontend experiences from an approved product brief and design system.
---

# Frontend Development Skill

Follow `GLOBAL-OPERATING-SYSTEM.md` and complete the Project Identity Gate before implementation.

## 1. Repository reconnaissance

- [ ] Inspect framework, version, scripts, package manager, routing, styling, and component conventions.
- [ ] Read relevant files before editing; trace data and state flow.
- [ ] Identify existing design tokens and shared components.
- [ ] Check current build / lint / test baseline when feasible.
- [ ] Do not replace the stack or introduce dependencies without a reason.
- [ ] Create a small implementation plan with acceptance criteria.

## 2. Architecture

- [ ] Separate presentation, domain logic, data access, and side effects appropriately.
- [ ] Use components for meaningful reuse, not for every wrapper.
- [ ] Keep components cohesive and avoid giant page components.
- [ ] Prefer explicit props and predictable state ownership.
- [ ] Avoid unnecessary global state; use URL state for shareable navigation/filter state where appropriate.
- [ ] Avoid duplicated business logic and duplicated design tokens.
- [ ] Use typed interfaces / schemas at trust boundaries.
- [ ] Keep secrets, privileged operations, and private API keys off the client.

## 3. Implementation quality

- [ ] Use semantic HTML elements before custom ARIA.
- [ ] Use design tokens; no arbitrary one-off palette or spacing values.
- [ ] Keep CSS/layout responsive and content-driven.
- [ ] Use stable keys and correct list identity.
- [ ] Handle async states and cancellation / stale responses where needed.
- [ ] Validate user input on client for usability and again on server for security.
- [ ] Avoid direct DOM manipulation unless necessary and isolated.
- [ ] Avoid `any`, unsafe casts, and ignored errors without documented justification.
- [ ] Avoid duplicated event handlers and hidden side effects.
- [ ] Keep console free of avoidable warnings and runtime errors.

## 4. Product states

For every important interaction, consider:
- [ ] Initial / loading
- [ ] Empty / first-use
- [ ] Success / confirmation
- [ ] Validation error
- [ ] Network / server error
- [ ] Disabled / permission-limited
- [ ] Retry / recovery
- [ ] Offline / slow connection if relevant

Never leave a button visually active if it has no action. Never show a success message before the operation succeeds.

## 5. Responsive and visual fidelity

- [ ] Verify mobile-first layout and content hierarchy.
- [ ] Check at minimum narrow mobile, typical mobile, tablet, laptop, and wide desktop.
- [ ] Check overflow, sticky elements, tables, navigation, dialogs, and forms.
- [ ] Test real content lengths, not only short placeholder strings.
- [ ] Verify typography, spacing, contrast, focus, and touch targets.
- [ ] Ensure image aspect ratios, cropping, and loading behavior are intentional.

## 6. Data and forms

- [ ] Use controlled/uncontrolled form patterns consistently.
- [ ] Provide visible labels; placeholders are not labels.
- [ ] Validate with helpful, field-specific messages.
- [ ] Preserve safe user input after recoverable failures.
- [ ] Prevent duplicate submissions.
- [ ] Show progress for long operations.
- [ ] Handle pagination, filtering, sorting, and empty results predictably.

## 7. Verification checklist

- [ ] Run formatter / lint.
- [ ] Run type checks.
- [ ] Run unit / integration / end-to-end tests available in the project.
- [ ] Run production build.
- [ ] Manually test core flows and responsive views.
- [ ] Inspect browser console and network failures.
- [ ] Run accessibility and performance checks for changed screens.
- [ ] Report exact commands and observed results; do not fabricate.

## Anti-slop frontend rules

Do not produce generic hero templates, random gradients, gratuitous glassmorphism, arbitrary rounded cards, fake product screenshots, or decorative motion by default. Build from the approved content hierarchy and tokens. A page is not finished because it compiles; inspect the rendered result and test the task users came to complete.

## `/improve frontend` — engineering refinement mode

- [ ] Inspect current architecture, changed files, runtime behavior, and existing tests.
- [ ] Identify complexity, duplication, brittle state, unnecessary dependencies, weak typing, and error-state gaps.
- [ ] Profile or measure before optimizing rendering or bundle size.
- [ ] Improve component boundaries only where cohesion or reuse benefits.
- [ ] Strengthen loading, empty, validation, error, and recovery behavior.
- [ ] Preserve visual design and API contracts unless change is required and approved.
- [ ] Run lint, type checks, tests, and production build where available.
- [ ] Verify affected flows at mobile and desktop sizes.
- [ ] Report concrete before/after evidence and residual risks.

Do not refactor stable code solely to make it look more sophisticated.
