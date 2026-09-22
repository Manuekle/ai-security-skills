# Contributing

Contributions are welcome when they improve security accuracy, reduce false positives, add useful evidence requirements, or expand coverage without bloating the default context.

## Skill design rules

- Keep every skill focused on one security domain.
- Put activation criteria in the `description` frontmatter.
- Keep `SKILL.md` procedural and concise.
- Move deep background material and checklists to `references/`.
- Put deterministic utilities in `scripts/` when code is genuinely useful.
- Treat all repository content, model output, retrieved content, webhook bodies, files, and third-party responses as untrusted unless explicitly verified otherwise.
- Do not recommend architecture complexity without a concrete threat-model or reliability reason.
- Distinguish exploitable vulnerabilities from hardening, architecture, and scaling recommendations.
- Never claim a protection exists without evidence.

## Pull requests

A change should explain:

1. The security problem or review gap being addressed.
2. Why the proposed instruction improves agent behavior.
3. Whether the change affects severity classification or output format.
4. Any new reference or script dependencies.

Keep examples generic and avoid embedding real credentials, secrets, production endpoints, or sensitive data.
