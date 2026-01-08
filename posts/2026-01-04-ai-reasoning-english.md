# AI Runaway Is Not a Model Problem — It’s a Collapse of System Boundaries

## Preface

When I first encountered ChatGPT in 2023, I immediately pictured a highly automated life:  
I would speak in the loosest, most casual language, and ChatGPT—like a small personal assistant—would help me think through everything and get everything done. I could just lie in bed, say what I wanted, and it would do it quickly and accurately.

By late 2023, GPT Actions appeared. I began building my own agents: reading emails, sending emails, summarizing replies, and assisting with scheduling. I even tried to let it arrange talk times for each speaker. But the problem surfaced almost immediately—it started making things up. It made a pile of basic, commonsense mistakes. The experience was unmistakable: I was not using an intelligent tool; I was constantly correcting an apprentice who kept producing ridiculous errors. Was I patiently teaching a child, or was “advanced AI” helping me complete tasks? In the end, I had to do the scheduling myself. From that moment on, I lost the most basic trust in AI.

In 2025, model capability improved dramatically. The obvious hallucinations of the past were greatly reduced. Even so, I still did not dare to let it send emails on my behalf.  
For **isolated, low-risk tasks**, it is already usable; but once you enter **long workflows and large systems**, the issue becomes fundamental:  
If it makes a mistake, who pays the cost?  
If an error spreads quietly, who notices first?

This problem does not automatically disappear just because the model becomes stronger.

---

## A System Being Accelerated Without Its Constraints Being Finished

Today’s AI development looks more like a racing competition with a gas pedal but no brakes.

Ever since ChatGPT first landed, there have been extensive discussions about safety mechanisms, alignment research, and systemic risks. Yet these topics have consistently failed to receive the same design priority as speed, scale, and efficiency. In a competitive environment, investing time in “seatbelts” and “braking systems” rarely yields an immediate boost on performance metrics; meanwhile, the engine and the fuel tank still have massive room to grow. Any time spent on constraints and safety can cause a team to fall behind competitors who focus exclusively on acceleration.

This incentive structure naturally forms a prisoner’s dilemma, pushing the entire industry to keep accelerating before safety and constraints have been properly designed. In theory, once engines approach their limit, attention should shift to braking. In reality, as long as no sufficiently severe accident has occurred, the inertia is unlikely to stop on its own.

From an investment perspective, this trend is amplified further. Any narrative attached to AI keeps getting rewarded. People’s expectations rely heavily on scaling laws, while intentionally or unintentionally ignoring ceilings such as data depletion, energy costs, and the upper bounds of system complexity. Ideas like “AI training AI” and “distillation reduces cost” get repeatedly reinforced, while the unpredictability of AI systems, cascading failures, and amplification effects rarely receive equally serious treatment.

In academic research, focusing on model performance, benchmarks, and chain-of-thought is not inherently wrong. The real shift happens during dissemination: when “showing a few more reasoning steps” gets simplified and packaged as evidence of being “closer to human thinking,” the stability, reproducibility, failure modes, and verifiability of that reasoning are quietly pushed aside.

In engineering practice, relying on the “high-concurrency” capability enabled by transformer architectures, systems have begun to absorb large-scale real-world data in an almost unconstrained way. Meanwhile, LLMs have been embedded into agent systems with persistent state, environmental sensing, and action selection—using language-based reasoning to take over decision-making and workflow evolution. This gets packaged as a “new paradigm” and rapidly integrated into various engineering stacks.

At the same time, existing theories, methods, and engineering experience are prematurely treated as “obsolete,” as if we could bypass historical accumulation and jump straight into a paradigm replacement—for example, imagining an LLM as an “operating system,” letting users accomplish everything through conversation, replacing traditional UI and interaction paradigms.

In this narrative, success cases are repeatedly amplified and future capabilities continuously promised, while failures rarely enter public view—let alone systematic analyses of failure mechanisms.

More concerning is a long-standing but rarely named assumption: **linguistic centralism**—treating language ability as a meta-ability, and then building cognition, reasoning, planning, and action uniformly on top of language.

