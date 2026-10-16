# Stat 157: agent skills and a personal profile

From the lecture "Using agents to deal with high dimensions" by Kareem Hegazy and Maksim Melnichenko
(UC Berkeley, Stat 157, Fall 2026).

**Download everything as a zip:**
[stat157-agent-skills-main.zip](https://github.com/mmelnich/stat157-agent-skills/archive/refs/heads/main.zip)

**Slides of the lecture:**
[slides/2026-10-15-using-agents-high-dimensions.pdf](slides/2026-10-15-using-agents-high-dimensions.pdf)

## Build your profile: let Claude interview you

A profile tells Claude who you are and how you want it to work, once, instead of in every chat. In a
fresh chat, paste:

```text
Help me build a persistent context profile. Ask ONE question at a time about: my role and courses; my code stack; my accuracy standards; preferred output format; what you should NEVER do; standing rules. Validate each answer. End with a complete Markdown profile in my exact words, and save it as ~/.claude/CLAUDE.md; if that file already exists, show me the changes and ask before overwriting it. If you cannot write files, tell me where to paste the profile instead.
```

Where the profile goes:

- Claude Code: `~/.claude/CLAUDE.md` for all your projects, or `CLAUDE.md` in one project folder.
- claude.ai: the personal instructions in Settings; they apply to every chat.
- Codex: `~/.codex/AGENTS.md`, or `AGENTS.md` in one project folder.

Keep it under a page, and once a month ask Claude to review it against your recent chats. More in
[prompts/profile-interview.md](prompts/profile-interview.md). The prompt comes from Kareem Hegazy's
workshop "Working with Claude: a practical guide for researchers" (ICSI, June 2026).

## What is where

- `slides/`: the lecture slides (PDF).
- `prompts/`: the profile-interview prompt.
- `skills/`: the three skills, one folder each, for Claude Code (also Codex and Gemini CLI).
- `claude-ai-uploads/`: the same three skills zipped for claude.ai (Claude in the browser), which accepts a skill only as a
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

## Add-ons worth installing

Free add-ons for Claude Code, by category. Plugins install from inside Claude Code with
`/plugin install <name>@claude-plugins-official` (the official marketplace is preloaded). Read what
you install: a plugin or skill runs with your permissions.

| Name | Kind | What it does | Install |
|------|------|--------------|---------|
| **Correctness signal** | | | |
| clangd-lsp | plugin, first-party | C/C++ diagnostics on every edit; find references | `/plugin install clangd-lsp@claude-plugins-official` |
| pyright-lsp | plugin, first-party | Same for Python (type and import errors) | `/plugin install pyright-lsp@claude-plugins-official` |
| context7 | MCP server, community | Current, version-specific library docs | `/plugin install context7@claude-plugins-official` |
| **Discipline, review, cleanup** | | | |
| superpowers | plugin, community | Spec, failing test, implement, debug | `/plugin install superpowers@claude-plugins-official` |
| code-review | plugin, first-party | Multi-agent PR review, confidence-scored | `/plugin install code-review@claude-plugins-official` |
| code-simplifier | plugin, first-party | Behavior-preserving cleanup of new code | `/plugin install code-simplifier@claude-plugins-official` |
| security-guidance | plugin, first-party | Flags injection, unsafe deserialization, leaked secrets | `/plugin install security-guidance@claude-plugins-official` |
| **Tokens and cost** | | | |
| [codeburn](https://github.com/getagentseal/codeburn) | CLI tool, open source | Token and cost meter for 31 tools, local only | `npx codeburn` in a terminal |
| [caveman](https://github.com/JuliusBrussee/caveman) | skill, community | Terse output, about two-thirds fewer tokens | `/plugin marketplace add JuliusBrussee/caveman`, then `/plugin install caveman@caveman` |
| **Workflow** | | | |
| commit-commands | plugin, first-party | `/commit`, push, full PR in one bundle | `/plugin install commit-commands@claude-plugins-official` |
| skill-creator | plugin, first-party | Scaffold, evaluate and audit your own skills | `/plugin install skill-creator@claude-plugins-official` |

The catch: of 3,984 public skills that Snyk audited in 2026, 36.8% had a flaw and 76 carried
malware ([ToxicSkills](https://snyk.io/blog/toxicskills-malicious-ai-agent-skills-clawhub/)).

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
