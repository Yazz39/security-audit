# 🔒 Security Audit Skill for OpenCode

**Professional-grade security auditing for codebases - detects vulnerabilities, secrets, OWASP issues, and provides actionable fixes.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Compatibility](https://img.shields.io/badge/Compatibility-OpenCode-blue)](https://opencode.ai)
[![Category](https://img.shields.io/badge/Category-Security-green)](https://opencode.ai/docs/skills)
[![Stars](https://img.shields.io/github/stars/YOUR_USERNAME/security-audit?style=social)](https://github.com/YOUR_USERNAME/security-audit)

---

## 🎯 What This Does

This skill transforms OpenCode into a **security auditing powerhouse** that scans your codebase for:

- 🔑 **Hardcoded secrets** (API keys, passwords, tokens)
- 💉 **Injection vulnerabilities** (SQL, NoSQL, command, XSS)
- 🔓 **Authentication issues** (weak sessions, broken auth)
- 📦 **Vulnerable dependencies** (known CVEs)
- ⚙️ **Security misconfigurations** (CORS, headers, debug mode)
- 🛡️ **OWASP Top 10 compliance** gaps

---

## ⚡ Quick Install

### Option 1: Global (All Projects)

```bash
git clone https://github.com/YOUR_USERNAME/security-audit.git ~/.config/opencode/skills/security-audit
```

### Option 2: Project-Specific

```bash
git clone https://github.com/YOUR_USERNAME/security-audit.git .opencode/skills/security-audit
```

### Option 3: Manual

1. Download this repository
2. Place in `~/.config/opencode/skills/security-audit/` (global)
3. Or `.opencode/skills/security-audit/` (project)

---

## 🚀 Usage

### Basic Audit

```
@build Run a security audit on this codebase
```

### Specific Scan

```
@build Check src/auth/ for vulnerabilities
```

### Secret Detection

```
@build Scan for hardcoded API keys and secrets
```

### Full Report

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

Create `.opencode/skills/security-audit/config.json`:

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
      
      - name: Install OpenCode
        run: npm i -g opencode-ai
      
      - name: Run Security Audit
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

Contributions welcome! Please:

1. Fork the repo
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

### Areas for Contribution

- New vulnerability detection patterns
- Additional language support
- Custom rule templates
- CI/CD integrations
- Documentation improvements
- False positive reductions

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file.

---

## 🆘 Support

- **Documentation**: https://opencode.ai/docs/skills
- **Discord**: https://opencode.ai/discord
- **Issues**: https://github.com/YOUR_USERNAME/security-audit/issues

---

## 🙏 Acknowledgments

- Built for [OpenCode](https://opencode.ai) - the open source AI coding agent
- Follows [OWASP](https://owasp.org) guidelines
- Inspired by security best practices from NIST, CWE, SANS

---

## 📈 Roadmap

- [ ] Custom rule builder UI
- [ ] Auto-fix suggestions with PR generation
- [ ] Compliance report templates (SOC2, ISO 27001, HIPAA)
- [ ] Integration with security scanners (Semgrep, Bandit)
- [ ] Multi-language report translation
- [ ] Historical trend analysis
- [ ] Team dashboard integration

---

<div align="center">

**Made with ❤️ for safer code**

[Report Vulnerability](https://github.com/YOUR_USERNAME/security-audit/security/advisories) • [Request Feature](https://github.com/YOUR_USERNAME/security-audit/issues)

</div>
