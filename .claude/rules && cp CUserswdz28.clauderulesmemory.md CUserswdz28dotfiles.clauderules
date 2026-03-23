---
alwaysApply: true
---

# User Preferences — Ding

## Rule Locations
- **Project rules:** `AGENTS.md` in project root
- **Global rules:** `.claude/rules` in home directory
- **Priority:** Project rules override global rules

## About Ding
- Name: Ding
- Call me: Ding
- Role: Full-stack developer
- Primary stacks: TypeScript/JavaScript, Python, Rust, Full-stack web
- Experience: Senior level — don't over-explain basics

## Environment
- OS: Windows
- AI tools: OpenCode (Antigravity), Antigravity IDE
- Shell: PowerShell / cmd
- Note: Use Windows-compatible commands (no bash-only syntax)

## Always Do
- Use venv for ALL Python projects — project-specific library isolation is mandatory
  - Always verify a venv exists before running pip install or python scripts
  - If none exists, ask if Ding wants one created
  - When running python, prefer explicit path (e.g., `.venv/Scripts/python script.py`) to guarantee correct environment
- Document every project change — include process flow in Mermaid format
- Flag security concerns in proposed solutions — don't wait to be asked
- Understand task objective before starting — clarify "what problem are we solving?"
- Update README.md when features change, behavior changes, or directory structure changes
  - Why: README.md is the Single Source of Truth

## Never Do
- NEVER read credential files (`.env`, `credentials.json`, `secrets.*`, API keys, tokens)
  - Instead: Guide Ding to create a credential setup doc or `.env.example`
  - Why: Security and trust — agent should never see real secrets
- NEVER install packages globally — always use project-level package management
- NEVER proceed on ambiguous tasks — stop and ask for clarification
- NEVER guess at requirements — explicit confirmation required
- NEVER create or maintain `.cursorrules` files — use `.agent/rules.md` for workspace rules
- NEVER delete files without permission — always ask first

## Preferences
- Documentation: Mermaid diagrams for all process flows, always keep README updated
- Naming: Descriptive over terse — `getUserAuthToken()` not `getToken()`
- Errors: Handle explicitly, surface clearly, never swallow silently
- Validation: When processing data, always provide verification (sample outputs, counts, before/after)
- Workspace rules: Store workspace-specific rules ONLY in `.agent/rules.md`

## Commit Rules
- **Always confirm before committing** — Show what will be committed, get user approval first
- **Never commit without asking** — Even for small changes
- **Show commit message** — User reviews before `git commit`
- **Show files to be staged** — User confirms which files to include

## Query Rules
- **Allow flexible natural language queries** — LLMs can understand "what is the highest total revenue brand"
- **Don't over-constrain query syntax** — Support both structured and free-form queries
- **Show available columns** — User knows what they can query
- **Mask column names in query** — Replace actual names with placeholders before sending to LLM
