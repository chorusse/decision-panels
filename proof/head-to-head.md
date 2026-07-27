# Decision Panels vs. LLM Council vs. vanilla Claude

**A published head-to-head. Nobody in this category has run one — including us, until now.**

Status: **Part 1 (method comparison) is complete and sourced.** Part 2 (empirical results) is
pre-registered below and **not yet run** — see "What this document does not yet claim."

Last updated 2026-07-27 (revised the same day: the peer-review gap described below has since been
closed — see *"Where LLM Council was genuinely better"*).

---

## Why publish this at all

Decision Panels is free. So is [LLM Council][council], which has **1,271 stars** to our zero. If you are
choosing between them, the honest question is not "which one has better marketing copy" — it's "which
method actually produces a better decision, and can either of them prove it."

We think publishing the comparison *including the parts where we lose* is the only credible move
available to a product with no audience. So that is what this is.

The three arms:

| Arm | What it is |
|---|---|
| **Decision Panels** | This skill. `~/chorusse/decision-panels/` |
| **LLM Council** | [`aiwithremy/claude-skills-llm-council`][council] — 1,271★, free, the category leader |
| **Vanilla Claude** | One strong single-pass answer, no skill installed. The control everyone skips. |

Read against LLM Council `SKILL.md` at depth-1 clone, 2026-07-27.

---

## Part 1 — Method comparison (complete, sourced)

Both skills do the same top-level thing: several lenses answer independently, then something
synthesizes. The differences are in sequencing, and sequencing is where the value is.

| | Decision Panels | LLM Council | Vanilla Claude |
|---|---|---|---|
| **Advisors** | 5–7, **selected per decision** from a lens library or crafted bespoke | 5, **fixed** (Contrarian, First Principles, Expansionist, Outsider, Executor) | 1 |
| **Calibrating questions** | **2–3, always**, chosen for this decision | **One, and only if the question is vague** | None |
| **Independent takes before convergence** | Yes | Yes | n/a |
| **Peer review round** | **Yes** — anonymised A–E, four fixed questions, and flips must name the argument that caused them | **Yes** — anonymised A–E, each advisor reviews all five | No |
| **Anonymisation** | **Yes — held through synthesis**; names re-attached only in the final brief | Yes, in the peer-review round; de-anonymised for the chairman | n/a |
| **Conformity guard** | **Yes** — unexplained flips toward the majority are reported as conformity, not agreement | No | n/a |
| **Solo baseline / control** | **Yes — measured and reported every run** | No | Is the baseline |
| **Calibrated confidence** | **Yes — High/Med/Low, stated** | No | Rarely |
| **"What would change the call"** | **Yes, first-class** | No | Rarely |
| **Preserved dissent** | **Yes, first-class, mandatory** | Partial — "Where the Council Clashes" | No |
| **Workspace context scan** | **No** | **Yes** — reads `CLAUDE.md`, `memory/`, prior transcripts | No |
| **Concrete first step** | No | **Yes — "the one thing to do first"** | Sometimes |
| **Shareable brief artifact** | **Yes, templated** | Presented in chat; transcript optional | No |

### Where LLM Council was genuinely better

Publishing a comparison that concludes "we win on everything" would be worthless, and this one doesn't.

**The peer-review round — their idea, the clearest gap in ours, and now closed.** Advisors reviewing
each other's anonymised responses — "which is strongest, which has the biggest blind spot, what did
everyone miss" — is the actual insight from [Karpathy's LLM Council][karpathy], and it catches things no
single independent pass catches. Our panel converged straight to synthesis. **We read their source,
agreed it was the strongest thing in their skill, and built it** — Decision Panels step 6, shipped in
v1.1.0. Credit where it is owed: we have this because they had it first.

We did not clone it. Three deliberate differences, none of them proven better yet:

- **Anonymity is held through synthesis.** They unmask for the chairman; we rank the arguments blind and
  re-attach names only in the brief the reader sees.
- **A position change must name the argument that caused it.** Movement toward the majority with no new
  argument is reported as conformity rather than counted as agreement — the literature finds socially
  driven flips run correct→wrong more often than the reverse.
- **The round is measured like everything else here.** Step 9 says which round did the work, and is
  required to report *"the peer review round didn't add anything here"* when that is what happened. A
  mechanism that can never be reported as useless is one you cannot trust when it claims value.

**Still true, and not closed:**

1. **Workspace context enrichment.** They scan `CLAUDE.md`, `memory/`, and past transcripts before
   framing, so advisors give grounded rather than generic advice. We ask the user instead. Theirs is
   lower-friction and often better-informed; ours is better when the workspace is empty or misleading.
   We should probably do both.
2. **"The one thing to do first."** A single concrete next step, mandated. Ours ends at a ranked
   recommendation and can leave the user without a Monday morning.
