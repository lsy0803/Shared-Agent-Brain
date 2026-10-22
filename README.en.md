# Shared Agent Brain

A lightweight, file-based workflow for trusted agents to share and maintain knowledge. Includes a Markdown / Obsidian starter and a portable Skill.

[中文](README.md) · [Workflow](vault/00_Home/WORKFLOW.md) · [Skill](skills/shared-vault/SKILL.md)

Authorized agents can maintain the projects they work on directly. There is no mandatory central reviewing agent.

- Retrieve context by task, then read the relevant sources.
- Reuse stable context already read in the current session.
- Preserve other agents' valid work; correct errors with evidence.
- Keep user statements, verified facts, inferences and unknowns distinct.
- Use proposals for unresolved disputes or concurrent handoffs, not every edit.

## Use the starter

Copy `vault/` **outside this public checkout** into a private directory. Open that folder in Obsidian or a Markdown editor. Give your agent its absolute path, authorize the intended access, and ask it to read the starter's AGENTS.md and relevant project context.

Do not fill the public starter with real personal data. Its sample project is fictional.

## Use the Skill

Copy `skills/shared-vault/` into a supported project-local skill directory such as `.agents/skills/shared-vault/`. Tell the agent your actual private vault path. Tools without skill discovery can read SKILL.md directly. Discovery and filesystem permissions depend on the host; this package does not grant permissions.

## What this is

Documentation, an instruction-based Skill, and empty templates. No dependencies are required to use the Markdown starter. Most detailed starter documentation is currently in Chinese; the Skill is written in English.

This is not an automatic memory service. It does not implement embeddings, background ingestion, sync, caches, file locking or guaranteed conflict-free writes. A file hash detects changes; it is not a lock.

See [design and sources](docs/DESIGN.md), [contributing](CONTRIBUTING.md) and the [MIT license](LICENSE). Initial release: v0.1.0.
