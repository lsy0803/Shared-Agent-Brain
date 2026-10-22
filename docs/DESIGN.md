# Design and sources

This starter is an independently written workflow informed by public, first-party projects. No third-party implementation code is bundled. Research observations are design references, not performance guarantees.

## Adopted ideas

- **Layered retrieval:** Claude-Mem searches a compact index, examines context, then fetches selected observations. We apply the idea using ordinary Markdown indexes and task-scoped search. [First-party search instructions](https://github.com/thedotmack/claude-mem/blob/main/plugin/skills/mem-search/SKILL.md).
- **Lean core, discoverable detail:** Letta Code keeps core memory concise and uses indexes for external/shared memory. It also reads current files before editing. We use the organizational pattern, not its runtime or automatic synchronization. [Pinned source](https://github.com/letta-ai/letta-code/blob/035bb8c8917b5dd94a3989d4adf04860a2ce8fea/src/agent/prompts/letta_root_memfs.md).
- **Scoped queries:** Mem0 searches by query and filters such as user, agent and run. Our starter uses project and topic scope without installing its dependencies. [Pinned search API](https://github.com/mem0ai/mem0/blob/2c81af3bbe27d9bccb09c772d583df9e9be72ee5/mem0/memory/main.py#L1393).
- **Avoid unconditional full reads:** Memory Bank MCP's instructions require reading all memory files before every task. We deliberately choose task-triggered reading for larger multi-project vaults. [First-party instructions](https://github.com/alioshr/memory-bank-mcp/blob/main/custom-instructions.md).

Sources were reviewed on 2026-10-22. Branch URLs can change. These projects have different licenses and architectures; this repository grants no rights to their code.

## Local choices

The user selects trusted agents. Those agents maintain their own work directly, regardless of model vendor. A central agent is not required.

Facts remain editable when better evidence arrives. Preserve current valid knowledge, record why an important conclusion changed, and keep unresolved conflict visible. The first author does not own the truth.

Avoid copying the full profile or history into every task. Source documents remain authoritative; a compact index or memory summary is only a discovery aid.

## Operational limits

Markdown rules guide agents; they do not enforce tool permissions, lock files, refresh another session, or prove cloud retention behavior. Hosts provide access and synchronization. Evaluate those facilities separately when needed.
