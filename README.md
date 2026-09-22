# AI Security Skills

[![skills.sh](https://skills.sh/b/Manuekle/ai-security-skills)](https://skills.sh/Manuekle/ai-security-skills)

A modular security architecture skill suite for AI-native applications, autonomous agents, tool-calling systems, APIs, webhooks, sandboxes, RAG pipelines, and production infrastructure.

The suite is designed around a simple security principle:

```text
AI
-> propose action
-> validate
-> authorize
-> evaluate policy
-> execute through a constrained boundary
-> observe and audit
```

Never give an AI model unrestricted authority over infrastructure, credentials, data, or execution environments.

## Install

Install interactively and choose the skills you want:

```bash
npx skills add Manuekle/ai-security-skills
```

Install the complete suite non-interactively:

```bash
npx skills add Manuekle/ai-security-skills --yes
```

Install a specific skill:

```bash
npx skills add Manuekle/ai-security-skills --skill ai-security-architect
```

Short form:

```bash
npx skills add Manuekle/ai-security-skills@ai-security-architect
```

## Skills

| Skill | Purpose |
| --- | --- |
| `ai-security-architect` | Coordinates full AI architecture and security reviews and routes deep analysis to the specialist skills. |
| `api-security` | Reviews authentication, authorization, sessions, API keys, CORS/CSRF, validation, rate limiting, idempotency, and tenant isolation. |
| `agent-tool-security` | Reviews agent authority, tool calling, policy engines, prompt injection, approvals, model-output validation, and autonomous budgets. |
| `sandbox-execution-security` | Reviews shell/code/browser execution, sandbox isolation, filesystem boundaries, egress controls, SSRF defenses, and resource limits. |
| `webhook-security` | Reviews signatures, replay protection, event validation, deduplication, idempotency, queues, and outbound webhook controls. |
| `data-rag-security` | Reviews databases, uploads, object storage, RAG, vector search, memory, retrieval authorization, and tenant boundaries. |
| `production-security` | Reviews secrets, service identity, workers, durable workflows, resilience, observability, audit logs, backups, and incident readiness. |

## Recommended starting point

For a full repository review, install or enable `ai-security-architect` and ask your agent:

```text
Audit this repository using the AI security architecture skills.

Map the architecture first. Identify trust boundaries, public attack surfaces,
model-to-tool action paths, privileged execution paths, data boundaries, and
production dependencies.

Do not modify code during the first pass.

Separate verified vulnerabilities from architectural risks, hardening advice,
and scalability recommendations. Mark anything that cannot be verified as
UNKNOWN — needs verification.

Produce a P0-P3 remediation plan and the smallest safer target architecture.
```

## Examples

### API review

```text
Review the API security architecture. Focus on authentication, authorization,
tenant isolation, rate limiting, idempotency, input validation, sessions,
service-to-service authentication, and sensitive endpoints.
```

### Agent and tool review

```text
Review all agent and tool-calling paths. Identify every side effect an LLM can
cause and verify that model output is validated, authorized, policy-checked,
bounded, and audited before execution.
```

### Sandbox review

```text
Review all shell, code, and browser execution paths. Verify isolation from the
host, credentials, internal networks, other tenants, and unrestricted egress.
```

## Repository layout

```text
skills/
├── ai-security-architect/
│   ├── SKILL.md
│   ├── references/
│   └── scripts/
├── api-security/
│   ├── SKILL.md
│   └── references/
├── agent-tool-security/
│   ├── SKILL.md
│   └── references/
├── sandbox-execution-security/
│   ├── SKILL.md
│   └── references/
├── webhook-security/
│   ├── SKILL.md
│   └── references/
├── data-rag-security/
│   ├── SKILL.md
│   └── references/
└── production-security/
    ├── SKILL.md
    └── references/
```

## Design principles

- Keep model authority smaller than application authority.
- Prefer capability-specific tools over unrestricted interfaces.
- Keep authentication, authorization, policy, and execution as separate boundaries.
- Treat model output and retrieved external content as untrusted.
- Use least privilege for users, services, agents, tools, credentials, and tenants.
- Bound autonomous execution by time, steps, tool calls, cost, and concurrency.
- Require stronger isolation as execution capability becomes more general.
- Preserve evidence: do not claim a vulnerability without a concrete path or verified missing control.
- Prefer the smallest architecture that satisfies the threat model.

## Publishing on skills.sh

This repository is compatible with the `skills` CLI. skills.sh ranks repository-backed skills using anonymous installation telemetry from the CLI. Once the public GitHub repository exists, users can install from `Manuekle/ai-security-skills` and the skills can be surfaced by skills.sh based on installs.

## License

MIT License. See [LICENSE](./LICENSE).
