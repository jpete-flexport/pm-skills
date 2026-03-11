# Quick Start - PM Skills

Get up and running with Flexport PM skills in 5 minutes.

---

## Installation (One-Time Setup)

```bash
# 1. Clone the repo
git clone https://github.com/jpete-flexport/pm-skills.git
cd pm-skills

# 2. Install the skill
cp -r skills/pm-prd-scaffold ~/.claude/skills/

# 3. Restart Claude Code
# Exit and restart your Claude Code session

# 4. Verify
ls ~/.claude/skills/pm-prd-scaffold
# Should show: SKILL.md, README.md, resources/, examples/
```

---

## Usage

### Generate a PRD

```
/pm:prd-scaffold
```

**The skill will:**
1. Ask your name and title
2. Ask if you're in Discovery or PRD mode
3. Interview you (~10 questions)
4. Generate complete PRD

**Time:** 20-30 minutes

---

## What You Get

- ✅ Executive summary
- ✅ Success metrics (with suggestions)
- ✅ User personas
- ✅ User journey (current vs future)
- ✅ Requirements by epic
- ✅ Acceptance criteria (drafted)
- ✅ Visual stakeholder summary

**You refine:** ~20% (specific details, technical depth)

---

## Tips

**DO:**
- Have discovery notes ready
- Answer concisely (1-3 paragraphs)
- Let skill redirect edge cases
- Review and refine output

**DON'T:**
- Describe every edge case upfront
- Skip the metrics question
- Expect 100% complete (it's 70% done)

---

## Help

- **Full docs:** [skills/pm-prd-scaffold/README.md](skills/pm-prd-scaffold/README.md)
- **Examples:** [skills/pm-prd-scaffold/examples/](skills/pm-prd-scaffold/examples/)
- **Issues:** [GitHub Issues](https://github.com/jpete-flexport/pm-skills/issues)
- **Slack:** #product-management

---

## Updating

```bash
# Pull latest changes
cd ~/pm-skills
git pull

# Reinstall skill
cp -r skills/pm-prd-scaffold ~/.claude/skills/

# Restart Claude Code
```

---

## Next Steps

1. Try it on a real project
2. Share feedback (GitHub Issues or Slack)
3. Help improve it (see [CONTRIBUTING.md](CONTRIBUTING.md))

---

**Ready?** Run `/pm:prd-scaffold` and let it guide you!
