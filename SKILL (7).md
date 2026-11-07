---
name: web-security
description: Threat-model and harden web applications, APIs, authentication, data handling, and deployment configuration.
---

# Web Security Skill

Follow `GLOBAL-OPERATING-SYSTEM.md`. Security work must begin with system boundaries, data classification, user roles, and deployment context. Never claim an application is “secure” based only on a code scan.

## 1. Threat modelling

- [ ] Identify assets: accounts, personal data, payment data, business records, secrets, infrastructure.
- [ ] Identify actors: anonymous users, normal users, admins, support staff, services, attackers.
- [ ] Map trust boundaries and data flows.
- [ ] List entry points: forms, APIs, uploads, webhooks, OAuth callbacks, admin routes, dependencies.
- [ ] Consider spoofing, tampering, repudiation, information disclosure, denial of service, and privilege escalation.
- [ ] Prioritize risks by likelihood, impact, and exploitability.
- [ ] Record assumptions and out-of-scope threats.

## 2. Authentication and access control

- [ ] Use proven authentication libraries / providers.
- [ ] Enforce server-side authorization on every protected resource and action.
- [ ] Check object ownership, tenant scope, and role on every request.
- [ ] Prevent insecure direct object references (IDOR/BOLA).
- [ ] Secure sessions, cookies, token storage, refresh, expiry, and revocation.
- [ ] Use secure, HttpOnly, SameSite cookies when cookie sessions are appropriate.
- [ ] Add CSRF protection where required by the auth model.
- [ ] Protect password reset, OTP, signup, and login against abuse and enumeration.
- [ ] Require stronger controls for privileged accounts and sensitive actions.

## 3. Input, output, and browser risks

- [ ] Validate input by schema, type, length, format, and allowed values.
- [ ] Use parameterized queries / safe ORM APIs.
- [ ] Encode output for its context; avoid unsafe HTML injection.
- [ ] Prevent XSS, SQL/NoSQL injection, command injection, SSRF, path traversal, and open redirects.
- [ ] Restrict CORS to known origins and required methods/headers.
- [ ] Set appropriate security headers and a considered Content Security Policy.
- [ ] Validate redirects and callback destinations.
- [ ] Sanitize rich text with a maintained sanitizer and a strict allowlist.

## 4. Secrets, files, and integrations

- [ ] Keep API keys and service credentials on trusted servers.
- [ ] Scan repository history and build output for leaked secrets.
- [ ] Use secret managers / protected environment variables.
- [ ] Rotate exposed credentials immediately.
- [ ] Verify webhook signatures and protect against replay.
- [ ] Restrict upload size, type, content, storage path, and execution permissions.
- [ ] Store uploads outside executable web roots or in isolated object storage.
- [ ] Set outbound network allowlists for SSRF-sensitive services.
- [ ] Apply timeouts and safe parsing to third-party responses.

## 5. Abuse resistance and resilience

- [ ] Rate-limit authentication and costly endpoints.
- [ ] Add quotas, bot protection, and abuse monitoring where justified.
- [ ] Bound payload sizes, query complexity, and execution time.
- [ ] Prevent resource exhaustion and uncontrolled file processing.
- [ ] Use idempotency for payment / order / webhook operations.
- [ ] Avoid leaking stack traces, database errors, or internal identifiers.
- [ ] Log security-relevant events without recording passwords, tokens, or sensitive data.

## 6. Dependency and deployment security

- [ ] Review direct and transitive dependencies.
- [ ] Remove unused packages and risky abandoned libraries.
- [ ] Pin / lock dependencies and apply security updates.
- [ ] Separate development, staging, and production credentials.
- [ ] Disable debug mode and verbose errors in production.
- [ ] Restrict admin and database access.
- [ ] Use TLS and secure deployment configuration.
- [ ] Back up critical data and test restoration.
- [ ] Define incident response and credential rotation steps.

## 7. Verification

- [ ] Run static analysis and dependency audit.
- [ ] Test unauthenticated, unauthorized, cross-tenant, malformed, and abusive requests.
- [ ] Test access to another user's object by changing identifiers.
- [ ] Test upload and webhook boundaries.
- [ ] Review logs for sensitive data leakage.
- [ ] Document findings by severity, exploit path, impact, and remediation.
- [ ] Retest fixes; do not mark a risk resolved without evidence.

For production or regulated systems, obtain a qualified security review / penetration test. This skill is a development checklist, not a certification.

## `/improve security` — adversarial refinement mode

- [ ] Re-map assets, trust boundaries, roles, entry points, and sensitive data flows.
- [ ] Review authentication, authorization, tenant isolation, object ownership, sessions, and recovery.
- [ ] Test realistic abuse cases: IDOR/BOLA, injection, XSS, CSRF, SSRF, upload abuse, replay, enumeration, and rate-limit bypass as applicable.
- [ ] Check secrets, dependency vulnerabilities, security headers, CORS, logging, and deployment configuration.
- [ ] Rank findings by exploitability and impact; fix critical/high findings first.
- [ ] Add regression tests for confirmed vulnerabilities.
- [ ] Retest the exploit path after remediation.
- [ ] State what was tested, what was not tested, and whether a professional penetration test is still warranted.

Do not call the system secure or certified based on a limited review. Never run destructive or intrusive tests against third-party systems without authorization.
