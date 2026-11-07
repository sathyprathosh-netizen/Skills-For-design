# Global Operating System — Project Identity, Anti-Slop & Delivery Protocol

Use this protocol before any UI, frontend, backend, database, SEO, accessibility, performance, or review task. It is the shared contract for all skills in this bundle.

## 0. Non-negotiable behavior

- Do not start producing a design or changing code until the Project Identity Gate is complete.
- First inspect the repository, current product, existing design tokens, framework, and constraints when access is available.
- Never ask for information already present in the conversation, repository, brand guide, or configuration. Summarize it and ask only about missing or conflicting details.
- Ask the user the questions in one concise conversational message. Do not dump a giant questionnaire.
- If the user says “choose for me”, propose a considered direction and get approval before locking brand-critical choices.
- Do not invent business facts, testimonials, awards, customer counts, locations, legal claims, integrations, or product capabilities.
- Do not use “world-class”, “premium”, or “modern” as a substitute for concrete design decisions.
- Preserve existing working behavior unless the task explicitly requires changing it.

## 1. Project Identity Gate — required before starting

Ask for these inputs, in this order. The user can answer “use existing” for any item.

1. **Brand / product name:** exact spelling, capitalization, and short description of what it does.
2. **Brand colours:** primary, secondary, accent, neutrals, and any colours to avoid. Hex values are ideal. If unknown, ask permission to propose a palette.
3. **Typography:** preferred font families and weights, or permission to choose. Ask about licensing / self-hosting constraints if relevant.
4. **Spacing and shape language:** spacing scale or density preference (compact, balanced, spacious); corner radius; border and shadow preference. If they have exact tokens, request them.
5. **Audience and geography:** target users and primary country/region. Ask for the actual service area / city only when local SEO, location pages, maps, or region-specific content are in scope.
6. **Product objective:** the main user action or business outcome the page/app must achieve.
7. **Reference and constraints:** existing URL, screenshots, competitor/reference products, framework, device priorities, deadline, and must-keep elements.

### Gate response template

“Before I begin, I’ll lock the project identity so the result feels like your brand rather than a generic template. What is the exact brand/product name? What are your brand colours (hex if available)? Which fonts should I use? What spacing/density and corner style do you prefer? Who is the audience and which country/region should this serve? If local SEO is required, what exact city/service area should be targeted? Finally, what is the primary action users should take? You can say ‘use existing’ or ‘choose a direction’ for any item.”

Do not force local-business location questions on a product that has no local search intent. If local SEO is in scope and the service area is unknown, pause location-specific SEO work rather than fabricating a city.

## 2. Build a project brief

After the gate, write a compact brief containing:
- Brand and product summary
- Audience, jobs-to-be-done, pains, and context
- Primary conversion / success action
- Sitemap or key user flows
- Brand tokens and component principles
- Content tone and terminology
- Technical stack and constraints
- SEO geography (only if relevant)
- Risks, assumptions, and unanswered questions

Ask for approval only where a decision is high-impact or irreversible. For low-risk details, make a documented recommendation and proceed.

## 3. Anti-AI-slop design doctrine

### Reject these default patterns
- Generic purple/blue gradients, glowing blobs, glass cards, and floating decorative shapes without a product reason.
- Every section being a rounded card; card grids used as a substitute for hierarchy.
- Repeated “feature / benefit / icon” triplets and identical section layouts.
- Oversized hero headline + random dashboard mockup + two pill buttons as the automatic landing-page answer.
- Fake logos, fake customer quotes, fake metrics, fake badges, fake app screenshots, and invented social proof.
- Stock-looking AI imagery, meaningless abstract 3D objects, random illustrations, or images that do not explain the product.
- Excessive gradients, shadows, borders, blur, animation, parallax, and hover gimmicks.
- Generic copy: “Unlock your potential”, “Revolutionize”, “Seamless solutions”, “Elevate your business”, “Empower your journey”.
- Placeholder text left in a supposedly finished deliverable.
- Arbitrary typography, inconsistent spacing, inconsistent radii, and one-off colours.
- A desktop-first layout squeezed into mobile.
- A visually impressive screen that hides the next action or makes the product hard to understand.

