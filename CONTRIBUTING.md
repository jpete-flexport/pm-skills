# Contributing to Flexport PM Skills

Thank you for helping make PM work better at Flexport! This guide covers how to contribute to existing skills or create new ones.

---

## Ways to Contribute

### 1. Use Skills and Share Feedback
- Try skills on real projects
- Report what works well
- Report what's confusing
- Share in #product-management

### 2. Report Bugs
- Open a GitHub issue
- Include steps to reproduce
- Share expected vs actual behavior
- Tag with `bug` label

### 3. Suggest Features
- Open a GitHub issue
- Describe the problem it solves
- Propose a solution
- Tag with `enhancement` label

### 4. Improve Documentation
- Fix typos and clarify language
- Add examples and use cases
- Update FAQs
- Submit PR directly

### 5. Add Examples
- Share anonymized PRDs/artifacts
- Add to skill's `examples/` folder
- Include context (project type, outcome)

### 6. Build New Skills
- Follow skill template (see below)
- Solve a common PM workflow problem
- Submit PR for review

---

## Quick Start for Contributors

### 1. Fork and Clone

```bash
# Fork the repo on GitHub
# Then clone your fork
git clone https://github.com/YOUR-USERNAME/pm-skills.git
cd pm-skills
```

### 2. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### 3. Make Changes

Edit files, test locally, commit:

```bash
git add .
git commit -m "Add: description of your change"
git push origin feature/your-feature-name
```

### 4. Open Pull Request

- Go to GitHub
- Open PR from your branch to `main`
- Describe your changes
- Link related issues
- Request review

---

## Contribution Guidelines

### Code of Conduct

- Be respectful and professional
- Assume positive intent
- Provide constructive feedback
- Welcome newcomers
- Follow Flexport values

### Commit Messages

Format:
```
<Type>: <Subject>

<Body (optional)>

<Footer (optional)>
```

**Types:**
- `Add:` New feature or content
- `Fix:` Bug fix
- `Update:` Modify existing feature
- `Docs:` Documentation only
- `Refactor:` Code restructure
- `Test:` Add or update tests

**Examples:**
```
Add: pm-success-metrics skill for baseline analysis

Includes Socratic interview for metrics definition, data analysis
integration, and baseline/target recommendation engine.

Closes #15
```

```
Fix: pm-prd-scaffold edge case intervention timing

Intervention now triggers immediately when edge case mentioned,
preventing wasted time on details before redirect.

Fixes #23
```

### Pull Request Guidelines

**Title:** Clear, descriptive summary

