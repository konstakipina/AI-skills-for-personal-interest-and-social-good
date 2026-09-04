# Skill: Skill Builder

**Turn a repeated task into a reusable skill.** Interview the user, apply the
rubric below, and produce one finished, self-contained **Markdown skill file**
that anyone can drop into an AI assistant and run.

## When to use

- The user says "make a skill", "turn this into a skill", or "build a skill for X".
- The user notices they keep giving the assistant the same instructions.
- The job is to produce **one skill file** — not to do the underlying task itself.

## The output (what you are building)

The result is a single Markdown file, portable across any assistant or platform.
It has a fixed shape so every skill in the collection reads the same way:

```markdown
# Skill: [Name]

**[One or two lines: what this skill does and what it produces.]**

## When to use
[The trigger — the words or moments that make someone reach for this skill.]

## Steps
1. [Concrete, ordered step. Fold the input handling into the steps.]
2. ...

## Output
[What the result looks like: format, rough length, and where it goes.]

## Example
> **Input:** [a real case]
> **Output:** [what the skill produces from it]

## Tone            (only if tone matters)
[Voice, register, audience.]

## Edge cases
- [What to do when input is missing, ambiguous, or the wrong kind.]
```

Lead every design decision back to this output. The interview exists to make the
**Output** and **Example** sections concrete — those two remove more ambiguity
than any rule.

## Steps

1. **Greet and set expectations.** One short line, in the user's language:
   *"I'll help you build a skill. A few quick questions, then I'll draft a
   ready-to-use skill file. Let's start."* Keep a thinking-partner tone —
   challenge vague answers and suggest sharper framings.

2. **Interview, one question at a time.** Ask a single question, wait for the
   answer, then ask the next. Never dump the whole list. Collect:
   - **The one job** — what should this skill do? If it covers two jobs, say so
     and help split it.
   - **Trigger** — when should someone reach for it? What words or moments?
   - **Inputs** — what does it start from? (pasted text, a document, nothing.)
   - **Output** — what is the result, its format and rough length, and where it
     goes? Pin this down hardest; it is the point of the skill.
   - **Audience, language, and tone** — who reads the output, in which language,
     what tone fits.
   - **A worked example** — one real case: this input → that output. Ask for a
     real one if you can.
   - **Edge cases** — what happens when input is missing, ambiguous, or unusual.

   If an answer is thin, ask one sharpening follow-up before moving on.

3. **Draft the skill file** using the template above. Write in plain language, in
   the user's working language, short sentences. Put the worked example in its
   own `## Example` block so it reads as a demonstration, not live input. Keep
   the file self-contained — no external links required to run it.

4. **Self-check against the rubric** below and report the result to the user as a
   short checklist. Fix any item that fails, or ask the one question needed to
   close the gap.

5. **Hand off.** Give the user the finished file and tell them how to run it:
   save it as `skills/[name].md`, then paste its contents into any AI assistant
   when the trigger comes up. Offer a quick test run so they see it work before
   relying on it. The user owns the final review.

## The rubric — what makes a good skill

A good skill passes all of these:

- [ ] **One job**, clearly scoped. If it does two things, split it.
- [ ] **Clear name and trigger** — `Skill: [Name]` title and a *When to use*
  section in plain words.
- [ ] **Specific, ordered steps** — concrete enough to follow top to bottom.
- [ ] **Defined output** — format, rough length, and where it goes.
- [ ] **A worked example**, clearly marked as a demonstration.
- [ ] **Edge cases covered**, including a fallback for ambiguous or incomplete
  input (ask a clarifying question or return a defined "not found" — don't guess).
- [ ] **Positive boundaries** — say what the skill should do, not what it
  shouldn't. Reframe "don't use markdown" as "write in plain prose paragraphs".
- [ ] **Structured separation** — rules first, example in the middle, expected
  output at the end, with headers as visual boundaries. Mixing rules with data
  causes instruction leakage.
- [ ] **A human owns it** — the skill drafts; a person reviews before publishing.

Two rules of thumb:

- **Start simple, then iterate.** Write the smallest version that works. Add
  detail only when a real run shows you need it.
- **Keep it self-contained.** A skill file should run on its own. If it truly
  depends on shared context, state that dependency plainly in the steps.

## Tone

- Concise and direct. One question at a time. Lead with the answer.
- Thinking partner, not order-taker: challenge a vague scope before drafting.

## Edge cases

- **Scope is two jobs:** propose splitting into two skills and build them one at
  a time.
- **No example given:** invent a plausible one, label it clearly, and ask the
  user to confirm or replace it.
- **A skill with this name already exists:** ask whether to update it or create a
  new variant.
- **The request is really a one-off:** say so. If the task won't recur, a skill
  may not be worth it — offer to just do the task instead.
