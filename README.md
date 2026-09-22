# AI Security Skills Suite

A modular Agent Skills package for architecture and security reviews of AI-enabled applications.

## Skills

- `ai-security-architect` — orchestrator and architecture review
- `api-security` — API/auth/authz/rate limits/multi-tenancy
- `agent-tool-security` — agents, tools, policy, prompt injection, budgets
- `sandbox-execution-security` — shell/code/browser isolation and network egress
- `webhook-security` — webhook authenticity, replay protection and idempotency
- `data-rag-security` — databases, files, memory, vector search and RAG
- `production-security` — secrets, service identity, workers, observability and resilience

Each folder is independently usable as an Agent Skill and follows the `SKILL.md` + optional `references/`, `scripts/`, `assets/` convention.

Start with `ai-security-architect` for full-system reviews. It routes deeper work to the relevant specialist skills.
