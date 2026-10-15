# Skills for claude.ai

claude.ai accepts a skill only as a zip upload, so these are the three skills from `../skills/`,
zipped one per file:

1. Settings > Capabilities: turn on "Code execution and file creation".
2. Customize > Skills > + > Create skill > Upload a skill, once for each zip here.
3. Start a new chat with "Answer key: <your question>" or "Office hours: <your question>".

The answer-key and office-hours zips differ from `../skills/` in two places. Their header has no
"run only when typed" setting, which claude.ai does not accept, so the description says when to use
them; and their last line reads the question from the chat instead of from a typed command. Claude
Code users do not need these zips.
