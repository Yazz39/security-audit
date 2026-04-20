# Contributing to Security Audit Skill

Thank you for your interest in contributing! This document provides guidelines for contributing.

## 🎯 Where You Can Help

### High Priority Areas

1. **Vulnerability Detection Patterns**
   - New injection patterns
   - Framework-specific vulnerabilities
   - Language-specific security issues

2. **Language Support**
   - Additional programming languages
   - Framework-specific rules
   - Build system analysis

3. **Compliance Frameworks**
   - SOC2 controls
   - ISO 27001 requirements
   - HIPAA security rules
   - GDPR compliance checks

4. **Integration**
   - CI/CD pipelines
   - Security tool integrations
   - Report format exporters

5. **Documentation**
   - Usage examples
   - False positive reporting
   - Translation to other languages

## 🚀 Getting Started

### 1. Fork and Clone

```bash
git clone https://github.com/YOUR_USERNAME/security-audit.git
cd security-audit
```

### 2. Create Branch

```bash
git checkout -b feature/your-feature-name
```

### 3. Make Changes

Follow the existing structure and coding style.

### 4. Test Your Changes

Test with real codebases:

```
@build Test the new vulnerability detection pattern
```

### 5. Submit PR

```bash
git commit -m "Add: description of your change"
git push origin feature/your-feature-name
```

Then open a Pull Request on GitHub.

## 📝 Contribution Guidelines

### Code Quality

- Follow existing patterns in `SKILL.md`
- Use clear, descriptive language
- Include examples for new features
- Document limitations

### Security Considerations

- **Never** include real vulnerabilities in examples
- Use placeholder values (e.g., `YOUR_API_KEY`)
- Mark dangerous patterns clearly
- Test in isolated environments

### Documentation

- Update README.md for new features
- Add examples to EXAMPLES.md
- Update configuration options in SETUP.md
- Include severity classification

### Testing Checklist

Before submitting:

- [ ] Tested with at least 2 real codebases
- [ ] No false positives in test cases
- [ ] Documentation updated
- [ ] Examples provided
- [ ] Severity levels appropriate
- [ ] References included (OWASP, CWE, etc.)

## 📋 PR Template

When opening a PR, please include:

```markdown
## What this does
[Brief description]

## Why this is needed
[Problem statement]

## Testing done
- [ ] Tested on real codebase
- [ ] No false positives
- [ ] Examples provided

## Documentation
- [ ] README updated
- [ ] Examples added
- [ ] Configuration documented

## References
[Links to OWASP, CVE, or other references]
```

## 🐛 Reporting Issues

### Bug Reports

Include:
- OpenCode version
- Skill version
- Code snippet (sanitized)
- Expected vs actual behavior
- Severity of the issue

### Feature Requests

Include:
- Use case description
- Example scenarios
- Priority/urgency
- Similar implementations (if any)

### False Positives

Report false positives to help improve detection:

```markdown
**Pattern**: What was flagged
**Code**: Sanitized code snippet
**Why it's safe**: Explanation
**Suggested fix**: How to avoid flagging
```

## 💡 Ideas for Contributions

### Beginner Friendly

- [ ] Add more code examples
- [ ] Improve documentation clarity
- [ ] Add translations
- [ ] Create video tutorials
- [ ] Write blog posts

### Intermediate

- [ ] New vulnerability patterns
- [ ] Framework-specific rules
- [ ] CI/CD integrations
- [ ] Report templates
- [ ] Custom rule examples

### Advanced

- [ ] New language support
- [ ] Compliance frameworks
- [ ] Security scanner integrations
- [ ] Auto-fix suggestions
- [ ] Machine learning improvements

## 🏆 Recognition

Contributors will be:

- Listed in README.md contributors section
- Credited in release notes
- Mentioned in security advisories (if applicable)
- Invited to join the core team (for significant contributions)

## 📞 Questions?

- **General**: Open an issue
- **Quick questions**: Discord https://opencode.ai/discord
- **Security concerns**: See SECURITY.md

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for helping make code more secure! 🙏