**Description must include:**
- What changed and why
- Related issue numbers (#123)
- Testing performed
- Screenshots (if UI changes)
- Breaking changes (if any)

**Review process:**
- Small changes (docs, typos): 1 approval
- Features/fixes: 2 approvals including maintainer
- Breaking changes: Team discussion + maintainer approval

**Response time:**
- Typos/docs: 1-2 days
- Features: 3-5 days
- Major changes: 1-2 weeks

---

## Building a New Skill

### Skill Template

Every skill should have this structure:

```
skills/your-skill-name/
├── README.md              # Overview, installation, usage
├── SKILL.md               # Core skill logic
├── INSTALLATION.md        # Install guide
├── CONTRIBUTING.md        # Skill-specific contribution guide
├── resources/             # Patterns, references, templates
│   ├── patterns.md
│   └── quick_reference.md
└── examples/              # Sample outputs
    └── example_*.md
```

### SKILL.md Format

Must include YAML frontmatter:

```yaml
---
name: skill-name
description: Brief description (one sentence)
version: 1.0.0
---
```

Followed by:
- Core philosophy
- When to use
- Interview/interaction process
- Output structure
- Key behaviors
- Integration with other skills

### README.md Requirements

Must include:
- Overview and key features
- Installation instructions
- Quick start example
- Use cases
- Output samples
- FAQ
- Support information

### Documentation Standards

- Clear, concise language
- Written for PM audience (not engineers)
- Include examples and use cases
- Use markdown formatting
- Test all code examples
- Keep up to date with code

---

## Testing Your Changes

### For Skill Modifications

1. **Install locally:**
   ```bash
   rm -rf ~/.claude/skills/skill-name
   cp -r skills/skill-name ~/.claude/skills/
   # Restart Claude Code
   ```

2. **Test scenarios:**
   - New feature project
   - Enhancement project
   - Automation project
   - Edge cases
   - Minimal information
   - With artifacts
   - Without artifacts

3. **Verify output:**
   - All sections present
   - Formatting correct
   - No broken markdown
   - Tables render properly
   - Links work

### For New Skills

1. **Test with 3+ real projects**
2. **Get feedback from 2+ other PMs**
3. **Document all edge cases**
4. **Include example outputs**
5. **Verify installation on fresh machine**

---

## Review Process

### What Reviewers Check

**Functionality:**
- Does it work as described?
- Are edge cases handled?
- Is error handling adequate?

**Code Quality:**
- Clear and maintainable?
- Follows existing patterns?
- Well commented?

**Documentation:**
- Clear and complete?
- Includes examples?
- FAQ answers common questions?

**Testing:**
- Tested on multiple scenarios?
- Works on fresh install?
- No regressions?

### Approval Requirements

| Change Type | Approvals | Maintainer Required |
|-------------|-----------|---------------------|
| Typo/doc fix | 1 | No |
| Bug fix | 1 | Recommended |
| New feature | 2 | Yes |
| New skill | 2+ | Yes |
| Breaking change | Team discussion | Yes |

---

## Skill Design Principles

### 1. Speed + Structure + Focus
- Get users from problem to solution quickly
- Provide opinionated structure (not blank canvas)
- Keep users focused on what matters

### 2. Consistency
- Enforce formatting standards
- Use predictable patterns
- Maintain terminology

### 3. Outcome-Oriented
- Focus on user outcomes, not features
- Ask "what are you trying to achieve?"
- Generate artifacts that drive decisions

### 4. Manageable Scope
- Defer edge cases to later priorities
- Active intervention to keep focus
- Clear P0/P1/P2 separation

### 5. Stakeholder-Friendly
- Generate visual summaries
- Use plain language
- Layer detail for different audiences

---

## Questions?

### For Technical Issues
- Open GitHub issue
- Tag with appropriate label
- Include reproduction steps

### For Design Discussions
- Open GitHub discussion
- Share in #product-management
- Request design review meeting

### For General Questions
- Check FAQ in README
- Ask in #product-management
- Contact maintainers

---

## Recognition

### Contributors

Names added to:
- Main README.md
- Skill-specific READMEs
- CHANGELOG.md

### Special Recognition

- **5+ contributions:** Added to Contributors section with title
- **Major feature:** Announced in #product-management
- **New skill:** Co-author credit

---

## Maintainers

**Primary:**
- John Peterson (@jpete-flexport)

**Responsibilities:**
- Review and merge PRs
- Maintain code quality
- Update documentation
- Support contributors
- Plan roadmap

---

## Resources

### Internal
- PM Handbook (Flexport)
- PRD Template Library
- #product-management Slack

### External
- [Continuous Discovery Habits](https://www.producttalk.org/2021/08/continuous-discovery-habits/) (Teresa Torres)
- [Inspired](https://www.svpg.com/inspired-how-to-create-products-customers-love/) (Marty Cagan)
- [Jobs-to-be-Done](https://jobs-to-be-done.com/)

---

## License

Internal Flexport use only.

By contributing, you agree that your contributions will be licensed under the same terms.

---

**Ready to contribute?** Pick an issue tagged `good-first-issue` or open a new one!

**Questions?** Ask in #product-management or open a GitHub discussion.

**Thank you for making PM work better at Flexport!** 🚀
