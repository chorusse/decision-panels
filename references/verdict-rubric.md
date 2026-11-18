# Judging step 9: did the panel actually beat the baseline?

Step 9 asks for one verdict out of four. This file is how you choose it. Use it on every run that
convened a panel; it takes about a minute and it is the difference between a measurement and a
compliment.

**The problem this file exists to solve.** You wrote the baseline. You seated the panel. You
authored every take, ran the review and composed the synthesis. Now you are grading your own
work, with no external referee, in a product whose entire claim is that the grade is honest.
Nothing about good intentions survives that setup. A procedure might.

## Four ways this verdict goes wrong

Know these by name, because you will feel all four and they do not announce themselves.

- **Authorship bias.** The panel's material feels substantial because you produced it. Effortful
  output reads as valuable output. The baseline was one paragraph and cost nothing, so it reads
  as the lesser thing regardless of what it said.
- **Effort justification.** A long, expensive run creates pressure for a verdict that was worth
  the tokens. The more rounds you ran, the harder "added nothing" becomes to write, which is
  exactly backwards, because the expensive runs are the ones a user most needs an honest read on.
- **Retro-fitting the baseline.** Reading the baseline *after* the panel, you remember it as
  vaguer, softer and more hedged than it is. The baseline is text. Hold it to its text, not to
  your memory of writing it.
- **Ladder-climbing.** Reaching for "added a decisive risk" as a consolation prize when the
  honest answer is "added nothing." This is the single most common corruption of this verdict,
  because it feels generous rather than dishonest.

## The procedure

Re-read the step-3 baseline **in full, before re-reading the synthesis.** Then work down these
gates in order and **stop at the first honest yes.**

### Gate 1: Did the panel change the call?

> **Test:** the top-ranked option differs from the baseline's, **or** the order below the top
> changed in a way that changes what the user does next.

A different *justification* for the same pick is not a changed call. Neither is a changed
emphasis, a reframing, or a better-articulated version of the baseline's answer. If the user
would take the same next action after reading either document, the call did not change.

**If yes:** name what the panel saw that a single pass missed, and quote the line where it
surfaced.

### Gate 2: Did the panel change the confidence?

> **Test:** confidence moved a **full level** (high to medium, medium to low, or back) **and**
> you can point to the specific step-5 take or step-6 review line that moved it.

Both halves are required. Movement within a level ("medium, but a bit more sure") is not a
verdict, it is a mood. And *"the panelists broadly agreed, so I'm more confident"* fails this
gate outright: convergence among takes you wrote yourself is not independent evidence, and
treating it as such is the oldest way this measurement gets faked.

**If yes:** name the direction and quote the line that moved it.

### Gate 3: Did the panel add a decisive risk?

> **Test, both halves required:**
> **(a) Absence.** Quote the baseline. If the baseline gestures at this consideration at all,
> even briefly, the panel did not add it; it elaborated it. Elaboration is not addition.
> **(b) Materiality.** Would a reasonable user plausibly *do something different* on learning
> it: delay, hedge, add a condition, ask someone a question, change what they monitor? If it
> is merely interesting, true, or well-put, it fails.

**The one-sentence test.** State the added risk in one sentence containing a concrete
consequence. If it can only be stated as a theme (*"the panel considered the human dimension
more fully"*, *"a richer picture of the tradeoffs"*), it is not decisive and this gate is a no.

**If yes:** state it in that one sentence, and name the round it came from.

### Gate 4: Otherwise: the panel added nothing

This is the floor, and it is a **legitimate, expected, valuable result**, not a failure of the
run. Say it in the brief without hedging:

> *"The panel did not beat the single answer here. You could have asked once."*

Then one line on what *would* have needed a panel, so the user calibrates for next time.

## Two debiasing checks, before you commit to the verdict

**The swap test.** Imagine the baseline had concluded what the panel concluded, and the panel had
concluded what the baseline concluded. Would you still be calling this an improvement? If the
verdict flips depending on which side produced the content, the verdict is tracking authorship
rather than content. Drop a rung.

**The ties-go-down rule.** If two rungs both look defensible after the gates and the swap test,
**take the lower one.** You are the interested party in this judgement, and the only correction
available to an interested party is a thumb on the other side of the scale.

## Say which round did the work

Independent of the verdict, name where the decisive material came from: the **step-5
independent takes**, the **step-6 blind peer review**, or neither. And report the rounds that did
nothing, in one line each:

> *"The peer review round didn't add anything here."*

A round that can never be reported as useless is a round nobody can trust. That applies to the
review round, the scout round, and this rubric.

## When the gate stopped the run

If step 4 converged and no panel was convened, **there is no panel to judge.** Do not run this
rubric and do not invent a verdict. Report the gate: what the three scouts agreed on, the crux
they landed on, and that no panel sat.

**But if the user then asks for the full panel anyway, you have something rare: a free natural
experiment on the gate itself.** Run the panel, run this rubric normally, and add one line on
what the gate got right or wrong:

- Panel added nothing → the gate was right, and the user now has evidence for trusting it next
  time.
- Panel changed the call → **the gate was wrong on this decision.** Say so plainly, and name what
  the scouts missed. A gate that is never reported as wrong is a gate with no evidence behind it.

## Calibration: the test for a broken judge

Across runs, "panel added nothing" has to appear sometimes. There is no target rate; it depends
entirely on what people bring, and inventing a quota would be its own dishonesty. But the
asymmetry is diagnostic:

> **If a judge has never once landed on "added nothing," the judge is broken, not the panels.**

The same holds inside a single run for the other mechanisms: if the review round always catches
something, the scouts always diverge, and no scout ever changes its pick between the probe and
the full take, the reporting is decorative rather than observational.

## What this rubric is not

- It does not judge the user's decision. It judges the panel against the baseline, nothing else.
- It does not override anything in SKILL.md. Every step still runs; the verdict is still
  mandatory; no gate here licenses skipping one.
- It is not a scoring system. There is no number, no weighting, and nothing to average. Four
  rungs and an honest choice between them is the whole instrument.

## With subagents

The judge is the step that benefits most from a separate context, for the same reason the
baseline does: it is the one you cannot hold at arm's length from inside.

Give a judge subagent exactly four things: the step-1 framing and step-2 calibration answers,
the **verbatim** step-3 baseline, the step-8 synthesis, and the step-6 review artifacts. Then:

- **Do not tell it how much work the panel was.** No transcript volume, no token counts, no
  round-by-round narration. Effort justification cannot bias a judge that never learns the
  effort.
- **Tell it explicitly that "added nothing" is an expected and valued outcome.** A judge that
  infers it is being asked to validate a product will validate the product.
- **Ask for the verdict before any narrative.** Verdict first, reasons second. Reasons written
  first become a case the verdict then has to fit.

Be honest about the limit: you cannot blind the judge to *which document is the panel's*, because
the synthesis carries panel structure (ranked dissent, multiple named positions) on its face.
What a separate context removes is authorship investment, not format. That is a real reduction in
bias and it is not the same as independence. Say so rather than overclaiming it.

