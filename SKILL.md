---
name: backend-development
description: Design and implement secure, observable, maintainable APIs, authentication, business logic, and integrations.
---

# Backend Development Skill

Follow `GLOBAL-OPERATING-SYSTEM.md`. Complete the identity gate; confirm product goals, data sensitivity, deployment environment, and expected load before architecture decisions.

## 1. Discovery and contracts

- [ ] Inspect current runtime, framework, deployment, routes, middleware, and dependency versions.
- [ ] Identify actors, roles, permissions, core entities, and business invariants.
- [ ] Define API contracts: method, path, auth, request, response, status codes, pagination, errors.
- [ ] Define expected traffic, latency, availability, and data retention needs; do not invent scale requirements.
- [ ] Identify third-party services, secrets, rate limits, and failure modes.
- [ ] Keep API behavior backward-compatible unless a breaking change is approved.

## 2. API design

- [ ] Use resource-oriented, consistent naming and appropriate HTTP methods.
- [ ] Validate and normalize all untrusted input at the boundary.
- [ ] Use consistent response and error formats without leaking internals.
- [ ] Add pagination and bounded query parameters for collection endpoints.
- [ ] Use idempotency for operations where duplicate execution is costly.
- [ ] Apply timeouts, retries with backoff, and circuit-breaking where appropriate.
- [ ] Version APIs when compatibility requires it.
- [ ] Document authentication, authorization, rate limits, and examples.

## 3. Authentication and authorization

- [ ] Choose an established identity provider / protocol where appropriate; do not invent cryptography.
- [ ] Distinguish authentication (who) from authorization (what they can do).
- [ ] Enforce authorization server-side on every protected operation.
- [ ] Deny by default; use least privilege.
- [ ] Secure sessions / tokens, expiry, rotation, revocation, and logout.
- [ ] Protect account recovery and email / phone verification flows.
- [ ] Avoid trusting client-supplied user IDs, roles, prices, or ownership claims.
- [ ] Consider CSRF for cookie-authenticated state-changing requests.

## 4. Business logic and reliability

- [ ] Keep business invariants in trusted server-side code.
- [ ] Use transactions for multi-step data changes that must succeed together.
- [ ] Handle concurrency and duplicate requests.
- [ ] Validate state transitions; do not accept impossible status changes.
- [ ] Make external integrations resilient to timeouts and partial failure.
- [ ] Use queues for work that should not block a request, where justified.
- [ ] Design safe retries and dead-letter / recovery paths for asynchronous work.
- [ ] Use structured logs, metrics, traces, and correlation IDs without logging secrets or sensitive payloads.

## 5. Security and privacy

- [ ] Store secrets in managed environment / secret storage, never source control.
- [ ] Use TLS in transit and appropriate encryption at rest.
- [ ] Apply rate limits and abuse controls to login, signup, OTP, search, and costly endpoints.
- [ ] Prevent mass assignment and excessive data exposure.
- [ ] Avoid unsafe file uploads; validate size, type, content, and storage permissions.
- [ ] Minimize personal data; define retention and deletion behavior.
- [ ] Return generic auth errors where detailed errors enable account enumeration.
- [ ] Review dependency vulnerabilities and patch strategy.

## 6. Testing and operations

- [ ] Unit-test business rules and boundary conditions.
- [ ] Integration-test database, auth, and external service behavior.
- [ ] Test unauthorized, forbidden, malformed, duplicate, and rate-limited requests.
- [ ] Test transaction rollback and concurrent updates where relevant.
- [ ] Add health/readiness checks appropriate to deployment.
- [ ] Ensure migrations and rollback / recovery are planned.
- [ ] Document environment variables and deployment steps.
- [ ] Verify logs and monitoring provide useful signals without exposing data.

## Definition of done

API contract documented, authorization enforced, input validated, failure paths handled, tests run, migrations considered, secrets protected, and operational limitations clearly reported.

## `/improve backend` — service refinement mode

- [ ] Trace the target request from route through auth, validation, business logic, data access, and external services.
- [ ] Inspect contracts, authorization boundaries, failure handling, concurrency, and observability.
- [ ] Prioritize correctness, security, data integrity, and reliability before stylistic refactoring.
- [ ] Improve validation, idempotency, timeouts, retries, transactions, and error semantics where evidence supports it.
- [ ] Preserve API compatibility or explicitly document breaking changes.
- [ ] Add tests for the defect or risk, including negative and boundary cases.
- [ ] Run relevant integration tests and report exact outcomes.
- [ ] Check database and security implications of the changes.

Never expose secrets, weaken authorization, or claim scalability without workload evidence.
