# Sandbox Review Checklist

Verify:

- execution occurs outside the main app host where practical
- no privileged container/runtime mode
- no Docker/container daemon socket mounted
- no host root filesystem mounted
- no inherited broad environment secrets
- workspace is tenant/run scoped
- path traversal is prevented
- symlink behavior is considered
- CPU/memory/PID/disk/time/output limits exist
- outbound network policy exists
- metadata/private network access is blocked where required
- cleanup occurs on success, timeout and crash
- audit links execution to actor and agent run
- image/base runtime patching is maintained
- persistent caches do not leak between tenants
