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
