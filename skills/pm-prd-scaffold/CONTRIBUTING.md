# Contributing to PM PRD Scaffold

Thank you for your interest in improving this skill! This guide will help you contribute effectively.

---

## Ways to Contribute

### 1. Share Feedback

**After using the skill:**
- What worked well?
- What was confusing?
- What would make it more useful?
- What questions were unclear?

**Share via:**
- #product-management Slack channel
- GitHub issues
- Direct message to John Peterson

### 2. Report Bugs

**Found an issue?**

Create a GitHub issue with:
- **Title:** Brief description
- **Description:** What happened vs what you expected
- **Steps to reproduce:**
  1. Invoke `/pm:prd-scaffold`
  2. Answer question X with Y
  3. Observe incorrect behavior Z
- **Environment:** Claude Code version, OS
- **Priority:** High / Medium / Low

### 3. Suggest Enhancements

**Ideas for improvement?**

Create a GitHub issue with:
- **Title:** Feature request: [your idea]
- **Description:** What problem does this solve?
- **Use case:** When would you use this?
- **Proposed solution:** How might it work?
- **Alternatives considered:** Other approaches?

### 4. Add Examples

**Help others learn:**

Add sample PRDs to `examples/` directory:
- Real (anonymized) PRDs you've created
- Different project types (new feature, automation, etc.)
- Good and bad examples (with explanations)

### 5. Improve Documentation

**Make it clearer:**

- Fix typos
- Add clarifications
- Include screenshots
- Add use case examples
- Update FAQs

### 6. Enhance the Skill

**Improve the code:**

- Add new interview questions
- Improve epic structure suggestions
- Add success metric categories
- Enhance AC generation logic
- Add new PRD section templates

---

## Contribution Process

### For Small Changes (Typos, Doc Fixes)

1. Make changes directly
2. Submit PR with clear description
3. Tag reviewer (@johnpeterson or PM team)

### For Medium Changes (New Features, Logic Changes)

1. **Open an issue first** to discuss approach
2. Get feedback from maintainers
3. Implement changes
4. Submit PR with:
   - Clear description
   - Examples of output changes
   - Test cases

### For Major Changes (Restructure, New Paradigms)

1. **Propose via RFC** (Request for Comments)
2. Share in #product-management
3. Gather feedback from PM team
4. Create design doc if needed
5. Implement after approval
6. Submit PR with comprehensive testing

---

## Development Setup

### 1. Fork and Clone

```bash
git clone [REPO_URL]
cd pm-skills/pm-prd-scaffold
```

### 2. Create Development Copy

```bash
# Backup your current installation
mv ~/.claude/skills/pm-prd-scaffold ~/.claude/skills/pm-prd-scaffold.backup

# Symlink to development version
ln -s $(pwd) ~/.claude/skills/pm-prd-scaffold
```

### 3. Make Changes

Edit files:
- `SKILL.md` - Main skill logic
- `resources/prd_patterns.md` - Writing patterns
- `resources/quick_reference.md` - Quick tips
- `README.md` - Documentation

### 4. Test Locally

```bash
# Restart Claude Code
# Invoke skill
/pm:prd-scaffold

# Test with various scenarios
```

### 5. Submit PR

```bash
git checkout -b feature/your-feature-name
git add .
git commit -m "Add: your feature description"
git push origin feature/your-feature-name
```

Then create PR on GitHub.

---

## Coding Guidelines

### SKILL.md Structure

**Maintain these sections:**

1. **Frontmatter** (YAML metadata)
   ```yaml
   ---
   name: pm:prd-scaffold
   description: Brief description
   version: X.Y.Z
   ---
   ```