Because humans rely heavily on language for collaboration, reflection, and creation, once AI learns to talk to us in human language, people naturally infer that it must also possess understanding, judgment, and creativity—as if the peak of intelligence is simply “speaking like us.” This inference hides a dangerous false premise: **human language can carry and replace every capability.**

But human language is only a carrier, not cognition itself.

Being able to tell a story is not the same as understanding the story;  
Speaking fluently is not the same as reasoning stably—and certainly does not mean taking responsibility for the conclusions it generates.

These technical assumptions, commercial incentives, and social anxieties combine and rapidly evolve into a rushed “AI transformation movement.” Before AI has been clearly defined—what it is, what it is suitable for, and which scenarios it should not be used in—many teams are already being required to force AI into their workflows as a “mandatory productivity upgrade,” while responsibility assignment for failures, reliability checks, and exit mechanisms have not been built in parallel. The tension between top-down pressure and bottom-up infeasibility distorts what AI actually becomes inside organizations: its form, its function, and what people expect from it.

Society as a whole thus enters a contradictory state: hope mixed with fear, excitement drifting into loss of control.

In public discourse, some even take the opportunity to declare that children in the future will not need to learn programming because it will inevitably be replaced. This sounds forward-looking, but it avoids the key issue: the real risk is not whether AI will “replace people,” but whether we are willing—especially in domains with zero tolerance for failure—to embed a black-box system that can fabricate, cannot localize errors, and cannot take responsibility.

---

## A Cold Look: What Is an LLM, What Did It Create, and Where Do Its Abilities Come From?

From a technical origin perspective, the attention mechanism that mainstream LLMs rely on today was not originally designed for “conversation” or “general intelligence.” It was first systematized in machine translation, with a core role: explicitly modeling correspondences within a sequence and across sequences.

Under an autoregressive training objective and at massive data scale, this mechanism was incorporated into language-model systems, and the model as a whole gradually exhibited another stable and efficient capability: **semantic completion**.

In this sense, what LLMs do has never fundamentally changed. At the core there are only two things:
- **Translation** (building mappings between different symbol systems), and
- **Completion** (continuing patterns and structures given context).

Translation reduces friction between language systems. Completion allows the model to continue structure, semantics, and form within context. Together, they produce an appearance of “reasoning-like” and “near-general” capability—even while hallucination remains a persistent, non-negligible part of the picture.

The first truly disruptive capability indeed comes from translation. LLMs translate natural language into executable text, allowing systems to be controlled, have state modified, be automated, and even run commands through natural language. This is not that natural language “evolved” execution power; rather, execution power already existed in programming languages and was migrated through translation.

The key is not whether it can be done, but that the translation cost has been driven down—almost to zero. Once isolation between language systems is broken, capabilities previously sealed inside engineering systems begin to circulate, recombine, and become visible externally.

The rise of agents is the natural spillover of this process:
**requirements → language → code → execution**, compressed into a single system for the first time. Therefore, what LLMs hit first is not “creative labor,” but translation-heavy work; and low-end software development is, in essence, also translation—mapping vague human intentions into formal, executable instructions.

For the public that has never touched programming or formal languages, this shift creates a huge perceptual shock.

What they see is not “program capability being translated into natural language,” but everyday language suddenly gaining execution power: commands get understood, intentions get carried out, results get produced directly—without explicit code, intermediate systems, or professional training.

This feels deeply counterintuitive. It is easy to misread as “silicon-based life awakening,” as if an intelligence outside human design is spontaneously evolving. In reality, execution power has always existed; it was simply encapsulated within engineering systems, evolving gradually and invisibly to outsiders. The rupture between long-term invisible accumulation and sudden visible capability is what creates the collective shock of the present moment.

The second shocking capability comes from completion. By learning from massive text corpora, LLMs compress huge amounts of knowledge and experience into parameter space, making them far more efficient than humans at “fill-in-the-blank” tasks where humans would otherwise retrieve information piece by piece. This does not eliminate errors, but it sharply reduces the time cost of trial and error.

