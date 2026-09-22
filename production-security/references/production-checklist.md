# Production Readiness Checklist

## Identity and secrets
- separate production credentials
- scoped service identities
- credential rotation procedure
- emergency revocation path

## Runtime
- resource/concurrency limits
- dependency/runtime patch policy
- environment separation
- safe deployment and rollback

## Async work
- idempotent jobs
- retry/backoff/jitter
- dead-letter handling
- worker visibility/alerts

## Data
- backup schedule
- restore test
- migration rollback/forward plan
- retention/deletion behavior

## Observability
- request and trace correlation
- security event logs
- latency/error metrics
- agent/tool/cost metrics
- alerts tied to meaningful failure conditions

## Emergency controls
- disable risky tool
- pause agent runs
- revoke provider key
- deny tenant/user
- isolate execution service
- switch provider/fallback mode
