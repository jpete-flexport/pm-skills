# PRD Patterns & Best Practices

This document captures patterns from the user's existing PRDs to ensure consistency.

## Writing Style

### Executive Summary Structure
- **Length:** 2-3 paragraphs
- **Paragraph 1:** Current state problem - "Today, [users] need to [painful process]..."
- **Paragraph 2:** Proposed solution - "In [year/quarter], [company] will launch [solution]..."
- **Paragraph 3:** Scope and approach - "We will limit initial launch scope to..."

### Language Patterns
- Use active voice: "clients can view" not "clients will be able to view"
- Be specific: "2-4 weeks" not "soon"
- Use present tense for features: "The system generates" not "The system will generate"

## Section Patterns

### Definitions Section
**Purpose:** Align stakeholders on terminology BEFORE diving into requirements

**Format:**
```markdown
## 2. Definitions

Below is a summary of definitions used throughout this document...

* **Term 1** is the [definition]. Additional context...
* **Term 2** can be [definition]. They are [additional context].
```

**Best practices:**
- Define domain-specific terms only (not common terms)
- Include context beyond just dictionary definition
- Link related terms together
- Note variations in terminology

### User Personas Table

**Required columns:**
| # | Persona | Description | Goals | Challenges |

**Best practices:**
- Number personas (1, 2, 3...)
- Keep description to 1-2 sentences
- Goals should be actionable outcomes
- Challenges should be current pain points this PRD addresses
- Limit to 3-5 key personas (don't over-segment)

### Requirements Structure

**Epic-based organization:**
```markdown
| Epic X: [Epic Name]
| [Brief description of epic scope]
|---|-------------|-----------|----------|
| # | Requirement | User Story & Acceptance Criteria | Priority |
| X.1 | [Name] | **User Story:**<br>As a [user]...<br><br>**AC X.1.1**<br>Given...<br>When...<br>Then... | P0 |
```

**Numbering convention:**
- Epic level: 1, 2, 3...
- Requirement level: 1.1, 1.2, 1.3...
- AC level: 1.1.1, 1.1.2, 1.1.3...

**Priority levels:**
- **P0:** Must have for MVP, happy path
- **P0.5:** MVP but can slip to next iteration if needed
- **P1:** Important for MLP, edge cases
- **P2:** Nice to have, future consideration

### Acceptance Criteria Patterns

**Format 1: Given/When/Then (preferred for behavior)**
```
**AC X.X.X**
Given [precondition/context]
When [user action or trigger]
Then [expected system behavior/outcome]
```

**Format 2: Imperative (for technical specs)**
```
**AC X.X.X**
The system shall [requirement]
And [additional requirement]
```

**Format 3: Bulleted (for configuration/data)**
```
**AC X.X.X**
The user will see:
- [Data point 1]
- [Data point 2]
And the user can [action]
```

**Best practices:**
- Be specific about data (don't say "relevant info", list actual fields)
- Include edge cases in same AC: "If [condition], then [exception behavior]"
- Call out UI specifics: "drop down", "multiple-choice", "in table format"
- Specify data formats: "date", "number with 2 decimal points", "USD currency"

## Common Requirement Patterns

### Navigation & Discovery
```markdown
| X.1 | [Feature] Navigation | As a [user], I need to easily access [feature], so that I can [goal].

**AC X.1.1**
Given a [user type] is logged in
When the user navigates to [location]
Then the user sees [entry point] to [feature]

**AC X.1.2**
Given [condition exists]
When [user accesses feature]
Then the user will view [specific data/content]
```

### Data Display Requirements
```markdown
| X.2 | [Feature]: Table View | As a [user], I need to view [data] in a table, so that I can [quickly scan/compare/find].

**AC X.2.1**
Given [data exists]
When the user views [page/section]
Then the user sees a table with columns:
- [Column 1]: [format/data type]
- [Column 2]: [format/data type]
- [Column 3]: [format/data type]

**AC X.2.2**
Given the user is viewing the table
When [condition]
Then the rows are sorted by [field] in [ascending/descending] order
And [secondary sort logic]
```

### Filtering & Search
```markdown
| X.3 | [Feature]: Filters | As a [user], I need to filter [data], so that I can find [specific items].

**AC X.3.1**
Given [data exists]
When the user accesses filters
Then the user can filter by:
- [Attribute 1]: [type of filter - dropdown, multi-select, etc.]
- [Attribute 2]: [type of filter]
And all filters are [single/multiple]-choice

**AC X.3.2**
Given the user has applied filters
When the user wants to clear filters
Then the user can clear all filters with one click
```

### Actions (Single Item)
```markdown
| X.4 | [Feature]: Actions | As a [user], I need to [take action] on [item], so that I can [outcome].

**AC X.4.1**
Given a [item] exists
When the user selects the item
Then the user can:
- [Action 1]
- [Action 2]
- [Action 3]

**AC X.4.2**
Given the user initiates [destructive action]
When the user confirms
Then [system behavior]
And [side effects/related changes]
```

### Batch Actions
```markdown
| X.5 | [Feature]: Batch Actions | As a [user], I need to [take action] on multiple [items], so that I don't need to [repeat action].

**AC X.5.1**
Given multiple [items] exist
When the user accesses the page
Then the user can select:
- One item
- Multiple items
- All items (after applying filters)

**AC X.5.2**
Given the user has selected [N] items
When the user initiates [action]
Then [action] is applied to all selected items
And [confirmation/result feedback]
```

### Detail View
```markdown
| X.6 | [Feature]: Detail View | As a [user], I need to view details of [item], so that I can [understand/configure/validate].

**AC X.6.1**
Given a user selects an item
When the detail view loads
Then the user sees:
- [Section 1] (view only/editable)
  - [Field 1]: [format]
  - [Field 2]: [format]
- [Section 2]
  - [Field 3]: [format]
```

### Notifications & Updates
```markdown
| X.7 | [Feature]: Updates | As a [user], I need to know when [event occurs], so that I can [take action/stay informed].

**AC X.7.1** (logic for triggering notification)
Given [condition is met]
When [trigger event occurs]
Then [notification is generated/flag is shown]

**AC X.7.2** (notification content & delivery)
Given a notification is generated
Then the notification contains: "[message text]"
And the notification is delivered via:
- In-app notification
- Email (if user preferences allow)
And selecting the notification navigates to [destination]
```

## Success Metrics Patterns

### Metric Table Format
```markdown
| Metric | Baseline | Target | Measurement Method | Owner |
|--------|----------|--------|-------------------|-------|
| [Metric name] | [Current value or TBD] | [Specific target] | [How/where measured] | [Team/person] |
```

### Metric Categories

**For New Features:**
- Adoption Rate: % of target users who use the feature
- Engagement: Actions per user, frequency of use
- Task Completion Rate: % of users who complete core workflow
- User Satisfaction: NPS, feedback scores

**For Automation:**
- Time Saved: Hours/minutes per task or per week
- Error Reduction: % decrease in errors or support tickets
- Cost Savings: $ saved on manual work
- Throughput: Increase in tasks completed per period

**For Simplification:**
- Task Completion Time: Before vs after time to complete
- Support Tickets: % reduction in related tickets
- User Confusion: Decrease in "how do I..." questions
- Adoption of new flow: % using simplified vs old flow

**For Standardization:**
- Compliance Rate: % following standard process
- Variance Reduction: Standard deviation of outcomes
- Consistency Score: % matching defined standard
- Audit Findings: Reduction in exceptions

### Metric Definition Best Practices
- Always include baseline (current state) even if TBD
- Set specific, time-bound targets: "Increase from 45% to 70% by Q3"
- Define measurement method: "Tracked via Mixpanel event: [event_name]"
- Distinguish launch metrics (did we ship?) from success metrics (did it work?)
- Include leading indicators (usage) and lagging indicators (business impact)

## Phasing Patterns

### Phase Table Format
```markdown
| # | Phase | Launch Qtr | Short Description | Key Features |
|---|-------|------------|-------------------|--------------|
| 1.0 | [Phase Name] | Q# 'YY | [2-3 sentence description]<br>Why we need it: [Justification] | [Bullet list] |
| 2.0 | [Phase Name] | Q# 'YY | [2-3 sentence description]<br>Why we need it: [Justification] | [Bullet list] |
```

### Phasing Terminology
- **MVP (Minimum Viable Product):** Smallest thing that delivers value
- **MLP (Minimum Lovable Product):** Feature-complete enough for users to prefer it
- **North Star:** Long-term vision, ultimate goal state

## Technical Considerations Section

**Include when relevant:**
```markdown
## Technical Considerations

**Dependencies:**
- [System/API 1]: [What we need from it]
- [Integration 2]: [What we need from it]

**Constraints:**
- [Technical limitation and impact]
- [Platform constraint and workaround]

**Open Questions:**
- [ ] [Technical question requiring research]
- [ ] [Design question requiring decision]

**Non-Functional Requirements:**
- Performance: [SLA/response time requirement]
- Security: [Data sensitivity, access control needs]
- Scalability: [Expected load, growth considerations]
```

## Scope Management

### In Scope / Out of Scope
**Always include to set boundaries:**

```markdown
## Scope

**In Scope (P0 for MVP):**
- [Feature/capability 1]
- [Feature/capability 2]

**Deferred (P1/P2):**
- [Feature delayed to future phase]
- [Edge case to address later]

**Explicitly Out of Scope:**
- [Thing people might expect but we're not doing]
- [Related problem we're not solving yet]
```

## Common Pitfalls to Avoid

❌ **Don't:**
- Use vague terms: "improve", "optimize", "enhance" (without specifics)
- Write features as requirements: "Add a button" (describe the user outcome)
- Mix P0 and P1 in same epic without clear labels
- Write ACs that are too high-level: "System works correctly"
- Forget to define acronyms and domain terms

✅ **Do:**
- Be specific: "Reduce quote creation time from 15 min to 5 min"
- Write outcome-oriented requirements: "User can instantly book without quote approval"
- Clearly separate P0 (MVP) from P1 (MLP) from P2 (Future)
- Write testable ACs: "User sees error message 'Invalid date range' when end date < start date"
- Define terms upfront in Definitions section

## User Journey Best Practices

### Current vs Future State Table
```markdown
| Step | Current State | Future State | Improvement |
|------|--------------|--------------|-------------|
| 1. [Action] | [Manual process, time X] | [Automated process, time Y] | [Quantified improvement] |
| 2. [Action] | [Painful step with errors] | [Validated step with guidance] | [Qualitative improvement] |
```

### Journey Visualization (ASCII Art)
Keep it simple and focused on the flow, not perfection:

```
CURRENT STATE:
User → Manual Step 1 → Manual Step 2 → Pain Point → Manual Step 3 → Goal
       ⏱️ 5 min        ⏱️ 10 min       ❌ Errors    ⏱️ 5 min

FUTURE STATE:
User → Automated Step → Streamlined Step → Goal
       ⏱️ 1 min        ⏱️ 2 min          ✅ Validated
```

## Stakeholder Summary Best Practices

**1-Page Visual Summary should include:**
1. **The Problem** (1-2 sentences, pain point focused)
2. **The Solution** (1-2 sentences, outcome focused)
3. **Who It Helps** (Persona + key benefit each)
4. **Expected Impact** (Top 3 metrics with targets)
5. **User Journey Visualization** (Current vs Future)
6. **Timeline** (Phases with dates)

**Keep it:**
- Skimmable (executives read in 2 minutes)
- Visual (use tables, diagrams, emojis sparingly for clarity)
- Outcome-focused (business value, not features)
- Non-technical (anyone can understand)

## Language & Tone

- **Confident but not prescriptive:** "This approach will..." not "This might..."
- **Action-oriented:** Use strong verbs (create, automate, eliminate, enable)
- **User-centered:** Focus on user outcomes, not system features
- **Data-informed:** Reference research, metrics, user feedback
- **Clear and concise:** Favor shorter sentences, bullet lists over paragraphs

## Cross-References

When referencing other documents:
```markdown
See [Document Name](link) for additional details.
References: [System Name](link), [Data Source](link)
```

When referencing sections within PRD:
```markdown
(see section 2.3 for details)
(details in AC 1.4.2)
```

## Version Control

Include at top of document:
```markdown
**Document Owner:** [Name] | **Last Updated:** [Date] | **Status:** [Draft/Under Review/Approved]
```

For documents with version history:
```markdown
## Document Versions
1) Current Version (This document)
2) V2 ([found here](link))
3) V1 ([found here](link))
```

## Final Checklist

Before considering a PRD complete, verify:

✅ **Structure:**
- [ ] Executive summary clearly states problem, solution, impact
- [ ] Success metrics defined with baselines and targets
- [ ] All domain terms defined
- [ ] Personas include goals and challenges
- [ ] Requirements organized into logical epics

✅ **Content:**
- [ ] Every requirement has user story
- [ ] Every user story has 2+ acceptance criteria
- [ ] ACs are specific and testable
- [ ] Priorities clearly marked (P0/P1/P2)
- [ ] Edge cases deferred to P1/P2

✅ **Clarity:**
- [ ] Non-technical stakeholders can understand exec summary
- [ ] Engineers have enough detail to estimate and design
- [ ] Designers have enough context for UX decisions
- [ ] QA can write test cases from ACs

✅ **Completeness:**
- [ ] User journey shows current vs future state
- [ ] Technical dependencies identified
- [ ] Open questions captured
- [ ] Phasing defined if applicable
- [ ] Visual summary created for stakeholders
