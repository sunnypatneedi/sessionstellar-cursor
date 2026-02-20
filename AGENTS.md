# AGENTS.md — AI Agent Instructions for SessionStellar Cursor Plugin

This file guides AI coding agents contributing to the SessionStellar Cursor plugin (`github.com/sunnypatneedi/sessionstellar-cursor`).

## Quick Rules

1. **Skills live in `skills/<name>/SKILL.md`** with YAML frontmatter
2. **Rules live in `rules/<name>.mdc`** with `alwaysApply: false` by default
3. **The MCP server is external** — it runs `@sessionstellar/mcp` via npx, not bundled here
4. **Test all skills/rules in Cursor** before submitting a PR

## Repository Structure

```
sessionstellar-cursor/
├── .cursor-plugin/
│   └── plugin.json             # Cursor marketplace manifest
├── .mcp.json                   # MCP server configuration (npx @sessionstellar/mcp)
├── skills/
│   ├── score-session/SKILL.md  # /score-session — score current conversation
│   └── score-file/SKILL.md     # /score-file — score a file from disk
├── rules/
│   └── orchestration-quality.mdc  # Coaching patterns for better orchestration
├── assets/
│   └── avatar.svg              # Plugin logo
├── .github/
│   ├── FUNDING.yml
│   ├── pull_request_template.md
│   └── ISSUE_TEMPLATE/
└── README.md
```

## How the Plugin Works

1. **MCP server**: `.mcp.json` tells Cursor to launch `npx -y @sessionstellar/mcp` as an MCP server. This provides `score_session` and `score_session_file` tools to the AI agent.
2. **Skills**: Slash commands (`/score-session`, `/score-file`) that users invoke. Each skill's SKILL.md contains instructions for the AI agent to follow.
3. **Rules**: `.mdc` files with patterns that coach users toward better orchestration quality.

## Adding a New Skill

1. Create `skills/<name>/SKILL.md`:
   ```yaml
   ---
   name: skill-name
   description: One-line description
   ---
   ```
2. Write the skill instructions in Markdown below the frontmatter
3. Update `README.md`
4. Test in Cursor

## Adding a New Rule

1. Create `rules/<name>.mdc` with `alwaysApply: false`
2. Document what patterns the rule coaches
3. Update `README.md`

## Key Design Decisions

- **No build step**: This is a pure-file plugin — no compilation, no bundling
- **Scoring engine is external**: All scoring logic lives in `@sessionstellar/mcp` (published npm package). This plugin is a thin wrapper.
- **Offline scoring**: The MCP server makes no outbound network requests. All scoring happens locally.
