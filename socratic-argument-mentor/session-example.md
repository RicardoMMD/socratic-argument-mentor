# Annotated session: "cognitive gyms"

A real session, condensed and translated from Spanish. The author's turns are paraphrased; the mentor's moves are shown in the form they were actually delivered. Annotations in `>` blocks explain what each move is doing and why.

This is here to show the protocol in motion — particularly the parts that only work across rounds and cannot be demonstrated in a single exchange.

---

## The text under examination

> Past generations didn't need gyms the way we do, partly because work demanded far more physical activity. Technology, infrastructure and automation have made work increasingly sedentary, which damaged public health and drove the popularity of gyms as places to compensate.
>
> Something similar is happening now with cognitive effort. Using LLMs means delegating part of our thinking to a synthetic entity. But we need to exercise our cognitive capacities the way we exercise our bodies — otherwise we lose problem-solving ability, tire mentally faster, and struggle with complex thought. In short, we get dumber.
>
> So we can expect the emergence of gyms for the mind: places to do the cognitive work we used to do daily — writing code, solving math problems, building arguments without immediately delegating to an AI. And just as physical gyms developed training methods, mental gyms could develop methods to strengthen our capacities.
>
> Maybe the future isn't stopping AI use, but learning to train what we've chosen to stop doing.

---

## Phase 0

**Mentor:** Your text contains several claims: a historical one, a causal one, and a prospective one. I'm treating this as the central claim, and you can reformulate if it's wrong:

> Delegating cognitive effort to LLMs weakens our mental capacities the way sedentary work weakened the body, and this will make deliberate cognitive training spaces necessary.

How confident are you, 0–100%?

**Author:** 90%. It's more complex than what I laid out, but it's going in the right direction.

> **Move: extract and offer the central claim rather than assuming it.** Three claims of different genres were bundled together and needed separating before anything else.
>
> **Move: store the qualification, say nothing.** "It's more complex than what I laid out" is the most diagnostic sentence in this phase — it usually means confidence sits on an unwritten argument. Saved for Phase 5, where it paid off.

---

## Phase 1

The mentor labeled P1–P7, C1 (intermediate: "we get dumber") and C, then listed six implicit premises. The ones that decided the whole conversation:

- **PI1:** the body/mind analogy holds in the relevant respect — cognition atrophies from disuse like muscle.
- **PI2:** the delegated effort is not replaced by equivalent effort; the total goes down rather than being redistributed.
- **PI3:** coding, math and argument exercise **general** capacities, not just task-specific ones.
- **PI4:** deliberate cognitive training **transfers** to general capacities.
- **PI5:** people will perceive the loss and want to compensate, so demand will exist.

Structure: an argument **by analogy**, resting on an inference to the best explanation about the past and a causal claim about the present, yielding a prediction.

**Mentor:** There's an ambiguity in C worth fixing. "We can expect the emergence" reads either as a **prediction** (this will happen) or a **proposal** (this should exist). Which do you mean? And is this reconstruction faithful?

**Author:** C is a prediction.

> **Move: the implicit premises are the whole phase.** None of PI1–PI5 appear in the text, and four of them were where the argument eventually failed. Two of them the author later retired himself.
>
> **Move: disambiguate the modal status.** "Prediction" raised the bar immediately — a prediction has to explain why it will happen, not only why it would be good. Had this gone unasked, two rounds would have been spent arguing past each other.

---

## Phase 2

Six problems, ordered by severity. The top three:

1. **PI4 — Truth.** The gravest, because the prediction depends on it. Evidence on cognitive training is mostly negative on transfer: Simons et al. (2016); the Lumosity/FTC settlement (2016). Training a task improves that task.
2. **PI2 — Truth / Omission.** Assumes delegation reduces total effort rather than redistributing it. Long lineage of the same alarm: Socrates on writing in the *Phaedrus*, calculators, Clark and Chalmers on extended mind. Current evidence divided.
3. **P7 / PI1 / PI3 — Ambiguity.** "Cognitive capacities" covers specific skills, accumulated knowledge, and general capacities. "Use it or lose it" is well supported for the first (GPS and spatial memory, Dahmani and Bohbot 2020; manual flying skill erosion, Bainbridge 1983) and weak for the third. "We get dumber" conflates them.

