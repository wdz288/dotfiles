---
alwaysApply: true
---

# Memory — Persistent Agent Memory

- Long-term memory across sessions
- Append entries when learning something worth remembering
- Ding curates this file periodically
- Add learned preferences, technical decisions, lessons, project context, and user habits

## How to Add Entries

### [Topic/Title]
[What was learned or decided]
_Added: YYYY-MM-DDTHH:MM:SSZ_

## Maintenance Rule
- When file exceeds 120 lines, summarize older entries into Archive
- Keep recent and critical entries in active sections

## Lessons Learned
### Kimi K2.5 excluded from agent recommendations (2026-03-20)
Kimi K2.5 has 8+ open GitHub issues for tool-calling failures in OpenCode: planning mode produces 0 tool calls, tools rendered as plain text instead of structured calls, HTTP 400 errors with thinking mode. Do NOT assign Kimi K2.5 to any agent.
_Added: 2026-03-20T13:55:00Z_

## Technical Decisions
### OpenCode free models ranked by capability (2026-03-21 updated)
After benchmark and community research:
**MiMo V2 Pro Free**: Best for reasoning (1M context, #8 globally, agent-optimized). Does NOT support thinking/reasoning params — routes through 'opencode' provider which is not in THINKING_CONFIGS.
**MiniMax M2.5 Free**: Highest SWE-bench (80.2%) but has tool-calling bugs
**Big Pickle (GLM-4.6)**: Solid for planning, context degrades at 50-70K tokens
**Kimi K2.5**: EXCLUDED — planning mode broken, tool calls as plain text

### Master Agent Docs Suite (2026-02-17)
Created 9-file OpenClaw-inspired documentation suite:
- ~/.claude/rules/soul.md, user-prefs.md, memory.md (auto-loaded)
- ~/.agents/skills/ (5 skill files: dev, debug, research, code-review, architecture)
- ~/.gemini/GEMINI.md (auto-generated from soul + user-prefs for Antigravity)
- Source of truth: ~/.claude/rules/ — GEMINI.md regenerated from it
_Added: 2026-02-17_

### Agent model configuration (2026-03-21)
Config file: ~/.config/opencode/oh-my-opencode.json
Format: agents{} and categories{} objects with model: "provider/model-id"
MiMo V2 Pro Free: Reasoning agents (sisyphus, oracle, librarian, metis, ultrabrain, deep, artistry)
Big Pickle: Planning/reliability agents (hephaestus, prometheus, momus)
MiniMax M2.5 Free: Quick tasks, visual-engineering (explore, atlas, quick, unspecified-low, unspecified-high, writing)
MiMo V2 Omni Free: Multimodal tasks (multimodal-looker)
_Added: 2026-03-21T14:15:00Z_

## User Preferences Discovered

### Ding's pet peeves
- AI follows instructions blindly without thinking of better alternatives
- Must ask "what problem are we solving?" before starting
- Never read credential files — guide to create credential doc instead
_Added: 2026-02-17_

## Project Context

## Miscellaneous

## Archive

### OpenCode skills location on Windows (2026-03-21)
~/.config/opencode/skills/ is the working path on Windows (NOT ~/.agents/skills/ which has a known bug on Windows per issue #17007). Skills are folder-based with SKILL.md files.
_Added: 2026-03-21T06:18:00Z_

### Anthropic official skills installed (2026-03-21)
Installed from anthropics/skills repo: skill-creator, xlsx, docx to ~/.config/opencode/skills/. Also installed obra/superpowers to ~/.config/opencode/.opencode/superpowers/. Used curl+tar instead of git (git not in PATH on Ding's Windows machine). xlsx requires pandas+openpyxl Python deps. docx requires docx npm + pandoc.
_Added: 2026-03-21T06:18:00Z_

### Model config update: MiMo restored (2026-03-21)
MiMo V2 Pro Free restored to reasoning agents after confirming it works via `opencode models --refresh`.
Current config: sisyphus, oracle, librarian, metis, ultrabrain, deep, artistry → mimo-v2-pro-free. hephaestus, prometheus, momus → big-pickle. quick tasks → minimax-m2.5-free.
_Added: 2026-03-21T14:15:00Z_

### Bash shell quirk on Windows (2026-03-21)
The system prepends 'export CI=true...' to bash commands that start with that line. Commands starting with other commands (npm, npx, curl, dir, mkdir, xcopy) work fine. Workaround: use curl+tar instead of git, or use forward-slash paths in node.
_Added: 2026-03-21T06:18:00Z_
### MiMo V2 Pro/Omni status (2026-03-21)
MiMo V2 Pro/Omni WORKS in OpenCode. The 400 errors were transient (Zen API deployment delay). After running `opencode models --refresh`, MiMo works correctly.
Key: MiMo routes through 'opencode' provider which has no THINKING_CONFIGS entry, so no reasoning params are sent.
IMPORTANT: Never specify thinking/reasoning level for MiMo — it doesn't support those parameters.
_Added: 2026-03-21T14:15:00Z_
