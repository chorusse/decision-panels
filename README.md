# Decision Panels

**A Claude skill that convenes a panel of expert advisors on a hard decision, and tells you when the
panel wasn't worth convening.**

Free. Runs on your own Claude, or on Codex. Nothing leaves your chat.

---

## What makes this one different

Most multi-advisor tools have the same unstated problem: **they can't tell you when they didn't help.**
The research on multi-agent deliberation is genuinely deflationary. For a lot of decisions, five
advisors arrive exactly where one good one already was, at five times the cost. Every tool in this
category quietly hopes you won't notice.

Decision Panels measures it. On every run it:

1. Takes a **solo baseline** (one strong single-pass answer) *before* the panel is convened,
2. Hides that baseline from the panel so the comparison means something,
3. **Probes cheaply before spending a panel**: three maximally-distant lenses give a one-line read each;
   if they agree on both the call *and* the crux, it tells you a panel is unlikely to change anything and
   stops there (unless the decision is hard to reverse, where it always convenes),
4. Otherwise convenes 5–7 advisors, **seated by who actually disagreed**, hears them independently,
   keeps the disagreement,
5. Has them **cross-examine each other blind**, with answers stripped of authorship and relabelled A–E, so
   arguments are judged on merit rather than on which advisor said them,
6. And then **reports whether the panel actually beat the baseline**, including the runs where it
   didn't, in those words: *"The panel did not beat the single answer here. You could have asked once."*

That last step is the product. A panel that can't tell you when it was unnecessary isn't one you can
trust when it says it was.

## Install

**Claude Code**

```bash
git clone https://github.com/chorusse/decision-panels ~/.claude/skills/decision-panels
```

Or drop the `decision-panels/` folder into `~/.claude/skills/`. Restart Claude Code; it will pick the
skill up automatically.

**Codex**

```bash
git clone https://github.com/chorusse/decision-panels ~/.codex/skills/decision-panels
```

Codex picks it up on the next session. It plays the panelists in one conversation unless you ask it
to use subagents.

**Claude Desktop / claude.ai**: add the contents of `SKILL.md` as a Project instruction or custom
skill, depending on what your plan exposes.

## Use

Just describe the decision:

- "Should I raise prices or add a cheaper tier?"
- "Help me decide whether to hire or contract this out."
- "I'm torn between these two positioning angles."
- "Pressure-test this decision for me."

It will ask you **2–3 calibrating questions first**, the ones whose answers would actually change the
recommendation. That step is not filler; a panel run on guessed inputs produces a guessed answer dressed
up as rigor. Answer them in a sentence each.

You get back a **decision brief**: the recommendation with a stated confidence, the panel's real
disagreement, what the blind review round caught (including the thing *every* advisor missed), the
strongest case *against* the recommendation, what would change the call, and the baseline comparison.

## What's in here

| File | What it is |
|---|---|
| `SKILL.md` | The method. 10 steps, in order, including the one where it declines to run. This is the actual asset. |
| `references/panel-lenses.md` | The advisor-lens library to draw panels from |
| `references/decision-brief-template.md` | The output format, built to be forwarded |
| `examples/example-pricing-decision.md` | A worked run end to end |
| `references/verdict-rubric.md` | How the step-9 verdict is chosen: four gates, the swap test, ties go down |
| `references/pack-template.md` | The format for a pack that adapts the panel to one field |
| `references/packs/` | One general tier (common lenses) and one sector pack (owner-operated professional services). No vertical pack is published yet; writing one for your own field is the intended use |

## Honesty notes

- **We publish our own comparison.** See [`proof/head-to-head.md`](proof/head-to-head.md) for
  Decision Panels vs. LLM Council (1,271★) vs. vanilla Claude, including a section on where the
  competitor is genuinely better than us, and a pre-registered protocol for the empirical results we
  have *not* yet produced.
- **Every example says where it came from.** A worked example in this repo states in its opening
  line whether it was captured from a live run or authored to the method. Both are useful and they
  are not the same evidence, and a tool whose whole claim is that it reports its own failures does
  not get to be vague about which one you are reading. Today the example here is authored.
- **This is a text file.** There is no magic in it and no lock-in. Read the method, take what's useful,
  fork it. The value is the sequencing, and the sequencing is right there for you to check.

---

*Decision Panels, by [Chorusse](https://chorusse.com). Many expert voices in, the disagreement kept
honest, one clear call out.*

*Built by Daniel A. Bauer · [linkedin.com/in/danbauer](https://www.linkedin.com/in/danbauer)*
