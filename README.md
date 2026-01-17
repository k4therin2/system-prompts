# System Prompts & Skills

AI prompts and skills I use for various workflows.

## About the Skills Here

The skills in this repo are **static snapshots**—this is how Anthropic intends Claude Code skills to work. You define instructions, save them as a slash command, and use them.

I use skills a bit differently. My actual workflow treats skills as living documents that learn from usage: I keep session transcripts, review what worked vs what I corrected, and update skills based on patterns. The skills evolve over time based on how I actually use them, not how I thought I'd use them.

**The skills shared here don't include that learning layer**—that requires a different workflow (transcript review, example logging, regular updates). What you're getting is a functional snapshot of what my skills do right now, without the history of how they got there or the infrastructure that keeps them evolving.

If you're curious about the learning approach:
- Keep session transcripts so you can review them later
- Add a "recent examples" log to your skill file
- Update skills as part of using them (Use → Notice → Update → Repeat)

But for most people, just using these as static skills works fine.

## What's Here

### `skills/`

- **digest-paper.md** - Translates academic papers into practical one-pagers focused on what matters for your work

### `prompts/`

Agent prompts generalized from my December 2025 multi-agent automation experiment. These work standalone in Claude Code or as part of a pipeline.

**The Pipeline (idea → production):**

```
User idea → requirements-reviewer → business-analyst → project-manager → tdd-developer → qa-engineer
```

| Agent | What It Does |
|-------|--------------|
| **requirements-reviewer.md** | Turns messy ideas into testable REQ-### requirements |
| **business-analyst.md** | Prioritizes requirements, RICE scoring, Now/Next/Later |
| **project-manager.md** | Creates and maintains roadmaps, triages blockers |
| **tdd-developer.md** | Implements work from roadmaps using TDD |
| **qa-engineer.md** | Quality gates, test strategy, builds tooling |

**Standalone (use when needed):**

| Agent | What It Does |
|-------|--------------|
| **incident-manager.md** | Investigates issues, RCA, verification before closure |
| **system-analyst.md** | Context budgets, anti-pattern detection, design reviews |

**New to AI agents?** Start with the simplified versions in my [Agentic AI Workshop](https://github.com/k4therin2/agentic-ai-workshop) (3 agents, 90-minute workshop).

### `claude_code.md`

My Claude Code system prompt. **Note:** Anthropic ships updates frequently, so parts of this may be outdated or unnecessary as Claude Code evolves. Use it as a starting point and ask Claude to help you customize it.

## Related

- [Agentic AI Workshop](https://github.com/k4therin2/agentic-ai-workshop) - Workshop for learning to go from idea to implementation with tools like Claude Code
