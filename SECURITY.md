# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| 0.x (latest) | Yes |

## Reporting a Vulnerability

This plugin runs an MCP server (`@sessionstellar/mcp`) via npx — we take security seriously.

**Please do not open a public GitHub issue for security vulnerabilities.**

Instead, report privately via:

- **GitHub private vulnerability reporting**: [github.com/sunnypatneedi/sessionstellar-cursor/security/advisories/new](https://github.com/sunnypatneedi/sessionstellar-cursor/security/advisories/new)

### What to include

- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (optional but appreciated)

### What to expect

- **Acknowledgement within 48 hours**
- **Triage within 5 business days**
- **Fix + coordinated disclosure** for confirmed vulnerabilities
- Credit in the changelog and advisory (unless you prefer to remain anonymous)

## Scope

In scope:

- MCP tool command injection or arbitrary code execution
- Data exfiltration through the scoring pipeline
- Skill or rule injection that alters scoring behavior maliciously
- Plugin manifest tampering that could affect Cursor users

Out of scope:

- Issues in the scoring engine itself (report to the [main repo](https://github.com/sunnypatneedi/sessionstellar))
- Social engineering attacks
- Attacks requiring physical access