2. **Core Philosophy** (don't change without discussion)

3. **Interview Process** (order matters!)
   - Mode Detection
   - Artifact Review
   - Core Questions
   - Epic Structure
   - Requirements Generation

4. **PRD Output Structure** (template)

5. **Key Behaviors** (consistency rules)

### Writing Interview Questions

**Good questions:**
- Open-ended
- Clear and specific
- One concept per question
- Builds on previous answers
- Includes context/examples

**Bad questions:**
- Yes/no only
- Too vague
- Multiple concepts mixed
- Assumes too much context

**Example:**

✅ Good:
```
"What problem are we solving, and for whom?
(Tell me about the user pain points and who's experiencing them.)"
```

❌ Bad:
```
"What's the problem?"
```

### PRD Template Updates

**When modifying the output template:**

1. **Maintain core sections:**
   - Executive Summary
   - Success Metrics
   - Definitions
   - User Personas
   - Requirements
   - Visual Summary

2. **Keep formatting consistent:**
   - Use markdown tables
   - Number sections
   - Use consistent heading levels

3. **Test with multiple project types:**
   - New feature
   - Enhancement
   - Automation
   - Infrastructure

### Pattern Documentation

**When adding to `prd_patterns.md`:**

1. **Show examples:**
   - Include before/after
   - Show good and bad patterns
   - Explain why

2. **Be specific:**
   - Don't say "write good requirements"
   - Do say "write requirements as user stories: As a [user], I want [goal], so that [outcome]"

3. **Link to real PRDs:**
   - Reference anonymized examples
   - Show how pattern applies in practice

---

## Testing Your Changes

### Manual Testing Checklist

Test the skill with:

- [ ] New feature project
- [ ] Enhancement project
- [ ] Automation project
- [ ] Infrastructure/platform project
- [ ] Discovery mode
- [ ] PRD mode
- [ ] With artifacts
- [ ] Without artifacts
- [ ] Edge case heavy scenario (test intervention)
- [ ] Minimal info scenario (test placeholders)

### Output Validation

Check generated PRD for:

- [ ] All required sections present
- [ ] Consistent formatting
- [ ] AC numbering correct (X.X.X)
- [ ] Priority labels present (P0/P1/P2)
- [ ] Success metrics included
- [ ] Visual summary generated
- [ ] No broken markdown
- [ ] Tables render correctly

### Quality Checks

- [ ] No Flexport-internal secrets or sensitive data
- [ ] Examples are anonymized
- [ ] Links work (if any)
- [ ] Terminology is consistent
- [ ] Grammar and spelling correct

---

## Review Process

### PR Review Checklist

Reviewers will check:

1. **Does it solve the stated problem?**
2. **Is it consistent with existing patterns?**
3. **Does it maintain backward compatibility?**
4. **Is documentation updated?**
5. **Are examples included?**
6. **Does it pass manual testing?**

### Response Times

- **Small changes:** 1-2 days
- **Medium changes:** 3-5 days
- **Major changes:** 1-2 weeks (includes RFC discussion)

### Approval Required

- **Typos/docs:** 1 approver
- **Feature additions:** 2 approvers (including maintainer)
- **Breaking changes:** Team discussion + maintainer approval

---

## Style Guidelines

### Documentation

- Use clear, concise language
- Write for PM audience (not engineers)
- Include examples and use cases
- Use markdown formatting consistently
- Break up long text with headers and lists

### Code (SKILL.md)

- Use clear variable names
- Comment complex logic
- Keep functions focused
- Follow existing patterns
- Don't over-engineer

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
Add: Success metric suggestions for standardization projects

Adds new metric category for standardization initiatives including
compliance rate, variance reduction, and consistency scores.

Closes #42
```

```
Fix: Edge case intervention timing

Intervention now triggers before user spends time on edge case details
rather than after, improving focus on P0 requirements.
```

---

## Community Guidelines

### Be Respectful

- Assume positive intent
- Provide constructive feedback
- Acknowledge good work
- Welcome newcomers

### Be Collaborative

- Share knowledge
- Help others contribute
- Pair on complex changes
- Document decisions

### Be Professional

- Keep discussions focused
- Avoid off-topic tangents
- Respect time and effort
- Follow Flexport code of conduct

---

## Recognition

### Contributors

Your name will be added to:
- README.md Contributors section
- CHANGELOG.md for significant contributions
- Special recognition in #product-management for major improvements

### Types of Recognition

- **Documentation Hero:** 5+ doc improvements
- **Feature Champion:** Major feature addition
- **Bug Hunter:** 10+ bug reports/fixes
- **Example Provider:** 3+ quality example PRDs
- **Community Builder:** Helps 5+ people adopt the skill

---

## Versioning

We use Semantic Versioning (SemVer):

**Format:** MAJOR.MINOR.PATCH

- **MAJOR:** Breaking changes (requires user action)
- **MINOR:** New features (backward compatible)
- **PATCH:** Bug fixes (backward compatible)

**Examples:**
- `1.0.0 → 1.0.1`: Bug fix in AC generation
- `1.0.1 → 1.1.0`: Add new epic structure pattern
- `1.1.0 → 2.0.0`: Change interview question order (breaks existing usage)

---

## Release Process

### For Maintainers

1. **Gather changes** from merged PRs
2. **Update version** in SKILL.md frontmatter
3. **Update CHANGELOG.md** with changes
4. **Test thoroughly** with multiple scenarios
5. **Create release tag** on GitHub
6. **Announce in #product-management**
7. **Update installation instructions** if needed

---

## Questions?

### Contribution Questions

- **General:** #product-management Slack
- **Technical:** GitHub discussions
- **Urgent:** DM John Peterson

### Getting Started

Not sure where to start? Try:

1. **Use the skill** and share feedback
2. **Fix a typo** in documentation
3. **Add an example PRD** from your work
4. **Answer questions** from other users in Slack

Every contribution helps! 🎉

---

**Thank you for contributing to making PM work better at Flexport!**
