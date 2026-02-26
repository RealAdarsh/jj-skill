# AGENTS.md

Shared instructions for AI coding agents working in this repository.

## Goal

Maintain and improve the reusable Jujutsu skill in this repository so it works reliably across agent runtimes.

## Canonical Source of Truth

1. Treat `SKILL.md` as the canonical workflow.
2. Keep supporting references in `references/` concise and task-focused.
3. Keep UI metadata in `agents/openai.yaml` aligned with skill behavior.

## Cross-Agent Compatibility Rules

1. Keep instructions deterministic and non-interactive by default.
2. Use small, composable instruction files (`AGENTS.md`, `CLAUDE.md`, `GEMINI.md`) instead of duplicating large prompt blocks.
3. Preserve identical operational guidance across adapters unless the platform requires a clear exception.

## Update Workflow

1. Validate command examples against official Jujutsu docs before editing workflows.
2. Update `SKILL.md` first.
3. Update references and adapters after core changes.
4. Update `references/sources.md` when adding or replacing external guidance.
