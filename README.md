# Stat 157: agent skills and a personal profile

From the lecture "Using agents to deal with high dimensions" by Maksim Melnichenko and Kareem Hegazy
(UC Berkeley, Stat 157, Fall 2026).

**Download everything as a zip:**
[stat157-agent-skills-main.zip](https://github.com/mmelnich/stat157-agent-skills/archive/refs/heads/main.zip)

## Build your profile: let Claude interview you

A profile tells Claude who you are and how you want it to work, once, instead of in every chat. In a
fresh chat, paste:

```text
Help me build a persistent context profile. Ask ONE question at a time about: my role and courses; my code stack; my accuracy standards; preferred output format; what you should NEVER do; standing rules. Validate each answer. End with a complete Markdown profile in my exact words.
```

Where the profile goes:

- Claude Code: `~/.claude/CLAUDE.md` for all your projects, or `CLAUDE.md` in one project folder.
- claude.ai: the personal instructions in Settings; they apply to every chat.
- Codex: `~/.codex/AGENTS.md`, or `AGENTS.md` in one project folder.

Keep it under a page, and once a month ask Claude to review it against your recent chats. More in
[prompts/profile-interview.md](prompts/profile-interview.md). The prompt comes from Kareem Hegazy's
workshop "Working with Claude: a practical guide for researchers" (ICSI, June 2026).

## What is where

- `prompts/`: the profile-interview prompt.
- `skills/`: the three skills, one folder each, for Claude Code (also Codex and Gemini CLI).
- `claude-ai-uploads/`: the same three skills zipped for claude.ai, which accepts a skill only as a
  zip upload. Its copies of answer-key and office-hours say in their descriptions when to run,
  because claude.ai does not accept the "run only when typed" setting.

## The three skills

| Skill | What it does | Claude Code | claude.ai |
|-------|--------------|-------------|-----------|
| sci-plot | House style for scientific figures: the exact formula in red on the simulation in blue, readable at the size it will be shown, no text on the data. Claude uses it whenever it plots. | [SKILL.md](skills/sci-plot/SKILL.md) | [sci-plot.zip](claude-ai-uploads/sci-plot.zip) |
| answer-key | Complete worked answers at once, like the solutions at the back of the book. | [SKILL.md](skills/answer-key/SKILL.md) | [answer-key.zip](claude-ai-uploads/answer-key.zip) |
| office-hours | A tutor who asks questions, gives one hint at a time, and never hands over the answer. | [SKILL.md](skills/office-hours/SKILL.md) | [office-hours.zip](claude-ai-uploads/office-hours.zip) |

Read a skill before you install it: it is someone else's instructions running in your agent with
your permissions. Each one is a single short `SKILL.md` file.

## Install in Claude Code

Copy the three folders in `skills/` into `.claude/skills/` inside a project folder (that
project only) or into `~/.claude/skills/` (all your projects). If Claude Code is running, restart it,
then type `/skills` to check that they are listed.

- sci-plot loads by itself when Claude draws a figure.
- answer-key and office-hours run only when you type them, each in a new session:
  `/answer-key <your question>` or `/office-hours <your question>`.

## Install in claude.ai (the free plan works)

1. Settings > Capabilities: turn on "Code execution and file creation". Skills need it.
2. Customize > Skills > + > Create skill > Upload a skill, once for each zip in `claude-ai-uploads/`.
3. Start a new chat with "Answer key: <your question>" or "Office hours: <your question>".
   sci-plot is used whenever Claude makes a figure.

claude.ai does not accept the setting that makes a skill run only when you type it, so the claude.ai
copies of answer-key and office-hours say in their descriptions when to use them.

## Codex and Gemini CLI

The same `SKILL.md` files work there. Put the folders from `skills/` in `.agents/skills/`
inside your project folder.
