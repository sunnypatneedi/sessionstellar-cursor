# Contributing to SessionStellar for Cursor

Thanks for wanting to improve AI orchestration quality scoring inside Cursor. Contributions of all kinds are welcome — new skills, rule improvements, MCP tool enhancements, and documentation.

## Repository Structure

```
.cursor-plugin/plugin.json   # Cursor marketplace manifest
.mcp.json                    # MCP server configuration
skills/                      # Cursor skills (slash commands)
  score-session/SKILL.md     # /score-session
  score-file/SKILL.md        # /score-file
rules/                       # Cursor rules (.mdc files)
  orchestration-quality.mdc  # Orchestration coaching patterns
assets/                      # Plugin assets
  avatar.svg                 # Plugin logo
```

## Types of Contributions

### 1. New skills (highest value)

Skills are slash commands that Cursor users invoke. Each skill lives in `skills/<name>/SKILL.md` with YAML frontmatter:

```yaml
---
name: skill-name
description: One-line description of what the skill does
---
```

To add a skill:
1. Create `skills/<name>/SKILL.md` with the frontmatter and workflow
2. Update `README.md` with the new skill
3. Open a PR

### 2. Rule improvements

Rules in `rules/` are `.mdc` files that coach better orchestration patterns. If you have patterns that consistently produce higher-quality AI sessions, add them:

1. Create or edit a rule in `rules/<name>.mdc`
2. Include `alwaysApply: false` unless the rule should always be active
3. Open a PR

### 3. MCP tool improvements

The MCP server is published separately as `@sessionstellar/mcp`. If you want to improve the scoring engine or add new MCP tools, contribute to the [main SessionStellar repo](https://github.com/sunnypatneedi/sessionstellar).

### 4. Bug reports

Open an issue using the **Bug Report** template. Include:
- Which skill or rule was involved
- What you expected vs. what happened
- Your Cursor version

### 5. Documentation

The README and skill descriptions are all fair game. Clear documentation is a feature.

## Pull Request Guidelines

- Keep PRs focused — one skill, rule, or fix per PR
- Test your skill/rule in Cursor before submitting
- Update the README if you're adding a new user-facing feature

## Security Vulnerabilities

Please don't open public issues for security vulnerabilities. See [SECURITY.md](./SECURITY.md) for the responsible disclosure process.

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](./LICENSE).
