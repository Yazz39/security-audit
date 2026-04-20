# 🚀 Setup Guide

## Installation

### Global Installation (Recommended)

Installs the skill for all OpenCode projects:

```bash
# Clone directly to global skills directory
git clone https://github.com/YOUR_USERNAME/security-audit.git ~/.config/opencode/skills/security-audit
```

### Project-Specific Installation

Installs only for a specific project:

```bash
# Clone to project's skills directory
git clone https://github.com/YOUR_USERNAME/security-audit.git .opencode/skills/security-audit
```

### Manual Installation

1. Download this repository as ZIP
2. Extract to `~/.config/opencode/skills/security-audit/` (global)
3. Or `.opencode/skills/security-audit/` (project)

## Verification

Verify the skill is loaded:

```
/skills
```

You should see `security-audit` in the list.

## Configuration

### Basic Config

Create `.opencode/skills/security-audit/config.json`:

```json
{
  "severity_threshold": "MEDIUM",
  "ignore_patterns": [
    "**/*.test.js",
    "**/vendor/**",
    "**/node_modules/**"
  ],
  "report_format": "markdown"
}
```

### Custom Rules

Create `.opencode/skills/security-audit/rules.md` for organization-specific rules:

```markdown
## Custom Security Rules

1. All API endpoints must have rate limiting
2. PII data must be encrypted at rest
3. Admin routes require MFA
4. No eval() or Function() constructors
5. All external URLs must be validated
```

## Permissions

Ensure skills are enabled in `opencode.json`:

```json
{
  "permission": {
    "skill": {
      "security-audit": "allow"
    }
  }
}
```

## First Audit

Run your first security audit:

```
@build Run a security audit on this codebase
```

## Next Steps

- See [README.md](README.md) for full documentation
- Check [SKILL.md](SKILL.md) for detailed capabilities
- Review examples in [examples/](examples/) (coming soon)