Completion does not give language new properties; it amplifies functions language already had.

Where does logic come from? Natural language already carries structured logic.  
Where does generality come from? Natural language is already a general communication tool.

Conditionals, causality, quantification, reference, recursion—these are already embedded in linguistic structure. Completion merely continues these structures. That is why LLMs appear “general,” “plannable,” and “reasoning-capable” at the language level.

But this ability is strictly constrained by three things:
- the expressive boundaries of language itself,
- structures that existed in the training distribution, and
- constraints that can be maintained within the context window.

There is no reasoning system independent of language, and no guarantee that conclusions hold beyond semantics. When this language-level continuation is mistaken for transferable, auditable, guaranteed reasoning ability, hallucination emerges.

At this point, the picture becomes clear:
LLM capabilities do “come from language,” but more precisely—

LLMs do not create these capabilities. They simply open a tunnel between different language systems, bringing abilities that already existed in other systems into the visible range of agents who interact through only a single language.

Much of today’s risk stems from exactly this: while language enables capability import, it also blurs the once-clear boundaries between language systems—so safety, responsibility, and verification problems are no longer confined locally, but diffuse across the entire system.

---

## But This Path Is Not Wrong

Despite widespread misunderstandings around language and intelligence, the technical direction itself has not gone astray. Language and text have existed for thousands—perhaps tens of thousands—of years as tools of human civilization, and their effectiveness has been repeatedly validated through evolution and history.

Text and symbols can carry formal logic and support mathematical reasoning. They form the basis of communication and collaboration, enabling legal texts and institutional design. The organization of society, the continuation of species, the rise and fall of civilizations—none of these have ever been separable from language as a carrier.

But language itself is not the “source of intelligence.” It is more like a **formal carrier**, like paper or notation. What truly does the work is the system behind it—running on logic, constraints, and rules.

Within humans, this is also true. The language center and the logic-control center are not the same mechanism. Human behavior is not driven by language alone; it is a tightly coupled, layered cooperative system. We often believe we “think in language,” but a more accurate statement is:

**Our thinking process happens to be expressible in language.**

Different languages naturally have different functions and limits, and this is especially clear in mathematics. A well-designed symbol system not only improves reasoning efficiency—it can directly expose the essence of a problem.

Formally, mathematical reasoning and proof are fundamentally a process of **variable substitution and structural matching**. The quality of a notation system directly determines whether that matching is stable, composable, and transferable.

Take calculus as an example. Newton’s dot notation is extremely intuitive for expressing rates of change, but once complex substitutions or nested structures appear, the notation no longer preserves enough information and the reasoning can easily go off the rails. Leibniz notation, by explicitly preserving variable dependencies, is verbose—but far more robust for structural transfer and compositional reasoning.

Consider the chain rule:
Let $$f(x) = g(h(x)) $$.  
If we use only prime notation $$f', g', h' $$, we must **introduce an external rule**:
$$
f'(x) = g'(h(x)) \cdot h'(x).
$$
This rule does not naturally emerge from the notation itself; it relies on memory and convention.

In Leibniz notation, the reasoning process is directly reflected in the symbol shape:
$$
\frac{df}{dx}
= \frac{df}{dh} \cdot \frac{dh}{dx}
= \frac{dg}{dh} \cdot \frac{dh}{dx}
= g'(h(x)) \cdot h'(x).
$$
Here, **variable substitution itself becomes the system’s mode of evolution**. The conclusion is not “derived by applying a rule,” but appears formally through **structural matching**.

In this sense, a mathematical proof is not “describing reasoning with language,” but rather letting structure unfold inside a language expressive enough to expose it. Formal systems like Lean are designed along precisely this line: proof is not narrative; it is step-by-step structural alignment.

A good language can directly reveal the trajectory of a system’s evolution. In extreme cases, it becomes difficult to distinguish whether the system is evolving—or whether the language itself *is* the system.

This is not an aesthetic difference; it is a difference in system operability.

