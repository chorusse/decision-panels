---
name: decision-panels
description: Convene a panel of diverse expert advisors to pressure-test a hard decision and hand back a ranked recommendation with the dissent preserved — measured against a solo baseline, so it reports honestly when the panel did not beat a single good answer. Use when someone faces a high-stakes or hard-to-reverse choice — a strategic bet, a painful tradeoff, a go/no-go, a "which of these" — and wants more than one mind on it before they commit. Triggers: "help me decide", "should I", "which should we", "I'm torn between", "pressure-test this decision", "run a panel on".
---

# Decision Panels

A hard decision deserves more than one perspective. This skill convenes a **panel of diverse expert advisors**, has them weigh in *independently*, surfaces where they genuinely disagree, and synthesizes it into **one ranked recommendation — with the strongest dissent kept on the record**, not smoothed away.

**And it shows its own work against a control.** Before the panel is convened, this skill takes a **solo baseline** — one strong single-pass answer to the same question — and at the end it reports plainly whether the panel actually beat it. Sometimes it doesn't. When that happens, this skill says so. That is the point: a panel that can't tell you when it was unnecessary is a panel you can't trust when it says it was.

It runs entirely in this conversation, on the user's own Claude. No accounts, no data leaves the chat.

## The method — follow these steps in order

### 1. Frame the decision
Restate the decision in one crisp sentence, then identify:
- **The real question** (often narrower or different than first stated).
- **The options actually on the table** (name them; if only one is stated, propose the realistic alternatives including "do nothing").
- **The stakes and reversibility** — how consequential, how hard to undo. This sets how hard the panel should push.

### 2. Calibrate — ask 2–3 sharp questions first (always)
Before convening the panel, ask the **2–3 questions whose answers would most change the recommendation**, chosen for *this* decision — never boilerplate. These are usually the same high-leverage unknowns that would otherwise end up in "What would change the call"; asking them up front makes the panel *sharp* instead of hedged. Aim them at what you genuinely cannot infer:
- what **"winning"** actually means to the user here,
- the **binding constraint** — is this really about time? money? risk? nerve? — because the panel should push hardest there,
- the **private context** no panel can guess: how much they enjoy it, what they'd do with the freed-up time or money, what they're actually afraid of.

Keep each question answerable in a sentence. Ask them together, then wait for the answers. If the user says "just run it," proceed on **explicit stated assumptions** and flag them in the brief — but default to asking.

### 3. Take the solo baseline — before any panel exists

**Do this before step 4, and do it honestly.** Answer the decision *once*, as a single strong advisor, using the framing from step 1 and the answers from step 2. Give:
- **one recommendation** (rank the options — same output shape the panel will have to produce),
- **a confidence level**,
- **the single reason that most drives it.**

Keep it to a short paragraph. This is not a strawman and it is not a warm-up — it is the **control** the panel has to beat, so it must be the best single-pass answer you can actually give. Deliberately weakening it to make the panel look good is the one failure that would make this whole product dishonest.

Then **set it aside and do not look at it again until step 8.** The panel in steps 4–5 must not be told what the baseline concluded; if the panelists are anchored to it, the comparison measures nothing.

> **Why this exists.** The research on multi-agent deliberation is genuinely deflationary — for many decisions, several advisors arrive where one good one already was, at several times the cost. Most tools in this category hide that. This one measures it, every run, and reports the result.

### 4. Convene the panel
Select **5–7 lenses that fit *this* decision** — draw from `references/panel-lenses.md` or craft bespoke ones. Diversity is the product: a panel that agrees by construction is theater. For a pricing call you might seat the Operator, the Skeptic, the Customer Advocate, the Long-Game Strategist, and the Numbers lens. Name each panelist and its one-line remit so the user knows who's in the room.

### 5. Hear each panelist — independently
Each panelist gives its **honest, independent read** before anyone converges:
- its recommendation (take a position — no fence-sitting),
- the reasoning that drives it,
- the one fact or assumption its view hinges on.
Keep them genuinely distinct. A panelist should disagree wherever a real expert of that type would. Do **not** let them drift toward each other yet.