> **Move: name the load-bearing premise explicitly.** Saying "this is the gravest *because the prediction depends on it*" tells the author where to spend effort.
>
> **Move: name the surviving premise.** The historical section (P1–P3) was diagnosed as only mildly weak and protected by his own "partly" — conceding this early bought credibility for pressing harder later.

---

## Phase 3 and 4: where the argument actually moved

### The author conceded PI4 — and substituted a new premise

**Author:** Right, I was always thinking about specific skills like programming. But total dependence on the machine costs a company extra: they pay for the developer *plus* tokens.

> **Pattern: concession with substitution** (`diagnostic-patterns.md` §1). The concession was clean and defused the objection. But a new premise arrived wrapped in it, unexamined. The mentor labeled it **PI7** — "the cost of dependence incentivizes preserving the unaided skill" — and evaluated it separately. This labeling is what made the next two rounds possible.

### His defense inverted PI7 rather than weakening it

**Author:** On A vs B — I've realized something. My programming used to be junior-mid, and I'm paid as junior-mid. With LLMs my output is senior. The company pays junior-mid plus tokens and gets senior results.

**Mentor:** This is the best idea you've contributed, and not for the reason you think. You're right that there's no contradiction — you're an arbitrage. But look at the consequence: **the company has no incentive to preserve your unaided skill. It has the opposite one.** PI7 doesn't weaken here; it inverts.

And there's a condition that does survive, which is stronger: your arbitrage works because you have real junior-mid competence. Someone with no base gets code they cannot evaluate and doesn't know it. What makes you an arbitrage is not your capacity to **produce** but your capacity to **judge**.

> **Pattern: premise inversion** (§3). Distinguishing inversion from weakening mattered: a weakened premise can be narrowed, an inverted one has to be withdrawn.
>
> **Move: extract the surviving condition.** The thesis that emerged here — that what delegation endangers is the capacity to *evaluate*, and that it was acquired by producing — was stronger than anything in the original text, and the author had supplied it himself without noticing.

### Counting the pattern

Across three rounds, every example the author offered in defense of his thesis was an instance of redistribution: connection pooling, Redis, Traefik, error handling, metadata documentation, and finally token efficiency.

**Mentor:** Notice what you just did. This is the third time that defending your thesis produced an example of redistribution.

> **Pattern: support that is actually the objection** (§2). No argument was needed on top of the count. This move is only available to a mentor tracking state across turns, and it was the single most efficient thing in the session.

### A retired premise came back

**Author:** My gym should train the correct thing, but also the difficult thing. I feel there's an intrinsic benefit in making the brain do hard tasks.

**Mentor:** I have to name something. **You're reintroducing PI4, which you retired two rounds ago.** "Intrinsic benefit in doing hard things" is a general-transfer claim, and you reintroduce it with the word "feel" and no new reasons.

There's a legitimate version nearby: Bjork's **desirable difficulties** — retrieval practice, spacing, interleaving — produce better learning than fluent practice. But those are specific, and they work **within the trained domain**. Difficulty is not the active ingredient; reconstruction without support is.

> **Pattern: attachment** (§9), nominated with a specific candidate rather than as an open question. In Phase 5 the author accepted it and added something better: he still held the conclusion, but no longer for the same reasons. That is revision, not attachment — and the mentor said so, while pointing out the new reasons were still unwritten.

### A better mechanism appeared

**Author:** Maybe I'm just more impatient when I write. I write with less subtlety because I know the LLM will polish it.

