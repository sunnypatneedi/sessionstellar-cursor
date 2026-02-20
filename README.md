# SessionStellar for Cursor

**Score your AI coding sessions for orchestration quality — directly inside Cursor.**

## What It Does

SessionStellar scores AI sessions across 5 weighted metrics:

| Metric | Weight | What it measures |
|--------|--------|------------------|
| Skill Diversity | 20% | Range of tools and skills invoked |
| Decision Depth | 25% | Explicit tradeoffs and reasoning quality |
| Error Recovery | 20% | How errors are handled and recovered from |
| Compound Learning | 20% | Cross-step insights building on context |
| Orchestration Mastery | 15% | Agent coordination and balance |

Scores run **offline** — no data leaves your machine.

## Install

Search for **SessionStellar** in the Cursor marketplace, or run:

```
/add-plugin sessionstellar
```

## Usage

### Score the current session

Use the `/score-session` skill to analyze the current conversation:

```
/score-session
```

### Score a file from disk

Use the `/score-file` skill with an exported session transcript:

```
/score-file path/to/session.md
```

### MCP Tools

The plugin exposes two MCP tools:

- **`score_session`** — Score session content passed as text
- **`score_session_file`** — Score a session file by path

These are available to the AI agent automatically.

## Orchestration Quality Rule

The plugin includes an optional rule (`orchestration-quality`) with patterns for producing higher-quality AI orchestration: tool diversity, explicit decision-making, error recovery strategies, and compound learning.

Enable it in Cursor settings to get coaching toward better orchestration patterns.

## CLI & CI/CD

For scoring outside Cursor — in CI/CD pipelines, git hooks, or the terminal:

```bash
npx sessionstellar score session.md
```

See the [CLI package](https://www.npmjs.com/package/sessionstellar) for GitHub Actions and GitLab CI examples.

## Platform

Track scores over time and benchmark against the community at [sessionstellar.com](https://sessionstellar.com).

## License

MIT
