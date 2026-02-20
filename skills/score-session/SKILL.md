---
name: score-session
description: Score the current AI coding session for orchestration quality across 5 metrics
---

# Score Session

Analyze the current conversation and score it for AI orchestration quality.

## Trigger

Use when you want to evaluate how well this coding session used AI orchestration patterns — tool diversity, decision-making, error recovery, and compound learning.

## Workflow

1. Gather the current session context — tools invoked, decisions made, errors encountered, skills used
2. Use the `score_session` MCP tool to score the session content
3. Present the score breakdown with actionable feedback

## Input

The full session transcript or a summary of the current conversation. If the user provides a specific session export file, use `score_session_file` instead.

## Output

- **Overall score** (0-100) with quality tier (Exceptional/Excellent/Good/Fair/Poor)
- **Per-metric breakdown**:
  - Skill Diversity (20%) — range of tools and skills invoked
  - Decision Depth (25%) — explicit tradeoffs and reasoning
  - Error Recovery (20%) — how errors were handled
  - Compound Learning (20%) — cross-step insights
  - Orchestration Mastery (15%) — agent coordination patterns
- **Actionable suggestions** for improving the score

## Constraints

- Score reflects orchestration quality, not code correctness
- Sessions with no tool use or decisions will score low — that's expected for simple tasks
- Scores are deterministic for the same input
