# /digest-paper

Translates academic papers into practical one-pagers. The goal isn't to summarize—it's to answer "What does this mean for ME and what I'm building?" If no project context exists, ask what the user is working on first.

## Usage

Add as a slash command in Claude Code: `~/.claude/commands/digest-paper.md`

Run with: `/digest-paper [paper URL or title]`, or just ask it questions about research topics.

---

## What This Skill Does

1. **Reads the paper** through the lens of what applies to your current projects
2. **Translates terminology** into terms you already use
3. **Calls out what doesn't apply** so you don't waste time on irrelevant sections
4. **Extracts actionable items** - what should you actually do?
5. **Provides quotes** that anchor the advice to the source

## Flexible Input

This skill handles various request styles:

- "Digest this paper: [link]" → Single paper digest
- "Pick 3 papers about agent memory and digest them" → Search, select, digest multiple
- "What research exists on procedural memory for agents?" → Survey + recommendations
- "Find papers relevant to what we've been discussing" → Context-aware search + digest

## Output Destination

**Default: Print to terminal.** Do NOT save to file unless user explicitly asks.

Only save to file when user says things like:
- "save this"
- "create a doc"
- "write this to a file"
- "I want to reference this later"

## Output Format

Print directly to terminal using this structure (or save to file if requested):

```markdown
# [Paper Title]: Paper Digest

*Translated for: [specific context, e.g., "Someone building X who wants to know Y"]*

**Paper:** [Link]
**Authors:** [Names and affiliations]
**Published:** [Date]
**Conference/Journal:** [If applicable]

---

## Authors & Context

Who wrote this and why should you trust (or question) them?

- **[Author Name]** - [Background, affiliation, notable prior work]
- ...

**Funding/Affiliation:** [Who paid for this? Industry lab, academia, startup?]

**Potential Biases:** [Are they selling something? Pushing their own framework? Academic incentives?]

---

## Industry Reception

*What are people saying about this paper?*

[Do a quick web search for reactions, critiques, implementations. Include:]
- Notable praise or criticism
- Who's implementing it
- Any rebuttals or follow-up work
- Hot takes from practitioners

---

## The One-Sentence Summary

> "[Capture the essence in plain language]"

---

## What Problem They're Solving

[2-3 sentences in plain language]

---

## Key Concepts Mapped to Your System

| Their Term | Your Equivalent | What It Means |
|------------|-----------------|---------------|
| ... | ... | ... |

---

## The [N] Questions/Things They Address

### 1. [Question]
**Finding:** [What they found]
**For you:** [What this means for your specific situation]

> *"[Relevant quote from paper]"* (Section X)

[Repeat for each key point]

---

## What You Should Actually Do

1. [Concrete action item]
2. [Concrete action item]
...

---

## What Doesn't Apply to You

- [Thing that's not relevant and why]
- [Thing that's not relevant and why]

---

## The Quote That Matters Most

> *"[The single most important quote]"*

Translation: [Plain language explanation]

---

## Read More

- Full paper: [link]
- [Any relevant sections to focus on]
```

## Workflow

1. Ask user for the paper URL or title
2. **Gather context** - Check for project context (CLAUDE.md, recent conversation, etc.). If none exists, ask:
   - "What are you working on that made you interested in this paper?"
   - "Any specific questions you're hoping it answers?"
   - "What terminology do you use for similar concepts?"
3. Fetch and read the paper
4. **For Industry Reception section:** Run a web search for reactions/critiques. Cross-validate claims across multiple sources.
5. Map paper concepts to user's existing terminology
6. Generate digest in the format above
7. **Ensure all URLs are linked** - Any paper URLs, GitHub repos, author pages, or related resources should be markdown links: `[text](url)`
8. Save to appropriate location if requested
9. **Invite follow-up** - End with: "Feel free to ask follow-up questions about specific sections or how to apply any of these findings."

## Key Principle

The goal is NOT to summarize the paper. The goal is to answer: **"What does this mean for ME and what I'm building?"**

## Show, Don't Just Tell: Concrete Examples

For key concepts, include **concrete examples** of what the user would actually see or experience when using a system built on these principles. Feel this out based on the paper and the user's current context.

Examples can take various forms depending on what fits:

**Conversation snippets** - What would a prompt/response look like?
```
User: "Find procedures related to deploying"
System: "Found 3 highly relevant (suppressed 8 weaker matches):
  1. deploy-to-prod (0.92 confidence)
  2. pre-deploy-checklist (0.87)
  3. rollback-procedure (0.71)"
```

**Data structure sketches** - What would the stored data look like?
```python
procedure = {
    "name": "security-review",
    "preconditions": ["has_code_changes", "not_draft_pr"],
    "success_count": 12,
    "failure_count": 2,
    "linked_procedures": ["code-review", "pre-push-hook"]
}
```

**Design decisions** - What would the UI/UX feel like?
```
When showing related procedures, don't list everything above a threshold.
Show top 3, with "and 8 more..." collapsed. Let the user expand if curious.
```

**Agent dialogue** - What would multi-agent coordination look like?
```
Grace → Henry: "User wants to add auth. What work packages exist?"
Henry → Grace: "Found WP-042 (OAuth implementation). Nadia claimed it 2 hours ago, 60% complete."
```

### Guidelines for examples:

- **Adapt to context**: Reference the user's actual systems and terminology when you know it
- **Feel it out per concept**: Not every concept needs an example. Pick the ones where seeing it makes it click.
- **Prefer tangible over abstract**: A 3-line code snippet beats a paragraph of explanation
- **Show the happy path AND edge cases**: What does "it worked" look like? What does "I don't know" look like?
