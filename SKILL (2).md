---
name: database-design
description: Model reliable, secure, evolvable data structures and query patterns for application workloads.
---

# Database Design Skill

Follow `GLOBAL-OPERATING-SYSTEM.md`. Confirm product entities, data ownership, sensitivity, retention, expected access patterns, and database technology before designing schemas.

## 1. Requirements before schema

- [ ] Identify entities, attributes, relationships, and lifecycle.
- [ ] Identify source of truth for each field.
- [ ] Define ownership / tenant boundaries and access rules.
- [ ] List read and write patterns before choosing indexes.
- [ ] Identify uniqueness, ordering, consistency, and transactional requirements.
- [ ] Classify sensitive, personal, financial, and public data.
- [ ] Estimate record volume and growth only from evidence or explicit assumptions.

## 2. Data modelling

- [ ] Use clear, consistent names and appropriate types.
- [ ] Define primary keys and stable identifiers.
- [ ] Enforce required fields, uniqueness, and referential integrity where supported.
- [ ] Model cardinality correctly; avoid embedding unbounded arrays or uncontrolled duplication.
- [ ] Normalize to reduce update anomalies; denormalize only for a measured access-pattern reason.
- [ ] Define nullability and defaults deliberately.
- [ ] Store timestamps consistently (typically UTC) and distinguish event time from update time.
- [ ] Use decimal-safe types for money; never use binary floating point for currency.
- [ ] Define soft-delete vs hard-delete behavior and retention policy.
- [ ] Add tenant / organization scoping where the product is multi-tenant.

## 3. Query and index design

- [ ] Write representative queries before adding indexes.
- [ ] Index based on filters, joins, sorting, and selectivity.
- [ ] Avoid redundant indexes and excessive write amplification.
- [ ] Use pagination that remains stable under concurrent writes.
- [ ] Avoid N+1 query patterns.
- [ ] Inspect query plans for slow or high-volume paths.
- [ ] Set query timeouts and bounded result sizes.
- [ ] Avoid unbounded scans and unbounded user-controlled filters.

## 4. Integrity and concurrency

- [ ] Use database constraints as a final integrity boundary.
- [ ] Use transactions for atomic multi-record operations.
- [ ] Define isolation / concurrency strategy for critical updates.
- [ ] Handle race conditions, duplicate submissions, and idempotency.
- [ ] Use optimistic locking or version fields when appropriate.
- [ ] Ensure counters and balances cannot silently drift.
- [ ] Define cascade behavior explicitly; avoid accidental destructive cascades.

## 5. Migrations and recovery

- [ ] Use version-controlled migrations.
- [ ] Prefer backward-compatible expand → migrate → contract changes.
- [ ] Test migrations against representative data volume.
- [ ] Plan rollback or forward-fix strategy.
- [ ] Back up before risky transformations and verify restore procedures.
- [ ] Avoid destructive schema changes without explicit approval.
- [ ] Never run production migrations casually or without a recovery plan.

## 6. Privacy and security

- [ ] Restrict database credentials by environment and least privilege.
- [ ] Enforce row / tenant access rules in trusted layers or database policies.
- [ ] Encrypt sensitive fields when the threat model requires it.
- [ ] Do not store passwords in plaintext; use a suitable password hashing scheme through a trusted auth library.
- [ ] Avoid logging raw records or secrets.
- [ ] Define deletion, export, and retention behavior where applicable.
- [ ] Use synthetic or anonymized data in development and tests.

## 7. Review checklist

- [ ] Schema matches actual domain language.
- [ ] Constraints protect business invariants.
- [ ] Indexes match demonstrated query patterns.
- [ ] Migrations are safe and tested.
- [ ] Data access is tenant-safe and permission-aware.
- [ ] Backup and restore expectations are documented.
- [ ] Performance has been checked on realistic data, not only tiny fixtures.

## `/improve database` — data-layer refinement mode

- [ ] Inspect schema, constraints, migrations, representative queries, and data access code.
- [ ] Identify integrity gaps, tenant isolation risks, slow queries, redundant indexes, and unsafe migrations.
- [ ] Use query plans and representative data before proposing performance changes.
- [ ] Strengthen constraints and transactions around real business invariants.
- [ ] Make migrations backward-compatible where feasible and define recovery steps.
- [ ] Preserve existing data and avoid destructive changes without explicit approval.
- [ ] Test migration behavior and critical queries.
- [ ] Report measured query / integrity improvements and unverified assumptions.

Do not denormalize or add indexes as guesswork.
