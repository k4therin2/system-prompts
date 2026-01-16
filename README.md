# System Prompts & Skills

AI prompts and skills I use for various workflows.

## Skills vs Prompts

**Skills** are living instructions that evolve based on how I actually use them. I treat skills as procedural memory - they learn from my usage patterns, get updated when something works better, and reflect how I naturally work rather than how I thought I'd work.

**Prompts** are more static - copy-paste templates for specific workflows. Useful starting points, but they don't evolve with you.

## My Approach to Skills

I don't pre-design elaborate frameworks. Instead:

1. Start with a rough skill that captures intent
2. Use it in real work
3. Notice what's missing or awkward
4. Update based on what actually happened

Skills in this repo are **snapshots** - frozen moments of skills that have evolved through actual use. They're useful starting points, but the real value comes from adapting them to your own workflow and letting them learn from how you use them.

### If you want to build skills that learn from you:

- **Keep session transcripts** - Save your AI conversations so you can review them
- **Keep the skill simple** - Don't over-engineer upfront; let complexity emerge from actual needs
- **Add a log of recent examples to the skill itself** - Include a section in your skill file with recent uses, what worked, what you corrected
- **Update as part of your workflow** - After using a skill, spend 30 seconds noting what to change. Make updating the skill part of using the skill.

The pattern: Use → Notice → Update → Repeat. The skill gets better because it learns from your actual behavior, not your theories about how you'll work.

## What's Here

### `skills/`

Living skills that evolve with use:

- **paper-digest.md** - Translates academic papers into practical one-pagers focused on what matters for your work

### `prompts/`

Static agent prompts for specific workflows:

- **business-analyst-agent.md** - Evaluates feature proposals, prioritizes work, hands off to PM
- **requirements-reviewer.md** - Turns messy ideas into testable requirements
- **project-manager-agent.md** - Manages roadmaps and coordinates parallel work
- **tdd-developer** - Executes work from roadmaps using test-driven development

The BA → Requirements → PM → TDD Developer pipeline is demonstrated in my [Agentic AI Workshop](https://github.com/k4therin2/agentic-ai-workshop).

### `claude_code.md`

My Claude Code system prompt. **Note:** Anthropic ships updates frequently, so parts of this may be outdated or unnecessary as Claude Code evolves. Use it as a starting point and ask Claude to help you customize it.

## Related

- [Agentic AI Workshop](https://github.com/k4therin2/agentic-ai-workshop) - Workshop for learning to go from idea to implementation with tools like Claude Code
