# Flexport PM Skills

Claude Code skills and tools to help Flexport Product Managers work more efficiently and systematically.

## Overview

This repository contains reusable Claude Code skills that help PMs with common workflows like PRD writing, discovery, metrics analysis, and stakeholder communication. Each skill enforces best practices while saving time.

## Available Skills

### ✅ pm-prd-scaffold (v1.0.0)

Generate structured PRDs from discovery insights using Socratic interviewing.

**What it does:**
- Interviews you about your project (~10 questions)
- Generates complete PRD with exec summary, metrics, personas, requirements, ACs
- Active edge case management (keeps you focused on P0)
- Visual stakeholder summaries
- 20-30 minutes vs 2-4 hours manually

**Install:**
```bash
cp -r skills/pm-prd-scaffold ~/.claude/skills/
# Restart Claude Code
/pm:prd-scaffold
```

**Documentation:** [skills/pm-prd-scaffold/README.md](skills/pm-prd-scaffold/README.md)

**Example output:** [skills/pm-prd-scaffold/examples/](skills/pm-prd-scaffold/examples/)

---

### 📋 Coming Soon

**pm-success-metrics** - Define measurable success criteria with data analysis

**pm-prd-to-spec** - Convert PRD to structured spec for AI consumption

**pm-prd-to-prototype** - Generate Figma/v0.dev prompts from PRD

**pm-visual-explainer** - Create stakeholder summaries on demand

**pm-prd-review** - Check PRD quality and consistency

---

## Quick Start

**New here?** See [QUICKSTART.md](QUICKSTART.md) for 5-minute setup guide.

### Prerequisites

- Claude Code installed and configured
- Access to `~/.claude/skills/` directory

### Installation

**Install all skills:**
```bash
git clone https://github.com/flexport/pm-skills.git
cd pm-skills
cp -r skills/* ~/.claude/skills/
```

**Install single skill:**
```bash
git clone https://github.com/flexport/pm-skills.git
cd pm-skills
cp -r skills/pm-prd-scaffold ~/.claude/skills/
```

**Verify installation:**
```bash
ls ~/.claude/skills/pm-prd-scaffold
# Restart Claude Code
```

### Usage

Invoke any skill with:
```
/skill-name
```

Example:
```
/pm:prd-scaffold
```

---

## Repository Structure

```
pm-skills/
├── README.md                      # This file
├── CONTRIBUTING.md                # How to contribute
├── skills/
│   ├── pm-prd-scaffold/          # PRD generation skill
│   │   ├── README.md
│   │   ├── SKILL.md
│   │   ├── INSTALLATION.md
│   │   ├── resources/
│   │   └── examples/
│   ├── pm-success-metrics/        # Coming soon
│   └── pm-prd-to-spec/           # Coming soon
└── docs/
    └── framework.md               # PM Skills framework overview
```

---

## For Users

### Getting Help

- **Installation issues:** See skill's `INSTALLATION.md`
- **Usage questions:** See skill's `README.md`
- **Examples:** Check skill's `examples/` folder
- **Bugs/features:** Open a GitHub issue
- **General questions:** Ask in #product-management Slack

### Best Practices

1. **Read the skill README first** - Understand what it does and when to use it
2. **Try with test data** - Run through once with a sample scenario
3. **Review and refine** - Skills generate 70% complete drafts, you refine the rest
4. **Share feedback** - Help us improve by reporting issues and suggestions

---

## For Contributors

### Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- How to report bugs
- How to suggest features
- Development setup
- Pull request process

### Common Contributions

- **Bug fixes** - Found an issue? Submit a PR
- **Documentation improvements** - Clarify or expand docs
- **New examples** - Share anonymized PRDs you've created
- **New skills** - Build skills for other PM workflows
- **Pattern updates** - Add new PRD patterns or conventions

### Building a New Skill

Want to create a new skill? Follow this template:

```
skills/your-skill-name/
├── README.md              # Overview, installation, usage
├── SKILL.md               # Core skill logic (YAML frontmatter + instructions)
├── INSTALLATION.md        # Step-by-step install guide
├── resources/             # Supporting files (patterns, references)
└── examples/              # Sample outputs
```

See `skills/pm-prd-scaffold/` as a reference implementation.

---

## Success Metrics

**Adoption:**
- Number of PMs using skills
- PRDs/artifacts generated per week
- Active users (used in last 30 days)

**Efficiency:**
- Time saved per artifact
- Reduction in revision cycles
- Faster project kickoffs

**Quality:**
- Consistency (% following format)
- Completeness (% including all sections)
- Stakeholder satisfaction

**Current Stats:**
- **pm-prd-scaffold:** Used by X PMs, Y PRDs generated, avg 3.5 hours saved per PRD

---

## Roadmap

### Q2 2026
- ✅ Launch pm-prd-scaffold
- 🔄 Build pm-success-metrics
- 🔄 Build pm-prd-to-spec

### Q3 2026
- 📋 Build pm-prd-to-prototype
- 📋 Build pm-visual-explainer
- 📋 Build pm-prd-review

### Q4 2026
- 📋 Discovery skills (pm-discovery-plan)
- 📋 Technical design review skills
- 📋 Stakeholder alignment skills

---

## FAQ

### Q: Can I customize skills for my team?
**A:** Yes! Fork the skill, edit SKILL.md and resources/ files to match your conventions.

### Q: Can I use these outside of Flexport?
**A:** Skills are Flexport-internal. For external use, you'd need to generalize the terminology and patterns.

### Q: What if a skill doesn't fit my project?
**A:** Skills use "hybrid structure" and adapt to project types. If something's not working, open an issue!

### Q: How do I update a skill?
**A:** `git pull` this repo, then copy the updated skill to `~/.claude/skills/` and restart Claude Code.

### Q: Can I contribute a new skill?
**A:** Absolutely! Follow the template above and submit a PR. We'll review and help you refine it.

---

## Support

- **GitHub Issues:** [Report bugs or request features](https://github.com/flexport/pm-skills/issues)
- **Slack:** #product-management
- **Email:** Product team

---

## Credits

**Created by:** John Peterson, Principal Technical Product Manager

**Contributors:**
- [Your name here - contribute and get listed!]

**Inspired by:**
- Flexport PM best practices
- Jobs-to-be-Done framework
- Continuous Discovery Habits (Teresa Torres)
- Shape Up methodology (Basecamp)

---

## License

Internal use for Flexport employees only.

For questions about external use or licensing, contact the Product team.

---

**Get started:** Pick a skill from the list above and follow its installation instructions!

**Questions?** Open an issue or ask in #product-management Slack.

**Want to contribute?** See [CONTRIBUTING.md](CONTRIBUTING.md)!