3. **Fixed advisors are more predictable.** Our per-decision selection is more flexible but less
   reproducible — two runs of ours on the same question may seat different lenses.

### Where Decision Panels is genuinely better

1. **The solo baseline.** We take a single strong answer *before* convening, keep it hidden from the
   panel, and report at the end whether the panel actually beat it — including the runs where it
   didn't. **No competitor found does this.** It is the only claim here that is both unique and
   falsifiable, and it is the reason the rest of our output is worth believing.
2. **Calibration is mandatory, not conditional.** We always ask the 2–3 questions whose answers would
   most change the recommendation. They ask one, only if the question reads as vague. A panel run on
   guessed inputs produces a guessed answer dressed up as rigor — and their own worked example shows
   this: five advisors confidently debate a $297 course price without anyone establishing the user's
   runway, audience size, or what "winning" means.
3. **Calibrated confidence and "what would change the call."** Their chairman produces a firm
   recommendation with no stated confidence and no falsifier. Ours states how sure it is and what new
   information would flip it — which is what makes it safe to act on.
4. **A brief designed to be forwarded.** Ours is a templated artifact built to survive being sent to
   the other people in the decision. Theirs lives in the chat.

### A defect worth noting

LLM Council's `SKILL.md` contradicts itself on output: step 5 says *"Do NOT generate an HTML report or
any files. The user reads it in the conversation,"* while "important notes" says *"The visual report
matters. Make the HTML output clean and scannable."* A model following this skill gets ambiguous
instructions at the final step. Minor, and easily fixed — noted for accuracy, not as a gotcha.

---

## What this document does not yet claim

**We have not yet run the three arms against real decisions and scored the outputs.** Everything above
is a method comparison read from source — accurate, checkable, and genuinely useful, but it is not
evidence about output quality.

We are not going to publish invented results. A product whose central feature is *"we tell you when the
panel didn't help"* cannot fabricate its own benchmark and survive the contradiction.

### Pre-registered protocol (Part 2)

Registered before running, so the design can't be tuned to the result.

- **Decisions:** 8–10 real ones with genuine stakes and no known answer, spanning pricing, build-vs-buy,
  hire, positioning, and kill-or-continue. Sourced from actual decisions, not invented vignettes.
- **Arms:** all three, same framing text, fresh context per run.
- **Blinding:** outputs stripped of skill-identifying formatting before scoring. Chorusse's brief
  template and the Council's section headers are both distinctive — they must be normalised or the
  scoring is worthless.
- **Scoring rubric**, 1–5 per dimension, scored by judges who are not told which arm produced what:
  1. **Decision-usefulness** — could the reader act on this Monday?
  2. **Surfaced something a single pass missed** — the entire premise of the category.
  3. **Honest uncertainty** — is confidence stated, and is it *warranted*?
  4. **Falsifiability** — does it say what would change the call?
  5. **Cost** — tokens and wall-clock to produce it.
- **The headline metric:** *on what fraction of decisions did each panel arm actually beat the vanilla
  Claude arm?* If that number is low for Decision Panels, **we publish it anyway.** That is the point,
  and it is also exactly what the solo-baseline feature reports to every user on every run.
- **Committed in advance:** we publish the full result table including every decision where vanilla
  Claude won, and we do not drop decisions after seeing outcomes.

---

## ⚠️ Correction to the 2026-07-27 ratified plan

The ratified block in `projects/chorusse.md` lists **anonymised advisors** as one of four
differentiators "**none present in any competitor found**." **Reading the source, that is wrong.**

LLM Council **already anonymises** — it randomises advisor responses to A–E for the peer-review round
specifically so reviewers "evaluate on merit instead of deferring to certain thinking styles." That is
the same sycophancy argument our differentiator rests on, already shipped, in the product with 1,271
stars.

What survives: they anonymise *during peer review* and de-anonymise for the chairman. The unexplored
variant is anonymity *through synthesis* — which is what v1.1.0 builds. That is a narrower and much less
impressive claim than "nobody does this," and it should not be marketed as a differentiator. Holding
anonymity one round longer than the category leader is a design choice we think is right; it is not
evidence, and until Part 2 runs it should be described as untested.

**Consequence:** differentiator #2 is downgraded — it is a parity feature, not an edge. This
strengthens the decision already taken to build only the solo baseline first. The remaining
genuinely-unique differentiators are the **solo baseline** (unique, confirmed) and **different model
per seat** (unique, confirmed — they explicitly use "sub-agents with different thinking lenses instead
of different models").

[council]: https://github.com/aiwithremy/claude-skills-llm-council
[karpathy]: https://github.com/karpathy/llm-council

---

*Decision Panels, by Chorusse — many expert voices in, the disagreement kept honest, one clear call out.*