**Mentor:** This is your best answer of the round, and I don't think you noticed why. Your text claims **atrophy** — you stop using a capacity and it degrades, like muscle. What you just described is **anticipated offloading**: the capacity may be intact, and what changed is the decision to invoke it.

Three reasons the distinction matters: it's immediately reversible, it's behavioural (responds to rules, not training), and it doesn't need the muscle analogy — your weakest point. It's also **falsifiable**: write three genuinely difficult texts with no AI at any stage, and compare them against something you wrote in 2022, not against what a model would produce today.

> **Pattern: mechanism shift** (§6), named as progress rather than inconsistency. The conclusion survived; the causal story improved.
>
> **Move: propose a falsifiable test.** The author's evidence had been introspective throughout. This converted it into something that could actually be checked, including the correct baseline — the wrong comparison standard was itself a live confound.

### Self as sample, four times

**Author:** Someone starting with LLMs, if they're curious and determined enough, can learn the architecture using the LLM itself — that's how I did it. I investigate why a technology is recommended, review the scripts, understand the logic, and ask about what I don't understand.

**Mentor:** Two problems. The small one: **"if they're curious and determined enough"** does nearly all the work — with that clause the claim approaches "those disposed to learn, learn." The default path is shorter and produces working results; you took the long one. That describes you, not the market.

The large one: everything you listed is **verification, and verifying requires a prior base**. You review those scripts with the eyes of someone who learned to read code first. And there's a documented mechanism: Rozenblit and Keil (2002) on the **illusion of explanatory depth**; Fisher, Goddu and Keil (2015) showing that searching inflates perceived knowledge without increasing it. A fluent LLM explanation has exactly that shape — recognizing that it makes sense feels like understanding.

Your own practice contains the antidote you didn't name: **you ask about what you don't understand**. That presupposes detecting that you don't. That detection is the critical skill, and it's the one fluency degrades.

> **Pattern: the tautological condition** (§8) and **self as sample** (§4), both named in one turn, with the count ("the fourth time you've used yourself as the sample").
>
> **Move: find the antidote inside their own account.** Stronger than an external objection, because it builds from something they already do.

---

## Phase 5

The author said "close". Five questions, one at a time.

Recalibration went from **90% to 60%**. The mentor pushed back on the number:

**Mentor:** I asked for confidence in the **original formulation** — the muscle analogy plus the prediction of gyms — and that's the version you retired two premises from. 60% seems high. Which formulation are you scoring: that one, or the thesis about preserving the capacity to evaluate?

> **Move: audit the recalibration.** A number that doesn't match the concessions is more informative than one that does. It usually means the person is scoring the *reformulated* thesis — which is itself the finding: confidence in the improved argument fell less than confidence in the original, exactly as it should when an argument gains precision by losing scope.

On what moved him, the author named the reconciliation of the A/B contradiction and learning to distinguish understanding from the feeling of understanding.

**Mentor:** Notice your choice: neither of those is an objection that refuted you. They're **distinctions** you didn't have. What moved you wasn't losing a premise, it was gaining an instrument for separating things that were mixed together.

> This is the observation the protocol exists to produce, and it can only be made at the end, with the whole conversation in view.

---

## Where the argument ended

| Piece | Status |
|---|---|
| Loss of general capacities (PI4, PI3) | Retired by the author |
| Effort not redistributed (PI2) | Refuted by his own examples, three times |
| Token cost as incentive (PI7) | **Inverted** by his own arbitrage argument |
| Atrophy as mechanism | Replaced by **anticipated offloading** — falsifiable |
| Gym as space or industry | Reinterpreted as a personal practice |
| Preserving the capacity to **evaluate** | Emerged as the strongest claim, absent from the original text |

And one unresolved tension, stated rather than adjudicated: economically, everything in his analysis points to delegating more; personally, his behaviour points to delegating less. No reconciling reason appeared — which suggests the real claim is about what kind of mind he wants to have. A thesis about values, not a prediction about markets. Possibly the "more complex" idea he said he had in mind at Phase 0.
