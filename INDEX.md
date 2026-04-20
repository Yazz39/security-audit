# 🔒 Security Audit Skill

> **Professional-grade security auditing for OpenCode agents**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Compatibility](https://img.shields.io/badge/Compatibility-OpenCode-blue)](https://opencode.ai)
[![Category](https://img.shields.io/badge/Category-Security-green)](https://opencode.ai/docs/skills)

## 🎯 What This Does

Transforms OpenCode into a **security auditing powerhouse** that scans your codebase for:

- 🔑 Hardcoded secrets (API keys, passwords, tokens)
- 💉 Injection vulnerabilities (SQL, NoSQL, command, XSS)
- 🔓 Authentication issues
- 📦 Vulnerable dependencies (known CVEs)
- ⚙️ Security misconfigurations
- 🛡️ OWASP Top 10 compliance gaps

## ⚡ Quick Start

```bash
# Install globally
git clone https://github.com/YOUR_USERNAME/security-audit.git ~/.config/opencode/skills/security-audit

# Use in OpenCode
@build Run a security audit on this codebase
```

## 📊 Sample Findings

| Severity | Issue | Location |
|----------|-------|----------|
| 🔴 CRITICAL | Hardcoded database credentials | `src/db.py:15` |
| 🟠 HIGH | SQL injection vulnerability | `api/users.js:42` |
| 🟡 MEDIUM | Missing security headers | `server.js` |
| 🟢 LOW | Console logging in production | `utils/logger.js` |

## 📋 Features

- **Secret Detection** - API keys, passwords, tokens, certificates
- **OWASP Top 10** - Full coverage of 2021 Top 10
- **Dependency Review** - Known CVEs, outdated packages
- **Multi-Language** - JS/TS, Python, Go, Rust, Java, PHP, C#, Ruby
- **CI/CD Ready** - GitHub Actions workflow included
- **Compliance** - SOC2, ISO 27001, HIPAA gap analysis

## 🚀 Installation

See [SETUP.md](SETUP.md) for detailed installation instructions.

## 📖 Documentation

| Document | Description |
|----------|-------------|
| [README.md](README.md) | Full documentation and usage guide |
| [SKILL.md](SKILL.md) | Technical skill specification |
| [SETUP.md](SETUP.md) | Installation and configuration |
| [EXAMPLES.md](EXAMPLES.md) | Usage examples and patterns |
| [SECURITY.md](SECURITY.md) | Security policy and vulnerability reporting |

## 🛠️ CI/CD Integration

```yaml
- name: Security Audit
  run: |
    opencode --skill security-audit "Full audit" > security-report.md
```

See [`.github/workflows/`](.github/workflows/) for complete workflow.

## 📈 Roadmap

- [ ] Custom rule builder UI
- [ ] Auto-fix PR generation
- [ ] Compliance report templates
- [ ] Integration with security scanners
- [ ] Historical trend analysis

## 🤝 Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

MIT License - See [LICENSE](LICENSE) file.

## 🆘 Support

- **Docs**: https://opencode.ai/docs/skills
- **Discord**: https://opencode.ai/discord
- **Issues**: https://github.com/YOUR_USERNAME/security-audit/issues

---

<div align="center">

**Made with ❤️ for safer code**

[Install Now](#-quick-start) • [View Examples](EXAMPLES.md) • [Report Vulnerability](SECURITY.md)

</div>
