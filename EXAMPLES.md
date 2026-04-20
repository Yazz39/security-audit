# 📚 Examples - Security Audit Skill

## Basic Usage Examples

### 1. Full Codebase Audit

```
@build Run a comprehensive security audit on the entire codebase
```

**Expected Output:**
- Summary of all findings by severity
- Detailed report with locations and fixes
- Priority-ordered remediation list

---

### 2. Secret Detection

```
@build Scan for any hardcoded secrets, API keys, or credentials
```

**What it finds:**
- AWS access keys
- Database passwords
- JWT secrets
- API tokens (Stripe, Twilio, etc.)
- Private keys

---

### 3. Directory-Specific Audit

```
@build Security audit the src/auth/ directory for vulnerabilities
```

**Use case:** Focus on sensitive areas like authentication, payments, user data

---

### 4. Pre-Deployment Check

```
@build Pre-deployment security audit - check for any critical or high severity issues before production
```

**Focus:** Critical and high severity only, fast turnaround

---

### 5. OWASP Compliance

```
@build Audit this codebase against OWASP Top 10 2021 requirements
```

**Output:** Compliance report with gaps and remediation

---

### 6. Dependency Security

```
@build Analyze all dependencies for known security vulnerabilities and CVEs
```

**Checks:**
- package.json, requirements.txt, Cargo.toml, etc.
- Known CVEs
- Outdated packages
- Malicious packages

---

### 7. File-Specific Review

```
@build Security review this file: src/api/payments.js
```

**Use case:** Quick review of specific files before commit

---

### 8. Compliance Report

```
@build Generate a SOC2 Type II compliance gap analysis
```

**Output:**
- Control requirements
- Current gaps
- Remediation steps
- Evidence needed

---

### 9. Pull Request Review

```
@build Security review the changes in this pull request
```

**Focus:** New vulnerabilities introduced in recent changes

---

### 10. Incident Response

```
@build We suspect a security breach - audit for backdoors, webhooks, or data exfiltration
```

**Focus:**
- Suspicious external calls
- Unknown webhooks
- Data exfiltration patterns
- Backdoor code

---

## Language-Specific Examples

### JavaScript/Node.js

```
@build Audit this Express.js app for security vulnerabilities
```

**Common checks:**
- Helmet middleware
- Input validation
- CSRF protection
- Session security

---

### Python/Django

```
@build Security audit this Django project
```

**Common checks:**
- DEBUG = False
- ALLOWED_HOSTS
- CSRF tokens
- SQL injection in raw queries

---

### Python/Flask

```
@build Audit this Flask application for security issues
```

**Common checks:**
- Secret key exposure
- Input validation
- SQL injection
- Debug mode

---

### Go

```
@build Security review this Go web service
```

**Common checks:**
- SQL injection
- Command injection
- Error handling
- TLS configuration

---

### Rust

```
@build Audit this Rust project for memory safety and security
```

**Common checks:**
- Unsafe blocks
- Dependency vulnerabilities
- Input validation

---

## Configuration Examples

### Custom Severity Threshold

```json
{
  "severity_threshold": "HIGH"
}
```

Only report HIGH and CRITICAL issues.

---

### Ignore Test Files

```json
{
  "ignore_patterns": [
    "**/*.test.js",
    "**/*.spec.ts",
    "**/__tests__/**",
    "**/vendor/**"
  ]
}
```

---

### Custom Rules

```markdown
## Organization Rules

1. All database queries must use parameterized statements
2. No console.log in production code
3. All API responses must have Content-Type headers
4. Rate limiting required on all public endpoints
```

---

## Report Format Examples

### Executive Summary

```
Generate an executive summary for non-technical stakeholders
```

**Output:** High-level overview, business impact, priority actions

---

### Technical Report

```
Generate a detailed technical report for the development team
```

**Output:** Code snippets, exact locations, fix implementations

---

### Compliance Checklist

```
Export findings as a compliance checklist for auditors
```

**Output:** Control-by-control status, evidence references

---

## CI/CD Examples

### Fail on Critical

```bash
if grep -q "🔴 CRITICAL" security-report.md; then
  echo "Critical issues found - failing build"
  exit 1
fi
```

---

### Slack Notification

```yaml
- name: Notify Slack on Critical Issues
  if: failure()
  run: |
    curl -X POST $SLACK_WEBHOOK \
      -H 'Content-Type: application/json' \
      -d '{"text":"🚨 Critical security issues found in '"$GITHUB_REPOSITORY"'"}'
```

---

## Advanced Use Cases

### Monorepo Audit

```
@build Security audit all packages in this monorepo, report by package
```

---

### API Security

```
@build Audit all API endpoints for authentication, authorization, and rate limiting
```

---

### Database Security

```
@build Review all database queries for injection vulnerabilities and proper indexing
```

---

### Authentication Review

```
@build Comprehensive security review of authentication and session management
```

---

### Third-Party Code

```
@build Security audit this third-party library before integration
```

---

## Tips for Best Results

1. **Be specific** - "Audit src/auth/" vs "Audit everything"
2. **Set context** - "Pre-deployment" vs "Routine check"
3. **Ask for formats** - "Executive summary" vs "Technical details"
4. **Follow up** - "Now show me how to fix the critical issues"
5. **Iterate** - Run audit → Fix → Re-audit

---

## Common False Positives

These may be flagged but are often intentional:

- Test fixtures with fake credentials
- Example code in documentation
- Development-only configurations
- Intentional honeypot code

**Mitigation:** Use `ignore_patterns` in config

---

## Next Steps

After running an audit:

1. **Prioritize** - Fix CRITICAL first
2. **Verify** - Confirm findings are actual issues
3. **Remediate** - Apply suggested fixes
4. **Re-audit** - Run again to confirm fixes
5. **Document** - Add to security runbook

---

## Need Help?

- Documentation: [README.md](../README.md)
- Skill Details: [SKILL.md](../SKILL.md)
- Setup Guide: [SETUP.md](../SETUP.md)
