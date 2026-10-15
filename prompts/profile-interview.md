# Build your personal profile: let Claude interview you

A profile tells Claude who you are and how you want it to work, once, instead of in every chat.

## The prompt

In a fresh chat, paste:

> Help me build a persistent context profile. Ask ONE question at a time about: my role and
> courses; my code stack; my accuracy standards; preferred output format; what you should NEVER
> do; standing rules. Validate each answer. End with a complete Markdown profile in my exact words,
> and save it as ~/.claude/CLAUDE.md; if that file already exists, show me the changes and ask before
> overwriting it. If you cannot write files, tell me where to paste the profile instead.

## Where the profile goes

- Claude Code: `~/.claude/CLAUDE.md` for all your projects, or `CLAUDE.md` in one project folder.
- claude.ai: the personal instructions in Settings; they apply to every chat.
- Codex: `~/.codex/AGENTS.md`, or `AGENTS.md` in one project folder.

## What goes in it

Who you are (your course, Python and NumPy, what you have and have not taken); accuracy rules first;
the output format you want; hard limits ("never switch frameworks mid-answer").

## Keep it fresh

Once a month, ask: "review my instructions against our recent chats and propose fixes." Keep it
under a page; a bloated profile gets ignored.

## An example

```markdown
## How I want to work
- Explain the idea in two or three sentences before writing code.
- Show me the test before the implementation.
- Never change a test to make it pass; tell me why it fails.
- After making a figure, open it and tell me in one sentence what it shows.
```

The interview prompt comes from Kareem Hegazy's workshop "Working with Claude: a practical guide for
researchers" (ICSI, June 2026).