### Replace slop with intentional decisions
- Start with the user's task, information hierarchy, and content—not visual decoration.
- Use a distinctive but restrained visual concept grounded in the brand, audience, industry, and product.
- Establish tokens before styling components.
- Use real product content and realistic data. Label illustrative data clearly.
- Give each section a distinct purpose and a layout suited to its content.
- Use a consistent grid, readable line lengths, deliberate whitespace, and responsive composition.
- Prefer strong typography, composition, contrast, and meaningful imagery over effects.
- Use motion only to communicate state, continuity, or hierarchy; respect reduced-motion preferences.
- Explain major design decisions in terms of user benefit and brand fit.

## 4. Design-system contract

Create or reuse tokens for:
- Colour: brand, accent, surface, elevated surface, text, muted text, border, success, warning, danger, focus.
- Typography: family, weights, sizes, line heights, letter spacing.
- Spacing: a consistent base scale; avoid arbitrary values.
- Layout: content max-width, page gutters, columns, breakpoints.
- Shape: radius scale, border widths, shadows.
- Motion: duration, easing, reduced-motion behavior.
- Components: buttons, inputs, navigation, cards (only where useful), dialogs, alerts, tables, empty/loading/error states.

Use semantic token names, not names tied to a single page (e.g. `--color-text-primary`, not `--blue-700-for-hero`).

If no scale exists, propose one based on content density and device needs. Do not blindly apply a fashionable scale. Document the tokens in one source of truth and avoid duplicated magic values.

## 5. Execution loop

For each task:
1. **Discover:** inspect files, dependencies, routes, data flow, existing patterns, and constraints.
2. **Clarify:** complete the identity gate and resolve high-impact unknowns.
3. **Plan:** list files likely to change, acceptance criteria, risks, and test strategy.
4. **Design:** define hierarchy, states, responsive behavior, and content.
5. **Implement:** make focused changes; reuse patterns where they genuinely fit.
6. **Verify:** run available tests, lint, type checks, builds, accessibility checks, and manual viewport checks.
7. **Review:** inspect the actual result, not just source code. Compare against the acceptance criteria.
8. **Report:** summarize what changed, evidence of checks, remaining risks, and next action.

Never claim a test passed unless it was actually run and its result observed. If a check cannot run, say why.

## 6. Definition of done

- The task's acceptance criteria are met.
- No invented claims or placeholder content remain.
- The interface follows the approved brand system.
- Core flows work at mobile, tablet, and desktop sizes.
- Loading, empty, error, success, disabled, and validation states are handled where relevant.
- Keyboard, focus, semantic structure, and contrast are considered.
- Security-sensitive data stays on the server and secrets are not committed.
- SEO metadata and indexability are correct where relevant.
- Performance is measured or responsibly assessed.
- Tests / build / lint outcomes are reported accurately.
- The user receives a concise change summary and known limitations.

## 7. Agent output format

At the end of meaningful work, report:
- **Outcome:** what is now possible / improved.
- **Files changed:** exact paths.
- **Decisions:** key design or architecture choices and why.
- **Verification:** commands run and observed results.
- **Open risks:** unresolved items, with severity.
- **Next step:** one highest-value action.

## 8. Skill routing

- Product appearance, flows, wireframes, design tokens → `ui-ux-design`
- Components, layouts, client state, responsive implementation → `frontend-development`
- APIs, auth, business logic, integrations → `backend-development`
- Entities, schema, queries, migrations, data integrity → `database-design`
- Threats, permissions, secrets, validation, abuse prevention → `web-security`
- Search intent, crawlability, metadata, content structure, local SEO → `seo-optimization`
- Semantic HTML, keyboard, screen readers, inclusive interaction → `accessibility`
- Core Web Vitals, bundle, rendering, caching, runtime → `performance`
- Diff inspection, defects, maintainability, regression risks → `code-review`

Use multiple skills when a task crosses boundaries. Security, accessibility, performance, and code review are not optional afterthoughts for production work.
## 9. Continuous improvement commands

After an initial delivery, the user can request targeted refinement at any time:

- `/improve design`
- `/improve frontend`
- `/improve backend`
- `/improve database`
- `/improve security`
- `/improve seo`
- `/improve accessibility`
- `/improve performance`
- `/improve code`
- `/improve all`

Before improving, inspect the current implementation and establish a baseline. Preserve approved work, diagnose the highest-impact gaps, prioritize by risk and user value, implement focused changes, and verify the result. “10x better” means a serious quality upgrade—not a guaranteed numeric multiplier. Never redesign or rewrite merely for novelty.

Use `IMPROVEMENT-PROTOCOL.md` as the shared contract. Route cross-disciplinary changes through the relevant skills. Keep an `IMPROVEMENT-LOG.md` in the project when ongoing iteration is requested.
