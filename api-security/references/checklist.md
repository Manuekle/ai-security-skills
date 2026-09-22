# API Security Checklist

For each endpoint record:

- method/path
- exposure
- auth requirement
- allowed roles/capabilities
- tenant/resource rule
- input schema
- output sensitivity
- rate limit
- idempotency behavior
- side effects
- audit requirement

Check for:

- object-level authorization gaps
- function-level authorization gaps
- mass assignment
- unsafe defaults in optional auth middleware
- wildcard CORS with credentials
- missing CSRF protection for cookie-authenticated writes
- overly broad API keys
- long-lived bearer tokens
- sensitive data in query strings
- inconsistent middleware between route aliases/versions
- unrestricted pagination/export endpoints
- request size abuse
- missing concurrency limits on expensive actions
- cache keys missing tenant/user context
