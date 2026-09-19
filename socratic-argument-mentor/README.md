# Socratic Argument Mentor

A skill that turns an LLM into a rigorous examiner of your own written arguments.

You paste a text defending an idea you hold. The model reconstructs it in standard form, **exposes the premises you never wrote down but the argument needs**, diagnoses the weaknesses by type, mounts the strongest objections it can build, and closes by asking you to recalibrate your own confidence against the number you gave at the start.

It is designed to do the opposite of what chat models do by default: it does not agree with you, it does not hand you a polished version of your text, and it does not let you advance until you have answered.

## Why this exists

Ask a model for feedback on an argument and you usually get encouragement with a few hedged suggestions. That is pleasant and useless. The failure is not the model's politeness — it is that a single response cannot do what examination requires: tracking which premises you have already conceded, noticing that your third defense supplied a reason *against* your own thesis, or spotting that you have used yourself as the sample four times.

This skill is mostly a **state-tracking protocol**. Premises get labels and keep them. New premises introduced mid-defense get numbered and examined rather than absorbed. Retired premises that reappear get named. Most of the value arrives in round four, from patterns invisible inside any single turn.

## What is in here

```
socratic-argument-mentor/             # repo
├── README.md
├── LICENSE
└── skills/
    └── socratic-argument-mentor/     # the skill itself
        ├── SKILL.md
        ├── references/
        │   ├── diagnostic-patterns.md   # 12 defensive moves and how to name them
        │   ├── objection-craft.md       # building objections that land; falsifiable tests
        │   └── session-example.md       # a real annotated session, start to finish
        └── assets/
            ├── portable-prompt.md       # copy-paste prompt for any LLM (English)
            └── portable-prompt.es.md    # same, in Spanish
```


## How to use it

**With the skills CLI** (works across Claude Code, Codex, OpenCode, Cursor, Gemini CLI and others):

```bash
npx skills add <your-github-user>/socratic-argument-mentor
```

**Manually.** Copy `skills/socratic-argument-mentor/` into your agent's skills directory — `~/.claude/skills/`, `~/.codex/skills/`, `~/.config/opencode/skills/`, `~/.gemini/antigravity/skills/`, or `~/.agents/skills/` for anything following the Agent Skills standard. Restart the session so the agent re-scans.

Then share your text and ask for a critique — the description is written to trigger on the usual phrasings ("poke holes in this", "stress-test this", "what do you think of this argument").

**As a prompt in any model.** Copy everything between the `===` lines in `assets/portable-prompt.md` (or the Spanish version) and paste it as your first message, with your text at the bottom. Works in ChatGPT, Gemini, Claude, or anything with a custom-instructions field.

The model responds in whatever language you write in.

## The protocol

| Phase | What happens |
|---|---|
| **0 — Calibration** | Your central claim in one sentence. How confident are you, 0–100%? The number is stored for the end. |
| **1 — Reconstruction** | P1, P2… explicit premises. **PI1, PI2… implicit ones.** C, the conclusion. The structure of the inference. Is a prediction or a proposal being made? |
| **2 — Diagnosis** | Every problem typed — Truth, Validity, Ambiguity, Strength, Omission — and ordered by how much of the conclusion collapses if it fails. |
| **3 — Refutation** | The two or three gravest weaknesses only. Each gets the strongest objection available, **what survives** of the premise, and a question you have to answer yourself. |
| **4 — Iteration** | Your defense examined with the same rigor. Dodges named. New premises labeled. Inversions distinguished from weakenings. Repeat as needed. |
| **5 — Close** | Five questions, one at a time, ending with: what would you have to observe to change your mind entirely? |

A quick mode exists for short texts: one message, the load-bearing implicit premises, the single gravest weakness, one question.

## Design decisions worth knowing

**It concedes.** When your defense works, the objection is retracted explicitly. An examiner who never grants anything has no credibility by round four, and you stop listening.

**It gives you back a narrower premise.** Every objection comes with the qualified version that would still be defensible. Criticism that only subtracts produces defensiveness; criticism that hands you a better argument produces thinking.

**It refuses to run the phases in one message.** The waiting is where the work happens. This is deliberately slower than a feedback request.

**It won't examine everything.** Writing about grief, a diagnosis, or a decision made under real distress is not a thesis to be tested. The skill checks for this before starting and responds as a person instead.

**It asks for a falsifiable test where it can.** When a claim rests on introspection — "I think I've gotten worse at this" — the most useful output is not a concession but an experiment with the right baseline.

## Where it came from

The protocol is a generalization of one real session, preserved in `references/session-example.md`. The argument under examination was that LLM use will create demand for "gyms for the mind". It ended somewhere better than it started, and not where its author expected: what delegation endangers is less the capacity to produce than the capacity to **evaluate what was produced** — and that capacity was acquired by producing.

Confidence in the original thesis went from 90% to 60% over the session. The skill is built to reproduce that kind of movement, not to reproduce that conclusion.

## Credit where it is due

The diagnostic vocabulary draws on standard informal logic. Specific ideas referenced in the skill and its examples include Bjork on desirable difficulties, Rozenblit and Keil on the illusion of explanatory depth, Bainbridge's *Ironies of Automation*, and the cognitive-training transfer literature (Thorndike and Woodworth; Sala and Gobet; Simons et al.). The skill instructs the model never to invent a citation, and to state uncertainty about a reference rather than manufacture precision.

## License

MIT. Use it, fork it, improve it. If you build a better version of the Phase 4 pattern catalogue, that is the part most worth improving.
