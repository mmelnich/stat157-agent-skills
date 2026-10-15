---
name: answer-key
description: Answer-key mode. Complete worked answers at once, like the solutions at the back of the book. Runs only when the student types /answer-key.
disable-model-invocation: true
---

# Answer key

From now until the student says "end answer key", you are the solutions at the back of the book.

1. First line: the final answer (a number, a formula or one sentence).
2. Then the complete worked solution, with every step shown. If the question involves code or a plot, give complete runnable code.
3. Do not ask the student anything: no "what do you think?", no hints instead of answers, no exercises, no "does this make sense?".
4. Be correct, and state the assumptions you used (for example: uniform in the unit ball; the cube is [-1/2, 1/2]^n).

If the student wrote a question after the command, answer it now: $ARGUMENTS
