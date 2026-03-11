# Sharing PM PRD Scaffold with Flexport Team

This guide helps you share the pm-prd-scaffold skill with other Flexport Product Managers.

---

## What's Ready to Share

This package contains everything needed for other PMs to install and use the skill:

```
pm-prd-scaffold-package/
├── README.md              # Main documentation
├── INSTALLATION.md        # Step-by-step install guide
├── CONTRIBUTING.md        # How to improve the skill
├── SHARING_GUIDE.md       # This file
├── SKILL.md               # The actual skill logic
├── resources/
│   ├── prd_patterns.md    # PRD writing best practices
│   └── quick_reference.md # Quick tips
└── examples/
    └── example_prd_dcrs_rates.md  # Sample PRD output
```

---

## Step 1: Choose Distribution Method

### Option A: GitHub Repository (Recommended)

**Best for:** Official Flexport PM team distribution

**Steps:**

1. **Check if PM tools repo exists:**
   ```bash
   # Search Flexport GitHub for existing repos
   # Common names: pm-tools, product-tools, claude-skills
   ```

2. **If repo exists:**
   ```bash
   cd ~/flexport/[repo-name]
   git pull
   mkdir -p skills
   cp -r ~/Documents/Projects/pm-prd-scaffold-package skills/pm-prd-scaffold
   git add skills/pm-prd-scaffold
   git commit -m "Add: PM PRD Scaffold skill"
   git push
   ```

3. **If no repo exists, create one:**
   - Create new repo: `flexport/pm-skills` or `flexport/product-tools`
   - Clone locally
   - Copy package to repo
   - Push to GitHub
   - Share repo link in #product-management

4. **Announce in #product-management:**
   ```
   📢 New PM Skill Available: PRD Scaffold

   Generate well-structured PRDs in 20-30 minutes with Socratic interviewing!

   Features:
   - Active edge case management
   - Success metrics suggestions
   - Draft acceptance criteria
   - Visual stakeholder summaries

   Install: [link to repo README]
   Questions: DM me or ask in thread!
   ```

### Option B: Internal Wiki/Confluence

**Best for:** Documentation-first sharing

1. Create Confluence page: "PM Tools & Skills"
2. Upload package as zip file
3. Document installation steps
4. Link from PM Handbook
5. Share in #product-management

### Option C: Direct Sharing

**Best for:** Small team pilot / beta testing

1. **Create shareable zip:**
   ```bash
   cd ~/Documents/Projects
   zip -r pm-prd-scaffold.zip pm-prd-scaffold-package/
   ```

2. **Share via:**
   - Google Drive (Flexport shared folder)
   - Slack DM or #product-management
   - Email

3. **Include quick instructions:**
   ```
   Hi! I've created a Claude skill to help with PRD writing.

   To install:
   1. Download and unzip
   2. Copy to ~/.claude/skills/pm-prd-scaffold
   3. Restart Claude Code
   4. Run /pm:prd-scaffold

   Full instructions in INSTALLATION.md
   Let me know if you hit any issues!
   ```

---

## Step 2: Prepare for Sharing

### Before Sharing Checklist

- [ ] Tested skill on your own machine
- [ ] Reviewed all documentation for clarity
- [ ] Removed any sensitive/personal info from examples
- [ ] Updated README with correct repo URLs (if using GitHub)
- [ ] Prepared announcement message
- [ ] Ready to support early users

### Update README Links

If using GitHub, update these placeholders in README.md:

```markdown
# Before
git clone [GITHUB_URL]/pm-skills

# After
git clone https://github.com/flexport/pm-skills
```

Search and replace `[GITHUB_URL]` with actual URL.

---

## Step 3: Support Your Users

### Expected Questions

**Q: "I get 'skill not found' error"**
A: Point them to INSTALLATION.md troubleshooting section. Common fixes:
- Check file is at `~/.claude/skills/pm-prd-scaffold/SKILL.md`
- Restart Claude Code
- Verify filename is `SKILL.md` (all caps)

