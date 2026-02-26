# jj-skill

Open-source, generic Jujutsu (`jj`) agent skill repository.

This repo is intentionally just the `jj` skill payload, plus lightweight adapter files for common agent runtimes.

## Repository layout

```text
jj-skill/
├── AGENTS.md
├── CLAUDE.md
├── GEMINI.md
├── LICENSE
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── cheat-sheet.md
    ├── colocated-git.md
    ├── cross-agent.md
    └── sources.md
```

## Skill files

- `SKILL.md`: canonical operational instructions
- `references/`: supporting docs and command mappings
- `agents/openai.yaml`: optional metadata for skill catalogs that support it

## Cross-agent adapters

- `AGENTS.md`: generic shared agent guidance
- `CLAUDE.md`: Claude adapter (imports `AGENTS.md`)
- `GEMINI.md`: Gemini adapter (imports `AGENTS.md`)

## Design goals

- Prefer `jj` commands for repository mutations.
- Keep workflows non-interactive by default for automated agents.
- Keep instructions portable across agent runtimes.

## Sources

Primary references are documented in [references/sources.md](./references/sources.md).
