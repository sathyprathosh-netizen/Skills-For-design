---
name: performance
description: Measure and improve real-user web performance, Core Web Vitals, loading, rendering, and runtime efficiency without harming UX.
---

# Performance Skill

Follow `GLOBAL-OPERATING-SYSTEM.md`. Establish target devices, network conditions, user journeys, and performance budgets before optimizing. Measure first; do not cargo-cult optimizations.

## 1. Baseline and budgets

- [ ] Identify key pages and user journeys.
- [ ] Measure production-like behavior, not only local development.
- [ ] Record LCP, INP, CLS, TTFB, and relevant lab metrics.
- [ ] Use field data when available; distinguish field data from lab estimates.
- [ ] Define budgets for JavaScript, CSS, images, fonts, and critical requests.
- [ ] Prioritize slow devices and realistic network conditions.
- [ ] Capture baseline before changes.

## 2. Loading and assets

- [ ] Use modern image formats and responsive `srcset` / sizes where appropriate.
- [ ] Set image dimensions or aspect ratio to prevent layout shift.
- [ ] Lazy-load below-the-fold images; do not lazy-load the likely LCP image.
- [ ] Compress and resize assets to their actual display dimensions.
- [ ] Use video only when it adds value; provide poster and sensible loading behavior.
- [ ] Subset / preload fonts carefully; avoid excessive font families and weights.
- [ ] Preload only truly critical resources.
- [ ] Avoid unnecessary third-party scripts and trackers.

## 3. JavaScript and rendering

- [ ] Remove unused dependencies and dead code.
- [ ] Split code by route or feature where useful.
- [ ] Avoid shipping large libraries for trivial interactions.
- [ ] Defer non-critical work and hydrate only where needed.
- [ ] Prevent long main-thread tasks.
- [ ] Memoize only when profiling indicates benefit.
- [ ] Avoid layout thrashing and expensive repeated calculations.
- [ ] Virtualize genuinely large lists; do not add complexity to small lists.
- [ ] Avoid unnecessary re-renders and oversized client state.

## 4. Server, network, and caching

- [ ] Measure server response time and backend bottlenecks.
- [ ] Use caching with explicit freshness, invalidation, and privacy rules.
- [ ] Compress responses and use HTTP caching appropriately.
- [ ] Reduce request waterfalls; parallelize independent requests safely.
- [ ] Use CDN / edge delivery where it benefits the audience.
- [ ] Optimize database queries behind slow endpoints.
- [ ] Set timeouts and avoid unbounded retries.
- [ ] Ensure personalized or sensitive responses are not publicly cached.

## 5. Visual stability and responsiveness

- [ ] Reserve space for images, ads, embeds, and dynamic components.
- [ ] Avoid inserting content above existing content unexpectedly.
- [ ] Ensure font loading does not create severe layout shifts.
- [ ] Keep interactions responsive during network and CPU load.
- [ ] Avoid animation of layout-triggering properties where possible.
- [ ] Test on lower-end mobile hardware and throttled networks.

## 6. Verification

- [ ] Re-run the same tests / pages as the baseline.
- [ ] Compare before and after, including regressions.
- [ ] Use Lighthouse / PageSpeed / browser performance tooling appropriately.
- [ ] Check real-user monitoring when available.
- [ ] Verify no accessibility, SEO, or visual quality regressions.
- [ ] Report metric values, test conditions, and measurement type.
- [ ] Do not claim Core Web Vitals are “passed” based only on one lab run.

## Definition of done

Performance bottlenecks are evidence-based, changes are measured against baseline, user experience remains intact, and trade-offs are documented.

## `/improve performance` — measurement-led optimization mode

- [ ] Capture a reproducible baseline on key routes and representative devices / networks.
- [ ] Separate field metrics from lab measurements.
- [ ] Identify the actual bottleneck: server response, render-blocking resource, LCP asset, JS execution, layout shift, interaction delay, query, or third party.
- [ ] Prioritize the largest user-visible bottleneck.
- [ ] Apply the smallest effective change; avoid premature memoization or speculative caching.
- [ ] Re-measure under comparable conditions.
- [ ] Check visual, accessibility, SEO, and data-correctness regressions.
- [ ] Report before/after values, test conditions, and confidence.

Never claim a 10x speedup or Core Web Vitals success without comparable measurements.