**Q: "How do I customize it for my team?"**
A: Point them to CONTRIBUTING.md. They can edit:
- `SKILL.md` for interview questions
- `resources/prd_patterns.md` for team conventions

**Q: "Can I use this for non-Flexport PRDs?"**
A: Yes! They'll want to update terminology in `resources/prd_patterns.md` to remove Flexport-specific terms.

**Q: "It's asking too many questions!"**
A: That's by design (10 questions). Remind them:
- Takes 20-30 min total (vs 2-4 hours manually)
- Can answer concisely (1-2 paragraphs each)
- Generates 70% complete PRD

**Q: "How do I stop it from redirecting my edge cases?"**
A: Explain that's the core value - keeps them focused on P0. Edge cases are captured in P1/P2 sections.

### Gather Feedback

Create a feedback mechanism:
- [ ] GitHub Issues (for bug reports, feature requests)
- [ ] Slack thread in #product-management
- [ ] Bi-weekly "office hours" in first month
- [ ] Survey after 2-3 uses per person

Track:
- Installation issues (improve INSTALLATION.md)
- Confusing questions (refine SKILL.md)
- Missing features (add to roadmap)
- Time savings (validate success metrics)

---

## Step 4: Iterate Based on Feedback

### First Month Plan

**Week 1: Pilot**
- Share with 2-3 trusted PMs
- Gather detailed feedback
- Fix critical issues
- Update documentation

**Week 2: Broader rollout**
- Share in #product-management
- Monitor Slack for questions
- Create FAQ based on questions
- Release v1.0.1 with fixes

**Week 3-4: Adoption**
- Offer pair sessions (use skill together)
- Collect example PRDs people generate
- Add best examples to examples/ folder
- Plan v1.1 features

### Ongoing Maintenance

**Monthly:**
- Review GitHub issues / feedback
- Update patterns based on new PRD conventions
- Add requested features
- Release minor version updates

**Quarterly:**
- Major feature additions
- Review success metrics
- Plan next skills in framework
- Update training materials

---

## Step 5: Build Community

### PM Skills Community

Create momentum around PM tooling:

1. **#pm-skills Slack channel** (or use #product-management)
   - Share tips and tricks
   - Post example PRDs
   - Announce updates
   - Help each other

2. **Bi-weekly sync** (optional)
   - Demo new features
   - Share learnings
   - Pair on PRDs
   - Plan next skills

3. **Contribution encouragement**
   - Recognize contributors in README
   - Make it easy to contribute (CONTRIBUTING.md)
   - Merge PRs quickly
   - Celebrate improvements

### Expand the Framework

Once pm:prd-scaffold is adopted:

1. **Build next skill:** `pm:success-metrics`
2. **Share learnings:** What worked? What didn't?
3. **Document patterns:** Best practices for skill creation
4. **Enable others:** Help PMs create their own skills

---

## Templates for Sharing

### Slack Announcement Template

```
🚀 New PM Tool: PRD Scaffold Skill

Tired of staring at a blank page for hours? This Claude Code skill generates structured PRDs in 20-30 minutes through Socratic interviewing.

✅ What you get:
• Complete PRD with exec summary, metrics, personas, requirements
• Active edge case management (keeps you focused on P0)
• Success metrics suggestions based on project type
• Drafted acceptance criteria (60-70% complete)
• Visual stakeholder summary

📦 Install:
1. [Link to installation instructions]
2. Run /pm:prd-scaffold
3. Answer ~10 questions
4. Get your PRD!

📊 Early results:
• Time to PRD: 2-4 hrs → 20-30 min
• Consistent formatting: 100%
• Success metrics included: 100% (vs ~50% before)

🙋 Questions? Reply in thread or DM me!

Example: [Link to example PRD in examples/ folder]
```

### Email Template

