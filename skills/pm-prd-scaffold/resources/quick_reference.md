# Quick Reference: pm:prd-scaffold

## When to Use

```
/pm:prd-scaffold
```

**Use when:**
- Starting a new PRD
- Have discovery insights ready
- Need structured document fast
- Want to avoid blank page paralysis

## What You Get

1. **Structured PRD** in your style with:
   - Executive summary
   - Success metrics (with suggestions)
   - User personas
   - Requirements organized by epic
   - Acceptance criteria (initial drafts)
   - Visual stakeholder summary

2. **Edge case management:**
   - Active intervention to keep you focused
   - P0/P1/P2 priority separation
   - Deferred items captured, not forgotten

3. **Consistency enforcement:**
   - Standard AC numbering (X.X.X)
   - Uniform table formatting
   - Consistent user story format

## The Interview Process

The skill will ask you ~10 questions, one at a time:

1. **Mode:** Discovery or PRD mode?
2. **Artifacts:** Any discovery docs to review?
3. **Problem:** What are we solving and for whom?
4. **Impact:** What if we don't solve this?
5. **Users:** Who's affected and what are their jobs to be done?
6. **Success:** What does success look like for users?
7. **Scope:** What's the minimum viable solution?
8. **Phasing:** Any planned phases/releases?
9. **Metrics:** How will we measure success?
10. **Technical:** Any constraints or dependencies?
11. **Journey:** Current vs future user experience?

**Then:** Reviews epic structure, generates requirements with you

## Tips for Best Results

✅ **DO:**
- Have discovery notes ready (or share links/docs)
- Think in terms of user outcomes, not features
- Answer questions concisely (1-2 paragraphs)
- Let the skill redirect when you dive into edge cases
- Review and refine the generated PRD

❌ **DON'T:**
- Try to answer everything in first question
- Describe every edge case during P0 discussion
- Worry about perfect wording (you'll refine after)
- Skip the metrics question (even if unsure)

## What Happens After

The skill will:
1. Generate complete PRD markdown
2. Ask where to save it
3. Suggest follow-up skills:
   - `/pm:success-metrics` - Deep metrics analysis
   - `/pm:prd-to-spec` - Convert to structured spec
   - `/pm:prd-to-prototype` - Generate Figma prompts
   - `/pm:visual-explainer` - Additional summaries

## Example Output Structure

```markdown
# Project Name - PRD

**Owner:** You | **Updated:** Today | **Status:** Draft

## 1. Executive Summary
[Problem, solution, impact, scope]

## 2. Success Metrics
[Table with baselines, targets, measurement]

## 3. Definitions
[Key terms]

## 4. User Personas
[Goals and challenges table]

## 5. User Journey: Current vs Future
[Journey comparison]

## 6. Requirements

### Epic 1: [Name]
| # | Requirement | User Story & AC | Priority |
|---|-------------|-----------------|----------|
| 1.1 | [Name] | As a [user]...<br>**AC 1.1.1** Given...When...Then... | P0 |

### Epic 2: [Name]
[Continue...]

## 7. Out of Scope / Deferred (P1/P2)
[Edge cases and future work]

## 8. Technical Considerations
[Dependencies, constraints, open questions]

## 9. Phasing
[MVP, MLP, North Star]

## Appendix A: Visual Summary
[1-page stakeholder overview]
```

## Time Savings

**Without skill:** 2-4 hours to structure PRD
**With skill:** 20-30 min interview → structured PRD

**What you still own:**
- Refining ACs
- Adding technical details
- Validating metrics with data
- Stakeholder review

## Your PM Skills Ecosystem

```
pm:prd-scaffold (START HERE)
    ↓
    ├→ pm:success-metrics (define baselines & targets)
    ├→ pm:prd-review (check quality & consistency)
    ├→ pm:visual-explainer (create more summaries)
    └→ pm:prd-to-spec (convert to structured format)
         ↓
         └→ pm:prd-to-prototype (generate Figma/v0 prompts)
```

## Common Questions

**Q: What if I don't have all the answers during the interview?**
A: That's fine! The skill will mark items as TBD and create placeholders. You can fill in later.

**Q: Can I stop the interview and come back?**
A: The interview is conversational - you can pause, ask questions, or restart anytime.

**Q: What if I disagree with the suggested epic structure?**
A: Tell the skill! It will ask for your preferred structure and adapt.

**Q: How detailed should my answers be?**
A: 1-3 paragraphs per question is ideal. The skill will probe for more if needed.

**Q: Can I use this for technical specs or just product PRDs?**
A: Designed for product PRDs. Use `/pm:prd-to-spec` to convert to technical specs after.

**Q: What if my project doesn't fit the template?**
A: The skill uses "hybrid structure" - core sections are consistent, but it adapts contextual sections based on your project type.

## Need Help?

- Review `prd_patterns.md` for detailed writing guidelines
- Check your existing PRDs in `/Users/jpeterson/Downloads/` for reference
- Ask the skill questions during the interview - it's designed to help!

## Feedback & Iteration

After using the skill, consider:
- What questions were unclear?
- What sections needed most refinement?
- What would make the output more useful?

Share feedback to improve future versions!
