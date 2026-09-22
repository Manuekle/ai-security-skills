# Secure Tool Contract

For each tool define:

```yaml
name: resource.action
risk: low | medium | high | critical
side_effect: none | internal | external
requires_approval: false
required_capabilities: []
timeout_ms: 10000
rate_limit_scope: user+workspace
```

Then specify:

1. Strict input schema.
2. Canonical resource identifiers.
3. Server-derived tenant/workspace scope.
4. Deterministic authorization check.
5. Optional policy decision.
6. Credential injection after authorization.
7. Bounded execution.
8. Typed/sanitized result.
9. Audit event.

Do not let the model supply trusted identity fields that the server can derive itself.
