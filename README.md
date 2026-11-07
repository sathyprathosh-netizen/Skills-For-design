# World-Class Web Product Skills

A practical, anti-slop skill system for AI coding agents and human builders. It is designed to be copied into a workspace and adapted—not treated as a magic prompt or a guarantee of commercial success.

## Structure

```text
worldclass-web-skills/
├── README.md
├── GLOBAL-OPERATING-SYSTEM.md
├── IMPROVEMENT-PROTOCOL.md
├── ui-ux-design/SKILL.md
├── frontend-development/SKILL.md
├── backend-development/SKILL.md
├── database-design/SKILL.md
├── web-security/SKILL.md
├── seo-optimization/SKILL.md
├── accessibility/SKILL.md
├── performance/SKILL.md
└── code-review/SKILL.md
```

## Install

- **Claude Code:** place the relevant skill folders in the project's `.claude/skills/` directory, or in your user-level skills directory if you want them available across projects. Keep the folder name and `SKILL.md` together.
- **Antigravity / other agents:** add the relevant `SKILL.md` files to the agent's supported skills/rules location. Product support and global-vs-project paths can change; verify the current documentation for your installed version.
- **Any agent:** paste `GLOBAL-OPERATING-SYSTEM.md` into the workspace's top-level agent instructions if folder-based skill discovery is unavailable.

Do not assume a workspace folder syncs across devices. For portability, keep this bundle in a private Git repository or synced cloud folder, then clone/sync it on each machine.

## How to use

1. Start a project and invoke the relevant skill.
2. The agent must run the **Project Identity Gate** in `GLOBAL-OPERATING-SYSTEM.md` before design or implementation.
3. Complete only the fields relevant to the task. If the user already supplied a current design system, reuse it and confirm only uncertain or conflicting values. Do not ask the same questions repeatedly.
4. Work in small, verifiable phases. Inspect the existing code before changing it.
5. Run the relevant checklists and report evidence, unresolved risks, and exact files changed.
6. After delivery, invoke `/improve design`, `/improve security`, `/improve performance`, or `/improve all` for evidence-based iterative refinement. See `IMPROVEMENT-PROTOCOL.md`.

## Quality promise

These skills aim to reduce generic AI output through explicit discovery, design rationale, real content, implementation constraints, and verification. They cannot guarantee a “world-class” result automatically. The result depends on product strategy, user research, source quality, engineering constraints, and testing with real users.
