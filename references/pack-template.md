# <TIER> pack: <PACK NAME>

A pack adapts Decision Panels to a domain. It does not replace the method in `SKILL.md`; every step
still runs, including the baseline, the gate, the blind review, and the step-9 verdict. A pack
supplies the *domain judgement* those steps need: where people in this domain genuinely disagree,
what is irreversible here, and what must never be asserted.

## Pick the tier first, because this is the decision that matters

Packs come in three tiers and compose (SKILL.md step 0). Before writing anything, decide where each
claim belongs, using one test:

> **Would this claim change if the industry changed?**

- **No, it's true of any business** → `packs/general/`. ⚠️ **The general tier takes lenses and
  guardrails only.** See `packs/general/common-lenses.md`. It has no fault lines and no decision
  classes, because a fault line is a tension a *particular domain* argues about. If your claim is
  general enough for this tier, it is too general to be a fault line, and the sections below mostly
  do not apply. **Do not write a general-tier pack from this template.**
- **It's true of this *shape* of business** → `packs/sector/`, e.g. any owner-operated professional
  practice, regardless of profession. Full pack; use this template.
- **It would change if the profession changed** → `packs/vertical/`: the filing calendar, the
  regulatory regime, the licence. Full pack; use this template.

**This test is the whole point of the tiering, and getting it wrong is the failure mode that
motivated it.** A general claim written into a vertical pack, say "owner-operator practices have no
sale value", reads as domain expertise, gets inherited without scrutiny, and is much harder to
argue with than the same claim stated plainly at the tier where it belongs. **When in doubt, push it
up a tier.** A vertical pack that turns out small is a correct vertical pack.

**Load this pack when:** <one line naming the decision classes and the kind of user.>
**Do not load it when:** <the adjacent cases it will mislead, usually the neighbouring domain, or
the same domain at a very different size.>

## Marking contested claims

Where a claim is plausible but unvalidated, say so inline and say what is uncertain:

> ⚠️ **Contested, do not assert.** <the stronger version of the claim> is **plausible and
> unvalidated**. <what varies, and why>. A lens may raise it as a **question**; no lens may report
> it as a finding about the user's business.

A pack full of confident claims nobody has checked is worse than a smaller honest one. It produces
panels that are specific, fluent and wrong, which is the hardest kind of wrong for a user to catch.

## 1. Decision classes covered
Three to six recognisable decisions, each in the user's own words, not the vendor's.
- **<Class name>:** "<how the user would actually phrase it>"

## 2. Fault lines: where this field genuinely splits
The heart of the pack. Two to four tensions that real practitioners argue about, each stated as
two positions that are both defensible. These are what make a panel non-theatrical here; the
lens roster in §3 exists to staff them.
- **<Fault line>:** <position A, at strength> ⟷ <position B, at strength>

## 3. Lens roster
Five to nine lenses, each mapped to a fault line it staffs. A lens that staffs no fault line
does not belong in the pack.
- **<Lens name>.** *Remit:* <one line>. *Argues for:* <its standing position>.
  *Bias:* <where it is reliably wrong>. *Crux question:* <the one question that would flip it>.

## 4. Scout triples
For each decision class, the three most distant lenses to probe with (SKILL.md step 4a). Pick
for maximum worldview distance, not coverage. Note the split that would justify convening.
- **<Class>:** <Lens> · <Lens> · <Lens>. *Convene if:* <the disagreement to watch for>.

## 5. Reversibility map: one-way doors in this field
Step 4c overrides the gate for hard-to-reverse calls, so the pack must say what that means
here. Anything listed is convened regardless of scout convergence.
- **One-way:** <…>. *Why it doesn't undo:* <…>
- **Two-way (gate freely):** <…>

## 6. Calibration questions
The 2–3 highest-leverage unknowns for this vertical (step 2). Each must be answerable in a
sentence and must actually change the recommendation.
- <question>. *Changes:* <what it moves>.

## 7. Domain guardrails: what no lens may assert
Hard limits on the panel's mouth. A pack that lets lenses invent authority in a regulated field
is a liability, not a feature.
- Never state <specific rules, thresholds, filing dates, rates, case law> as fact. Frame as
  "confirm with <the authority>" and treat the answer as an input the panel doesn't have.
- Never present the output as <the regulated advice this field is licensed to give>.
- <vertical-specific limits>

## 8. What "the panel beat the baseline" usually looks like here
Calibration for step 9, so the verdict stays honest instead of flattering. Name the verdict
this vertical most often earns, and the trap that manufactures a false one.
- *Most common honest verdict:* <…>, *because:* <…>
- *The flattery trap:* <the difference a run is tempted to manufacture here>.

## 9. Anti-patterns
- Lenses that agree by construction in this field (and so must not be seated together).
- The consensus this vertical falls into by default, and what actually breaks it.
