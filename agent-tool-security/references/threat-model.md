# Agent Threat Model

Review these classes:

## Authority confusion
The model proposes an action outside the authenticated user's authority.

## Indirect prompt injection
Untrusted content attempts to alter the agent's priorities, permissions or tool use.

## Tool argument manipulation
Model-generated arguments target a different tenant, resource or environment than intended.

## Excessive agency
The agent has broader tools, scopes, budgets or runtime than the user goal requires.

## Secret exposure
Credentials, internal tokens, environment values or private tool responses enter model context or logs.

## Unsafe composition
Two individually safe tools compose into a higher-risk path.

## Loop amplification
The agent repeatedly invokes expensive or side-effecting operations.

## Cross-run contamination
Memory, scratch state, cache or tool results leak across users/tenants/runs.

## Approval bypass
A sensitive action can be reframed, retried or invoked through an alternate tool path that skips approval.