Therefore, language is always just the symbolic expression layer of a system. For different needs, language can be strongly typed with explicit dependencies; it can be loosely constrained for flexibility; it can carry emotion; it can serve process description and execution control. There is no “universal language” that optimizes all dimensions at once.

More fundamentally, language’s real role is to **define, operate, and even run systems** in symbolic form—projecting system capabilities into a layer that can be understood and controlled. The question is never whether language is “powerful enough,” but whether we clearly understand:

**Which languages are suitable for operating which systems, and what roles each system should be responsible for.**

---

## The Problem Is Not the Model — It’s the Collapse of System Boundaries

Most failures around LLMs today do not come from whether the model is “smart enough,” but from an assumption that seems reasonable yet is fundamentally wrong in engineering:

If a system can express intent in natural language, then natural language can directly take over execution.

In any reliable complex system, there are at least three essentially different layers:

- **Language layer**  
  Used to express intent, assumptions, and plans; it allows uncertainty, ambiguity, revision, and error. Natural language, mathematical formal language, and programming language all belong here—they answer “what to say,” not “what to do.”

- **Reasoning / checking layer**  
  Sits between abstract expression and real execution, imposing constraints: syntax checks, type consistency, condition validation, error localization, and auditability. Humans ask for clarification when instructions are ambiguous; compilers reject programs with invalid syntax or types. The job of this layer is to block errors from sinking downward.

- **Execution layer**  
  Irreversible, with external side effects, and naturally tied to responsibility. Once triggered, an error is no longer informational noise; it becomes a real-world event.

These layers differ fundamentally in reliability, reversibility, and failure cost; therefore, they must not be carried by the same mechanism.

Yet many so-called “agent systems” today do exactly the opposite: using the least stable, least auditable LLM black box, passing the language layer through weak syntax, weak constraints, and sparse filters, and directly connecting it to the execution layer—the layer where failure is least acceptable and rollback is least possible.

The problem is not that LLMs hallucinate. Hallucination is an intrinsic property of a language-completion machine under weak constraints. The real failure is that system designers allow hallucination to enter a layer where it does not belong.

What is natural language good for?  
Proposing options, drafting content, organizing information, exploring possibilities, performing open-ended search and summarization. It is good at generating “candidates,” not triggering “consequences.”

Natural language is not made for operating systems. Its weak syntax means: even if a sentence is perfectly valid in grammar and context, it still cannot reliably carry state mutation, resource scheduling, or side-effectful actions. Once language crosses its capability boundary, errors are no longer probabilistic; they become structurally inevitable.

Therefore, the proper place of an LLM based on natural language should never be an “automatic executor.” It should inherit natural language’s generality and expressive power for translation, proposal generation, heuristic search, and information organization—but it should not enter the execution layer, and it should not be responsible for final judgment, verification, or audit.

Natural language itself does not scale. Human societies have already proven—through rumor, distortion, and “three men make a tiger”—that without formal constraints, reasoning checks, and responsibility allocation, any system amplified by language will systematically drift away from truth.

Law can operate at scale not because language itself is reliable, but because it uses restricted forms of expression and is jointly backstopped by interpretive systems and human judges. Mathematical proof is trustworthy because formal systems exist and applicability is strictly bounded.

Language is never self-sufficient. It is trusted only when it is constrained to its proper role and backstopped by external constraint and verification mechanisms.

When boundaries are clear, failure is controllable.  
When boundaries blur, stronger models only amplify risk.

At this point, so-called “intelligence” has become a system design and architecture problem.

---

## Conclusion

Can we step outside our obsession with language itself—our superstition about LLMs—and instead confront system architecture, constraints, and audit?

Today’s loss of control does not come from choosing the wrong road, but from oversimplifying what a large system is: we keep reinforcing a single component—engines and throttles—while refusing to face a basic fact:

**Brakes and seatbelts are not optional features to be added after performance optimization;  
they are prerequisites for a system to be allowed on the road at all.**

As for what the brakes and seatbelts actually are—let that be for the next piece.

