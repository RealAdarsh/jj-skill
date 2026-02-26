# Cross-Agent Instruction Design

Use these rules when adapting this skill for additional agent runtimes.

## Core Practices

1. Keep one canonical operational source (`SKILL.md`).
2. Keep adapter files small and composable (`AGENTS.md`, `CLAUDE.md`, `GEMINI.md`).
3. Use explicit command examples over abstract policy text.
4. Keep instructions close to the code they control (repository root for repo-wide behavior).
5. Minimize interactive assumptions; prefer non-interactive command forms.

## Why This Repo Uses Adapter Files

1. `AGENTS.md` is a shared baseline for agent coding behavior.
2. `CLAUDE.md` and `GEMINI.md` import the shared baseline to avoid drift.
3. `openai.yaml` provides UI metadata for platforms that support skill catalogs.

## Maintenance Checklist

1. Update `SKILL.md` first.
2. Update references (`cheat-sheet.md`, `colocated-git.md`) next.
3. Update adapters (`AGENTS.md`, `CLAUDE.md`, `GEMINI.md`) last.