```
Subject: New PM Skill: Generate PRDs in 20-30 Minutes

Hi PM Team,

I've created a Claude Code skill that helps us write PRDs faster and more consistently. It uses Socratic interviewing to extract requirements and generates a complete PRD with:

- Executive summary
- Success metrics (with suggestions)
- User personas and journey
- Requirements with drafted ACs
- Visual summary for stakeholders

Installation:
[Link to repo or instructions]

Time Investment:
20-30 minutes for interview → Complete PRD draft

I've tested it on [X] PRDs so far and it's saved me ~2-3 hours per PRD while improving consistency and making sure I always include success metrics upfront.

Happy to do a quick demo if you're interested! Or just try it out and let me know what you think.

Example PRD: [Link]
Installation Guide: [Link]

[Your Name]
```

### Confluence Page Template

```markdown
# PM PRD Scaffold Skill

## Overview
Claude Code skill for generating structured PRDs through Socratic interviewing.

## Quick Start
1. Install: [Installation Guide]
2. Run: `/pm:prd-scaffold`
3. Generate PRD in 20-30 minutes

## Features
- Active edge case management
- Success metrics suggestions
- Draft acceptance criteria
- Visual summaries
- Consistent formatting

## Documentation
- [README](link)
- [Installation Guide](link)
- [Quick Reference](link)
- [Example PRDs](link)

## Support
- Questions: #product-management
- Issues: [GitHub Issues]
- Contact: [Your Name]

## Metrics
- Time savings: 2-4hrs → 20-30min
- Adoption: X PMs using
- PRDs generated: Y total
```

---

## Measuring Success

Track these to show impact:

### Adoption Metrics
- [ ] Number of PMs who installed
- [ ] Number of PRDs generated
- [ ] Usage frequency (PRDs/week)
- [ ] Active users (used in last 30 days)

### Quality Metrics
- [ ] Time to first PRD draft (before vs after)
- [ ] PRD consistency score (% following format)
- [ ] Success metrics inclusion (% of PRDs)
- [ ] Revision cycles (rework reduced?)

### Satisfaction Metrics
- [ ] User satisfaction (1-5 rating)
- [ ] Would recommend (yes/no)
- [ ] Most valuable feature (survey)
- [ ] Top pain point solved (survey)

### Business Impact
- [ ] PM time saved (hours/week)
- [ ] Stakeholder feedback on PRD clarity
- [ ] Faster project kickoffs
- [ ] Better requirement quality

---

## Troubleshooting Rollout

### Low Adoption

**Possible causes:**
- Installation too complex → Simplify instructions, offer pair installs
- Not seeing value → Share success stories, show time savings
- Uncomfortable with AI → Demo together, address concerns
- Too busy to try → Offer to do first PRD together

**Solutions:**
- Host "Install Party" - help everyone install together
- Create video walkthrough
- Share before/after examples
- Start with early adopters who champion it

### Installation Issues

**Common problems:**
- Wrong directory location
- Filename case sensitivity
- Missing resources folder
- Claude Code not updated

**Solutions:**
- Add verification script
- Create install shell script
- Better error messages in INSTALLATION.md
- Pre-flight check list

### Feature Requests

**Handle strategically:**
- Quick wins (docs, small tweaks): Do immediately
- Common requests: Add to roadmap, prioritize
- Edge cases: Defer to P2, explain why
- Out of scope: Politely decline, suggest alternatives

---

## Next Steps

1. **Choose distribution method** (GitHub, Confluence, or Direct)
2. **Prepare package** (update links, test one more time)
3. **Announce to team** (use templates above)
4. **Support early users** (first week is critical)
5. **Gather feedback** (iterate quickly)
6. **Build momentum** (share wins, celebrate adoption)
7. **Plan next skill** (pm:success-metrics, pm:prd-to-spec)

---

## Questions?

Contact: John Peterson
Slack: #product-management
GitHub: [Repo issues]

**Let's make PM work better at Flexport!** 🚀
