---
name: api-security
description: Review or design API security for AI and non-AI services, including authentication, authorization, RBAC/ABAC, sessions, API keys, CORS, CSRF, request validation, rate limiting, idempotency, multi-tenancy, middleware ordering, service-to-service access, and error handling. Use whenever an application exposes HTTP/RPC endpoints, public APIs, internal service APIs, admin APIs, or user/workspace scoped resources.
---

# API Security

Review APIs as explicit trust boundaries.

## Workflow

1. Enumerate all externally and internally reachable routes.
2. Classify routes as public, authenticated, privileged, webhook, internal, or admin.
3. Trace middleware order and confirm enforcement occurs before business logic.
4. Verify resource-level authorization, not only authentication.
5. Verify tenant/workspace scope at the data access boundary.
6. Review abuse controls and operational failure behavior.

## Authentication

Verify:

- session/token validation
- issuer/audience where applicable
- expiration
- revocation/rotation strategy
- secure cookie settings for browser sessions
- no credentials in URLs
- no authentication bypass on alternate methods/routes

Keep authentication distinct from authorization.

## Authorization

For each resource operation verify:

```text
actor -> action -> resource -> tenant/workspace -> policy decision
```

Prefer explicit ownership or policy checks. Do not rely on client-provided tenant IDs without binding them to the authenticated identity.

Use RBAC for broad capabilities and ABAC/resource checks for contextual constraints where necessary.

## Validation

Validate path, query, headers and body at the boundary using explicit schemas.

Reject unexpected fields for security-sensitive actions when practical. Normalize values before authorization when canonicalization matters.

## Rate limits

Select keys based on abuse model:

- IP
- account/user
- API key
- workspace/organization
- endpoint/action
- tool/model consumption

Expensive or side-effecting routes usually need stricter limits than cheap reads.

## Browser protections

Review:

- CORS allowlist
- CSRF controls for cookie-authenticated state changes
- `HttpOnly`, `Secure`, appropriate `SameSite`
- CSP and relevant security headers
- origin assumptions

## Idempotency

Use idempotency for operations that clients, workers, or providers may safely retry. Bind idempotency keys to appropriate actor/action scope and define retention behavior.

## Multi-tenancy

Verify tenant isolation in both authorization and query construction. Look for direct-object references, unscoped list/detail routes, cache key collisions and cross-tenant background jobs.

## Internal APIs

Do not treat "internal network" as identity. Use scoped service identity where the threat model requires it.

## Errors

Return stable external error codes and correlation IDs. Keep stack traces, secrets, provider payloads and sensitive internal details out of client responses.

## Output

Report verified controls, vulnerabilities, unknowns, and minimal recommended fixes. Include middleware/order diagrams when ordering affects security.

## Additional resources

Read `references/checklist.md` for a detailed endpoint checklist.
