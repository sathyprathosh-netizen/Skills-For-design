---
name: accessibility
description: Design and verify inclusive web experiences aligned with WCAG principles, semantic HTML, keyboard use, and assistive technology.
---

# Accessibility Skill

Follow `GLOBAL-OPERATING-SYSTEM.md`. Treat accessibility as a product requirement from the first wireframe, not a final overlay. Target WCAG 2.2 AA where applicable, while recognizing that automated tools cannot prove conformance.

## 1. Structure and semantics

- [ ] Use semantic landmarks: header, nav, main, aside, footer.
- [ ] Use headings in a logical hierarchy.
- [ ] Use native buttons, links, inputs, lists, and tables appropriately.
- [ ] Give every form control a programmatic label.
- [ ] Associate help text and errors with the correct field.
- [ ] Use ARIA only when native HTML does not provide the needed semantics.
- [ ] Ensure custom widgets expose role, name, value, and state.

## 2. Keyboard and focus

- [ ] All functionality works with keyboard alone.
- [ ] Focus order follows the visual and task order.
- [ ] Focus indicator is visible and not obscured.
- [ ] No keyboard traps; dialogs manage and restore focus.
- [ ] Menus, tabs, accordions, and comboboxes follow expected keyboard patterns.
- [ ] Skip link is available on substantial pages.
- [ ] Do not rely on hover, drag, or complex gestures as the only interaction.

## 3. Visual accessibility

- [ ] Text contrast meets WCAG AA: generally 4.5:1 for normal text and 3:1 for large text.
- [ ] Meaningful non-text UI and graphical objects have adequate contrast.
- [ ] Colour is not the only way to communicate status or meaning.
- [ ] Text resizes to 200% without loss of content or function.
- [ ] Reflow works at narrow viewport widths and high zoom.
- [ ] Text spacing overrides do not break content.
- [ ] Avoid tiny text and cramped targets.
- [ ] Respect user preferences for reduced motion and contrast where supported.

## 4. Images, media, and content

- [ ] Meaningful images have concise contextual alt text.
- [ ] Decorative images use empty alt / are hidden from assistive technology.
- [ ] Complex charts have a text summary or data alternative.
- [ ] Video has captions; audio-only content has a transcript where needed.
- [ ] Instructions do not depend only on visual position, shape, or colour.
- [ ] Plain language and descriptive link text are used.
- [ ] Language of page and language changes are identified.

## 5. Dynamic interaction

- [ ] Announce meaningful status updates without excessive live-region noise.
- [ ] Error messages explain the problem and how to fix it.
- [ ] Validation does not rely only on colour.
- [ ] Loading states are perceivable.
- [ ] Focus is managed after route changes and modal interactions.
- [ ] Time limits can be extended or avoided where required.
- [ ] Animation does not trigger avoidable vestibular discomfort.

## 6. Testing

- [ ] Run automated checks (axe or equivalent) but do not treat a clean scan as proof.
- [ ] Navigate every core flow with keyboard only.
- [ ] Test with at least one screen reader / browser combination when feasible.
- [ ] Test zoom, reflow, contrast, labels, errors, and focus.
- [ ] Test custom components with assistive technology.
- [ ] Record barriers, impact, reproduction steps, and remediation.
- [ ] Re-test after fixes.

## Definition of done

Core tasks are usable without a mouse; content and controls are programmatically understandable; contrast, zoom, reflow, focus, errors, and dynamic states have been checked; remaining barriers are disclosed.

## `/improve accessibility` — inclusive experience refinement mode

- [ ] Re-test the actual user flows rather than relying only on source inspection.
- [ ] Audit semantic structure, names/roles/values, labels, keyboard order, focus visibility, and focus management.
- [ ] Check contrast, zoom, reflow, target size, motion, captions, and error messaging.
- [ ] Test custom controls with keyboard and assistive technology.
- [ ] Use automated tools to find issues, then manually verify.
- [ ] Prioritize barriers that block task completion.
- [ ] Fix the root component or token where possible, not just individual symptoms.
- [ ] Re-test affected flows and report remaining barriers against the intended conformance target.

Do not claim WCAG conformance from an automated scan alone.
