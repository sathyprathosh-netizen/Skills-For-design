---
name: ui-ux-design
description: Design distinctive, usable, responsive digital products with a coherent design system and strict anti-AI-slop standards. Use before creating or substantially changing product UI.
---

# UI/UX Design Skill

Follow `GLOBAL-OPERATING-SYSTEM.md` first. Do not design before the Project Identity Gate is complete.

## Mission

Turn user needs and business goals into a clear, differentiated interface. Optimize comprehension, task success, trust, accessibility, and conversion—not visual novelty alone.

## Phase 1 — product understanding

- [ ] Identify primary audience, context, device, and user intent.
- [ ] Define the top task and the one primary action for each important screen.
- [ ] Map user journey: entry → orientation → decision → action → feedback.
- [ ] Identify user anxieties, trust requirements, and failure points.
- [ ] Review existing product, analytics, support feedback, and references when available.
- [ ] Separate verified facts from assumptions.
- [ ] Define measurable acceptance criteria (e.g. task completion, fewer steps, form completion).

Deliverable: a one-page UX brief and a prioritized flow map.

## Phase 2 — information architecture

- [ ] Create a sitemap / navigation model appropriate to product complexity.
- [ ] Group content by user mental model, not internal org chart.
- [ ] Use plain-language labels; avoid clever navigation names.
- [ ] Keep navigation depth appropriate; show location and current state.
- [ ] Make the next action obvious without making every element compete.
- [ ] Include search, filters, sorting, or progressive disclosure only when they solve a real problem.
- [ ] Design empty, loading, error, success, and permission-denied states.

## Phase 3 — visual direction

Before high-fidelity UI, define:
- [ ] Design concept in one sentence (e.g. “editorial precision for a specialist financial tool”).
- [ ] Three visual principles and three things deliberately avoided.
- [ ] Colour roles and contrast pairings.
- [ ] Typography hierarchy and maximum readable line lengths.
- [ ] Spacing, grid, responsive breakpoints, radii, borders, and elevation.
- [ ] Image / illustration art direction with a clear purpose.
- [ ] Motion principles and reduced-motion fallback.

### Anti-slop gate

Reject a screen if:
- [ ] It could be relabelled for any random SaaS company without changing its design.
- [ ] Its hero relies on vague claims rather than explaining what the product does.
- [ ] Decoration is more prominent than product value or content.
- [ ] Every section repeats the same card grid.
- [ ] Icons are used where clear labels would be better.
- [ ] It uses fake dashboards, fake testimonials, fake metrics, or fake logos.
- [ ] It looks polished at one viewport but breaks at realistic content lengths.
- [ ] The primary action is unclear or there are too many competing CTAs.

To pass, make the layout and visual language specific to the brand, audience, content, and task. Explain the rationale.

## Phase 4 — wireframes and interaction

- [ ] Start with content-first low-fidelity structure.
- [ ] Show hierarchy, grouping, actions, and responsive reflow.
- [ ] Define component states: default, hover, focus, active, disabled, loading, error, success.
- [ ] Define form labels, helper text, validation timing, and recovery.
- [ ] Define confirmation and undo for destructive actions.
- [ ] Ensure dialogs and menus have predictable focus and dismissal behavior.
- [ ] Avoid hover-only information and interactions.
- [ ] Use realistic content, including long names and empty datasets.

## Phase 5 — responsive design

- [ ] Design mobile intentionally; do not merely shrink desktop.
- [ ] Test narrow phones, common phones, tablets, laptops, and wide screens.
- [ ] Define what reorders, collapses, scrolls, or disappears at each breakpoint.
- [ ] Keep touch targets comfortable and avoid dense controls.
- [ ] Prevent horizontal overflow and clipped focus indicators.
- [ ] Check long headings, translations, large numbers, and error messages.
- [ ] Ensure sticky UI does not cover content or keyboard focus.

## Phase 6 — design QA

- [ ] Compare implementation to approved design intent.
- [ ] Check spacing rhythm, alignment, typography, contrast, and consistency.
- [ ] Inspect real screenshots at multiple widths.
- [ ] Test complete user journeys with keyboard and touch.
- [ ] Review loading, empty, error, success, and disabled states.
- [ ] Check reduced motion and zoom / text resizing.
- [ ] Ask: “What is the one thing this screen wants the user to understand or do?”
- [ ] Remove any element that does not support comprehension, trust, or task completion.

## Deliverables

Provide: UX brief, sitemap / flow, visual direction, token proposal, screen/state inventory, responsive rules, and QA findings. For implementation tasks, coordinate with frontend, accessibility, performance, and code-review skills.

## `/improve design` — expert refinement mode

- [ ] Capture the current screens at representative mobile, tablet, and desktop widths.
- [ ] Compare the UI against the approved brief, brand tokens, user tasks, and real content.
- [ ] Audit hierarchy, distinctiveness, whitespace, typography, colour roles, composition, and CTA clarity.
- [ ] Identify generic patterns, redundant sections, visual noise, weak content, and unnecessary decoration.
- [ ] Inspect all interaction states and responsive transitions.
- [ ] Check accessibility and performance implications before changing visuals.
- [ ] Rank improvements by user impact; preserve approved brand decisions.
- [ ] Implement the strongest coherent improvements, not a random collection of effects.
- [ ] Re-capture and compare screenshots; verify core flows and keyboard behavior.
- [ ] Report what materially improved and what was intentionally left unchanged.

Do not interpret “10x” as permission to replace the entire design. Make the experience more recognizably suited to this product and measurably easier to use.