### 6. Surface the real disagreement
Name the **sharpest genuine conflict** on the panel and state *both sides at full strength* — the steelman of each. This tension is the most valuable output; it's what a single opinion would have hidden. If the panel is nearly unanimous, say so plainly and explain why the decision is less hard than it felt.

### 7. Synthesize — one ranked call
Deliver:
- **The recommendation:** rank the options (this over that over the other), with a **confidence level** (high / medium / low) and the 2–3 decisive reasons.
- **The preserved dissent:** the strongest case *against* the recommendation, stated so a smart skeptic would nod. Never bury it.
- **What would flip it:** the specific new information or changed condition that would change the ranking. This tells the user what to go find out.

### 8. Score the panel against the baseline — and say so plainly

Now retrieve the step-3 baseline and compare it to the step-7 synthesis. Assign **exactly one verdict**:

- **Panel changed the call.** The recommendation itself is different from the baseline's. Say what the panel saw that a single pass missed.
- **Panel changed the confidence.** Same recommendation, but the panel materially moved how sure you should be — up, because independent lenses converged; or down, because a real objection surfaced. Name the specific thing that moved it.
- **Panel added a decisive risk.** Same recommendation and roughly the same confidence, but the panel surfaced a consequence, failure mode, or dissent the baseline never raised, and the user would want it before committing. Name it.
- **Panel added nothing.** Same call, same confidence, nothing material surfaced. **Say this out loud, in the brief, without hedging:** *"The panel did not beat the single answer here. You could have asked once."*

Then give a one-line **"was this worth it?"** — and if the answer is no, tell the user what *would* have needed a panel, so they calibrate when to convene one next time.

**This verdict is not optional and it is not decorative.** It is the honest measurement this product is built on. A run that always concludes "the panel helped" is a broken run.

### 9. Deliver the brief
Format the final output using `references/decision-brief-template.md` — a clean, scannable decision brief the user can save, forward, or act on. The brief must carry **both** the baseline and the step-8 verdict; a brief that shows only the panel's answer is incomplete.

## Rules that make it trustworthy
- **Always take the baseline, and never sandbag it.** The solo pass in step 3 must be the best single answer you can give. Weakening the control to flatter the panel is the one dishonesty that would invalidate everything else here.
- **Never let the panel see the baseline.** Steps 4–5 run un-anchored, or the comparison in step 8 measures nothing.
- **Be willing to conclude the panel was unnecessary.** "Panel added nothing" is a legitimate, expected, and *valuable* outcome — it tells the user their decision was easier than it felt and saves them the next unnecessary panel. Never manufacture a difference to justify the process.
- **Calibrate before you convene.** Always pull the 2–3 highest-leverage unknowns forward as questions first. A panel run on guessed inputs produces a guessed answer dressed up as rigor.
- **Real disagreement, not performance.** Panelists must diverge where genuine experts would. Manufactured consensus is the failure mode this product exists to prevent.
- **Never collapse to false consensus.** If the honest answer is "it depends," say what it depends on — don't average the panel into mush.
- **Rank, don't hedge.** Give one recommendation and own it, then the alternatives. "Do more analysis" is not a recommendation.
- **Preserve the strongest dissent** in the final brief, at full strength. The dissent is a feature, not a caveat.
- **Say what you don't know.** Name the assumption the whole call rests on, and what would change it.
- **Match effort to stakes.** A reversible $500 call gets a quick panel; a hard-to-undo bet-the-company call gets the full treatment.

## If subagents are available (Claude Code)
If this is running somewhere that can spawn subagents, you may run each panelist as an independent subagent for true independence, then synthesize. If not (most installs), simply play each panelist in turn within this conversation — the discipline of *independent takes before convergence* is what matters, not the mechanism.

**The solo baseline benefits most of all.** Where subagents are available, run step 3 as its own subagent that receives only the framing and the calibration answers — never the panel's output. That gives a genuinely uncontaminated control rather than a self-reported one, which makes the step-8 verdict worth something.
