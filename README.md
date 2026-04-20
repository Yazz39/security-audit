# 🔒 Security Audit Skill - Universal AI Agent

**Professional-grade security auditing for codebases - works with OpenCode, Claude Code, OpenClaw, Hermes, Cursor, Copilot, Cline, and all AI coding agents.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Compatibility](https://img.shields.io/badge/Compatibility-Universal-blue)](https://github.com/nabeelthethird/security-audit)
[![Agents](https://img.shields.io/badge/Agents-All%20AI%20Coders-green)](https://github.com/nabeelthethird/security-audit)
[![Category](https://img.shields.io/badge/Category-Security-green)](https://github.com/nabeelthethird/security-audit)

---

## 🎯 What This Does

This skill transforms **any AI coding agent** into a **security auditing powerhouse** that scans your codebase for:

- 🔑 **Hardcoded secrets** (API keys, passwords, tokens)
- 💉 **Injection vulnerabilities** (SQL, NoSQL, command, XSS)
- 🔓 **Authentication issues** (weak sessions, broken auth)
- 📦 **Vulnerable dependencies** (known CVEs)
- ⚙️ **Security misconfigurations** (CORS, headers, debug mode)
- 🛡️ **OWASP Top 10 compliance** gaps

---

## 🤖 Compatible AI Agents

| Agent | Status | Install Location |
|-------|--------|------------------|
| **OpenCode** | ✅ Full Support | `~/.config/opencode/skills/` |
| **Claude Code** | ✅ Full Support | `~/.claude/skills/` |
| **OpenClaw** | ✅ Full Support | `~/.claude/skills/` |
| **Hermes** | ✅ Full Support | `~/.hermes/skills/` or `~/.config/opencode/skills/` |
| **Cursor** | ✅ Full Support | `.cursor/rules/` or project skills |
| **GitHub Copilot** | ✅ Full Support | Project skills folder |
| **Cline** | ✅ Full Support | `~/.claude/skills/` |
| **Windsurf** | ✅ Full Support | Project skills folder |
| **Kilo Code** | ✅ Full Support | `~/.claude/skills/` |

---

## ⚡ Quick Install

### For All Agents (Global)

```bash
# Works for OpenCode, Claude Code, OpenClaw, Hermes, Cline, Kilo
git clone https://github.com/nabeelthethird/security-audit.git ~/.config/opencode/skills/security-audit

# Alternative location for Claude-based agents
git clone https://github.com/nabeelthethird/security-audit.git ~/.claude/skills/security-audit
```

### Project-Specific

```bash
# Works with any agent in this project
git clone https://github.com/nabeelthethird/security-audit.git .opencode/skills/security-audit
# OR
git clone https://github.com/nabeelthethird/security-audit.git .claude/skills/security-audit
```

---

## 🚀 Usage Examples

### With OpenCode
```
@build Run a security audit on this codebase
```

### With Claude Code / OpenClaw / Cline
```
Please run a comprehensive security audit using the security-audit skill
```

### With Cursor
```
@security-audit Audit this codebase for vulnerabilities
```

### With Hermes
```
Load security-audit skill and scan for hardcoded secrets
```

### Generic (Any Agent)
```
skill: security-audit
Perform comprehensive security audit with severity ratings
```

---

## 📊 Sample Findings

### 🔴 CRITICAL - Hardcoded Credentials

**Location**: `src/db/connection.py:15`

```python
# ❌ Vulnerable
DB_PASSWORD = "SuperSecret123!"

# ✅ Fixed
import os
DB_PASSWORD = os.environ.get("DB_PASSWORD")
```

### 🟠 HIGH - SQL Injection

**Location**: `api/users.js:42`

```javascript
// ❌ Vulnerable
const query = `SELECT * FROM users WHERE email = '${userInput}'`;

// ✅ Fixed
const query = 'SELECT * FROM users WHERE email = ?';
await db.execute(query, [userInput]);
```

### 🟡 MEDIUM - Missing Security Headers

**Location**: `server.js`

```javascript
// ❌ Vulnerable
app.listen(3000);

// ✅ Fixed
app.use(helmet()); // Adds security headers
app.use(rateLimit({ max: 100, windowMs: 15 * 60 * 1000 }));
app.listen(3000);
```

---

## 📋 What Gets Audited

| Category | Checks |
|----------|--------|
| **Secrets** | API keys, passwords, tokens, certificates |
| **Injection** | SQL, NoSQL, OS command, LDAP, XSS |
| **Auth** | Session management, JWT, OAuth, MFA |
| **Dependencies** | Known CVEs, outdated packages |
| **Config** | CORS, headers, debug mode, rate limiting |
| **Data** | Encryption, PII exposure, logging |
| **Infrastructure** | Docker, ports, TLS, containers |

---

## 🌐 Language Support

| Language | Files |
|----------|-------|
| JavaScript/TypeScript | `.js`, `.ts`, `.jsx`, `.tsx`, `package.json` |
| Python | `.py`, `requirements.txt`, `Pipfile` |
| Go | `.go`, `go.mod`, `go.sum` |
| Rust | `.rs`, `Cargo.toml` |
| Java/Kotlin | `.java`, `.kt`, `pom.xml`, `build.gradle` |
| Ruby | `.rb`, `Gemfile` |
| PHP | `.php`, `composer.json` |
| C# | `.cs`, `.csproj` |
| Shell | `.sh`, `.bash` |
| Config | `.env`, `.yaml`, `.yml`, `.toml`, `.json` |

---

## 🔧 Configuration

Create a config file in your skill directory:

```json
{
  "severity_threshold": "MEDIUM",
  "ignore_patterns": [
    "**/*.test.js",
    "**/vendor/**",
    "**/node_modules/**"
  ],
  "custom_rules": [],
  "report_format": "markdown"
}
```

---

## 🎯 Use Cases

### Pre-Deployment Check
```
Run full security audit before production deployment
```

### Secret Sweep
```
Scan entire repository for accidentally committed secrets
```

### Compliance Prep
```
Audit for SOC2 Type II compliance gaps
```

### Code Review
```
Security review this pull request before merging
```

### Dependency Check
```
Analyze all dependencies for known vulnerabilities
```

---

## 📊 Severity Levels

| Level | Response | Description |
|-------|----------|-------------|
| 🔴 CRITICAL | Immediate | Active exploitation possible |
| 🟠 HIGH | 24-48h | Significant vulnerability |
| 🟡 MEDIUM | Next sprint | Security weakness |
| 🟢 LOW | Backlog | Best practice recommendation |
| ℹ️ INFO | Optional | Informational |

---

## 🏗️ CI/CD Integration

### GitHub Actions

```yaml
name: Security Audit

on: [push, pull_request]

jobs:
  audit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Install Skill
        run: |
          git clone https://github.com/nabeelthethird/security-audit.git ~/.config/opencode/skills/security-audit
      
      - name: Run Audit
        run: |
          opencode --skill security-audit "Full audit" > security-report.md
      
      - name: Upload Report
        uses: actions/upload-artifact@v3
        with:
          name: security-report
          path: security-report.md
```

---

## 📚 References

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [CWE/SANS Top 25](https://cwe.mitre.org/top25/)
- [NIST Secure Software](https://www.nist.gov/itl/ssd)
- [GitHub Advisories](https://github.com/advisories)

---

## ⚠️ Limitations

- **Static analysis only** - cannot detect runtime issues
- **Not a penetration test** - combine with dynamic testing
- **No 100% guarantee** - always verify critical findings
- **No network access** - cannot test external endpoints

### Recommended Complement Tools

| Tool | Purpose |
|------|---------|
| Dependabot | Dependency updates |
| Snyk | Vulnerability scanning |
| Semgrep | Static analysis |
| Burp Suite | Dynamic testing |
| TruffleHog | Secret detection |

---

## 🤝 Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Areas for Contribution

- New vulnerability detection patterns
- Additional language support
- Custom rule templates
- CI/CD integrations
- Documentation improvements
- False positive reductions

---

## 📄 License

MIT License - See [LICENSE](LICENSE) file.

---

## 🆘 Support

- **Documentation**: See files in this repo
- **Issues**: https://github.com/nabeelthethird/security-audit/issues
- **Discord**: https://opencode.ai/discord

---

## ⚡ Quick Start Summary

```bash
# 1. Install (works for all agents)
git clone https://github.com/nabeelthethird/security-audit.git ~/.config/opencode/skills/security-audit

# 2. Use with any AI agent
# Ask your agent: "Run a security audit using security-audit skill"

# 3. Check results
# Agent will provide findings with severity ratings and fixes
```

---

<div align="center">

**Made with ❤️ for safer code across all AI agents**

[Install Now](#-quick-install) • [View Examples](EXAMPLES.md) • [Report Vulnerability](SECURITY.md)

</div>
