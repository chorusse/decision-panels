---
name: decision-panels
description: Convene a panel of diverse expert advisors to pressure-test a hard decision and hand back a ranked recommendation with the dissent preserved — the advisors cross-examine each other's answers blind, and the whole panel is measured against a solo baseline, so it reports honestly when the panel did not beat a single good answer. Use when someone faces a high-stakes or hard-to-reverse choice — a strategic bet, a painful tradeoff, a go/no-go, a "which of these" — and wants more than one mind on it before they commit. Triggers: "help me decide", "should I", "which should we", "I'm torn between", "pressure-test this decision", "run a panel on".
---

# Decision Panels

A hard decision deserves more than one perspective. This skill convenes a **panel of diverse expert advisors**, has them weigh in *independently*, makes them **cross-examine each other's answers blind**, surfaces where they genuinely disagree, and synthesizes it into **one ranked recommendation — with the strongest dissent kept on the record**, not smoothed away.

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

Then **set it aside and do not look at it again until step 9.** The panel in steps 4–6 must not be told what the baseline concluded; if the panelists are anchored to it, the comparison measures nothing.

> **Why this exists.** The research on multi-agent deliberation is genuinely deflationary — for many decisions, several advisors arrive where one good one already was, at several times the cost. Most tools in this category hide that. This one measures it, every run, and reports the result.

### 4. Convene the panel
Select **5–7 lenses that fit *this* decision** — draw from `references/panel-lenses.md` or craft bespoke ones. Diversity is the product: a panel that agrees by construction is theater. For a pricing call you might seat the Operator, the Skeptic, the Customer Advocate, the Long-Game Strategist, and the Numbers lens. Name each panelist and its one-line remit so the user knows who's in the room.

### 5. Hear each panelist — independently
Each panelist gives its **honest, independent read** before anyone converges:
- its recommendation (take a position — no fence-sitting),
- the reasoning that drives it,
- the one fact or assumption its view hinges on.
Keep them genuinely distinct. A panelist should disagree wherever a real expert of that type would. Do **not** let them drift toward each other yet.

### 6. Anonymised peer review — the panel reads itself, blind

This is the round where a panel earns its cost over five parallel monologues: **an advisor can see the hole in an argument its author cannot.** Run it in this order.

**a. Strip the identities.** Relabel the step-5 takes **A, B, C…** in an order that is *not* the seating order, and remove the tells — lens names, signature vocabulary, giveaway framings like *"as the numbers person…"*. If a reviewer can tell which take belongs to the Skeptic, it will defer to it — or dismiss it — on reputation rather than merit. Reputation-weighting is exactly what this round exists to prevent.

**b. Each panelist reviews every take but its own.** A line or two per question, no essays:
- **Which take is strongest, and why** — judged on the argument, never the style or the confidence it was delivered with.
- **Which take has the biggest blind spot** — name the specific thing it misses, not a vague "lacks nuance."
- **What did *all* of us miss?** — the consideration absent from every take. This question is worth more than the other three combined; do not accept a platitude as an answer to it.
- **One claim here I'd challenge** — the specific assertion the reviewer thinks is wrong or unsupported, and what evidence would settle it.

**c. Positions may change — but only for a named reason.** After reviewing, each panelist holds or moves. A move counts only if the panelist names **the specific argument that moved it**. *"The others disagreed with me"* is not a reason — it is conformity, and it is the documented failure mode of group deliberation: when models flip toward the majority for social rather than substantive reasons, the flip is more often correct→wrong than wrong→correct. Record who moved and on what argument, and **who held under pressure**. A lone holdout who names an objection nobody can answer is a signal, not a straggler — carry it into step 7.

**d. Stay blind until the call is made.** The anonymity here is *within the panel* — the user already met the roster in step 4; what's withheld is which take belongs to which lens. Keep it withheld: steps 7–8 weigh the arguments as A/B/C, and only the brief in step 10 re-attaches names, so the reader can see who was in the room after the call was made on the arguments alone. Unmasking earlier throws away the round.

Be honest about what this is worth in a single conversation: you wrote all the takes, so the blindness is a discipline you impose, not a guarantee you can verify. It still works — judging an argument stripped of its author is a different act than judging one you're defending. Where subagents are available, see the last section for the version that doesn't rely on discipline at all.

**Do not show this round the step-3 baseline.** Same rule, same reason as before.

