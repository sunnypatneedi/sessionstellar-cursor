---
name: score-file
description: Score an exported AI session file (.md, .txt, .jsonl) for orchestration quality
---

# Score File

Score an AI session transcript file from disk.

## Trigger

Use when the user has an exported session file (from Claude Code, Cursor, Windsurf, or Gemini) and wants to evaluate its orchestration quality.

## Workflow

1. Ask the user for the file path if not provided
2. Use the `score_session_file` MCP tool with the file path
3. Present the full score breakdown with per-metric analysis

## Input

A path to a session file. Supported formats:
- `.md` — Markdown session exports
- `.txt` — Plain text transcripts
- `.jsonl` — JSON Lines format

## Output

- **Overall score** (0-100) with quality tier
- **Per-metric breakdown** with bar visualization
- **Signals detected**: skills, agents, decisions, errors recovered, compound learnings
- **Complexity classification**: simple, moderate, or complex

## Constraints

- File must exist and be readable
- Empty files or files with no orchestration signals will score low
- Scoring is offline — no network calls, no data leaves your machine
