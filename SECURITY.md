# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

## Reporting a Vulnerability

**⚠️ IMPORTANT: Do not create public issues for security vulnerabilities**

If you discover a security vulnerability within this skill, please:

1. **DO NOT** create a public GitHub issue
2. Email directly to: security@yourdomain.com (replace with your email)
3. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if any)

## Response Timeline

- **Acknowledgment**: Within 48 hours
- **Initial Assessment**: Within 5 business days
- **Fix Timeline**: Depends on severity
  - Critical: 24-48 hours
  - High: 1 week
  - Medium: 2 weeks
  - Low: Next release

## What to Expect

1. You'll receive an acknowledgment within 48 hours
2. We'll assess the vulnerability and determine severity
3. We'll work on a fix and coordinate with you
4. You'll be credited in the security advisory (unless you prefer anonymity)
5. A public security advisory will be published after the fix is released

## Security Best Practices for Users

This skill performs **static analysis only**. For comprehensive security:

### Combine With:
- [ ] Dynamic Application Security Testing (DAST)
- [ ] Regular penetration testing
- [ ] Dependency scanning (Dependabot, Snyk)
- [ ] Runtime application self-protection (RASP)
- [ ] Security code review by humans

### Recommended Tools:
| Tool | Purpose |
|------|---------|
| Dependabot | Automated dependency updates |
| Snyk | Vulnerability scanning |
| Semgrep | Static analysis |
| Burp Suite | Dynamic testing |
| TruffleHog | Secret detection |
| OWASP ZAP | Security testing |

## Security Updates

Stay updated:
- Watch this repository for security patches
- Check the [Security Advisories](../../security/advisories) page
- Subscribe to security notifications

## Disclaimer

This skill:
- ✅ Performs static code analysis
- ✅ Identifies common vulnerability patterns
- ✅ Provides remediation guidance
- ❌ Cannot guarantee 100% vulnerability detection
- ❌ Cannot replace professional security audits
- ❌ Cannot detect runtime vulnerabilities
- ❌ Cannot access external systems or networks

**Always combine with other security measures and professional review for critical applications.**