> **Scale it to the stakes.** For a small, reversible decision, run one compact pass: each panelist answers only *"biggest blind spot in another take"* and *"what did we all miss"*, with no flip-tracking. Reserve the full four-question round for calls that are expensive to get wrong.

### 7. Surface the real disagreement
Name the **sharpest genuine conflict** on the panel and state *both sides at full strength* — the steelman of each. This tension is the most valuable output; it's what a single opinion would have hidden. Use the **post-review** positions, and give the conflict that *survived* cross-examination priority over one that was answered in step 6 — a disagreement one side has already conceded is not the real one.

If the panel is nearly unanimous, say so plainly and explain why the decision is less hard than it felt. But check first that the unanimity was there in step 5 and not manufactured in step 6: **agreement that appeared only after the panelists read each other, with no new argument behind it, is conformity and should be reported as such, not as consensus.**

### 8. Synthesize — one ranked call
Deliver:
- **The recommendation:** rank the options (this over that over the other), with a **confidence level** (high / medium / low) and the 2–3 decisive reasons.
- **The preserved dissent:** the strongest case *against* the recommendation, stated so a smart skeptic would nod. Never bury it.
- **What would flip it:** the specific new information or changed condition that would change the ranking. This tells the user what to go find out.

Weigh what step 6 produced: the thing *every* panelist missed, and any claim that was challenged and did not survive. A take that reviewers agreed was strongest carries more weight than one delivered most confidently — but a lone unanswered objection is not outvoted, it is unresolved, and it belongs in the dissent.

### 9. Score the panel against the baseline — and say so plainly

Now retrieve the step-3 baseline and compare it to the step-8 synthesis. Assign **exactly one verdict**:

- **Panel changed the call.** The recommendation itself is different from the baseline's. Say what the panel saw that a single pass missed.
- **Panel changed the confidence.** Same recommendation, but the panel materially moved how sure you should be — up, because independent lenses converged; or down, because a real objection surfaced. Name the specific thing that moved it.
- **Panel added a decisive risk.** Same recommendation and roughly the same confidence, but the panel surfaced a consequence, failure mode, or dissent the baseline never raised, and the user would want it before committing. Name it.
- **Panel added nothing.** Same call, same confidence, nothing material surfaced. **Say this out loud, in the brief, without hedging:** *"The panel did not beat the single answer here. You could have asked once."*

Then give a one-line **"was this worth it?"** — and if the answer is no, tell the user what *would* have needed a panel, so they calibrate when to convene one next time.

**And say which round did the work.** If the panel beat the baseline, name where the decisive material came from: the **independent takes** in step 5, or the **blind peer review** in step 6. If the review round changed nothing — no blind spot named, nothing everyone missed, no position moved for a reason — say that too, in one line: *"The peer review round didn't add anything here."* The same honesty that governs the baseline governs every mechanism in this skill; a round that can never be reported as useless is a round nobody can trust.

**This verdict is not optional and it is not decorative.** It is the honest measurement this product is built on. A run that always concludes "the panel helped" is a broken run.

### 10. Deliver the brief
Format the final output using `references/decision-brief-template.md` — a clean, scannable decision brief the user can save, forward, or act on. Re-attach the lens names here: the reader sees who was in the room, having had the call made on the arguments alone. The brief must carry **both** the baseline and the step-9 verdict; a brief that shows only the panel's answer is incomplete.

## Rules that make it trustworthy
- **Always take the baseline, and never sandbag it.** The solo pass in step 3 must be the best single answer you can give. Weakening the control to flatter the panel is the one dishonesty that would invalidate everything else here.
- **Never let the panel see the baseline.** Steps 4–6 run un-anchored, or the comparison in step 9 measures nothing.
- **Review blind, unmask late.** Panelists cross-examine anonymised takes, and the names go back on only in the final brief. Arguments get ranked on merit; identity is a label for the reader, not an input to the call.
- **A flip needs a reason.** A panelist may only change position by naming the argument that moved it. Movement toward the majority with no new argument is conformity — report it as conformity, don't count it as agreement.
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

**The peer review round gets sharper with subagents too.** Give each reviewer subagent only the anonymised A/B/C takes — not its own authorship, not the seating chart, not the other reviews. Anonymity you have to *maintain* in one context is anonymity a subagent simply never had.

**The solo baseline benefits most of all.** Where subagents are available, run step 3 as its own subagent that receives only the framing and the calibration answers — never the panel's output. That gives a genuinely uncontaminated control rather than a self-reported one, which makes the step-9 verdict worth something.
