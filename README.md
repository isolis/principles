# Principles

*Nacho Solis — [isolis@igso.net](mailto:isolis@igso.net)*

## TL;DR

Most engineering principles die in someone's head. This repository writes them down — argued from experience, structured for teams, and built for the AI agents now writing your code.

---

## Background

Every engineering team has principles. Most of them live in someone's head.

That works fine when the team is small, when the senior engineers are in the room, when institutional memory is intact. It stops working the moment you scale — new hires, new projects, changing team composition. And it stops working entirely when the team includes AI agents that have no access to unwritten knowledge whatsoever.

We are at an inflection point. The shift is not gradual — it is a step
function. An experienced engineer produces perhaps 200 lines of meaningful,
reviewed code per day. A single well-directed agent can easily produce
ten times that, and you can always run more agents. The scarce resource is
no longer the code itself, but the judgment about what the code should do and
how it should behave. And here is the consequence that follows: a bad design
decision that once propagated through one engineer's output now propagates
through ten times the code before anyone notices. Principles are how you encode
that judgment in a form that travels — across teams, across time, across the
human-agent boundary. They are also, increasingly, the guardrails that keep
fast-moving agents inside the lines.

I've been meaning to write these down for a long time. Over my career I've made several versions — for teams, for projects, for myself — but they always lived in documents that didn't travel well, or in my head, which travels even worse. The rise of agents finally made the case undeniable: principles that exist only in people stop working the moment you need a system, rather than a person, to reason from them. That urgency is what pushed this version into the open.

This is my take on what those principles are. Not a committee document — a point of view, argued from experience. Disagree with specific principles, override them for your context, argue back. The goal is to make the reasoning explicit so it can be evaluated and contested, not to hand down commandments from a mountain.

Footnote: I used ten as the multiplier factor for text cadence, but in reality this
could be quite large.

---

## The Principles

The principles are organized into four categories: **Valuable**, **Simple**, **Efficient**, and **Trusted**.

These four aren't arbitrary. They map to the four fundamental questions a system must answer to be worth running: Does it do something real for real people? Can it be understood and changed? Can it be operated without heroics? Can it be relied on? A system that fails any of these questions is not a finished system — it is a liability in progress.

The field manual is in [PRINCIPLES.md](PRINCIPLES.md). What follows is the context behind each principle — the reasoning, the failure modes, and the concrete situations where each one matters.

---

## Why This Matters Now

For most of software's history, principles lived in people. You hired experienced engineers and their judgment came with them. Apprenticeship, code review, and institutional memory were the transmission mechanisms. This still works, and it still matters. But it has a new limitation: agents don't apprentice.

An AI agent generating code, reviewing a pull request, or designing an API has no access to the tacit knowledge your senior engineers carry. It will follow the patterns it finds in your codebase and the reasoning it can infer from your documentation. If your codebase encodes bad patterns and your documentation is thin, your agent will faithfully reproduce both. If your principles are written down, argued well, and consistently applied, an agent can reason from them the same way a new engineer would — and get much further much faster.

This is the practical case for written principles. Not philosophy. Not compliance theater. A forcing function for making implicit expectations explicit, so they can be evaluated, debated, and acted on — by humans and agents alike.

The other side of this is evaluation. As agents generate more code, the question of who reviews it becomes urgent. A team reviewing 200 pull requests a week from human engineers can rely on taste and experience. A team reviewing 2,000 a week, most of them AI-generated, cannot. "Does this feel right?" is not a process. "Does this meet our principles for correctness, resilience, and security?" is.

---

## The Principles, With Examples

### Valuable
*Does the system do something real for real people?*

**Useful.** A correct system solving the wrong problem has failed.

The most expensive failure mode in software isn't buggy code — it's the right code for the wrong problem. A payment system that processes transactions flawlessly for a product nobody buys is not a success. Usefulness is the only metric that actually validates everything else, and it's the one most teams measure last. Define what "useful" means before you build, and check whether you achieved it after you ship.

**Intuitive.** If users need training, redesign the feature.

Documentation is a tax on poor design. Every hour a user spends reading docs to figure out something that should have been obvious is an hour you charged them for your design failure. This applies with equal force to developer-facing interfaces: an SDK that requires reading the source code to use correctly is not an SDK — it is an obstacle. The test is simple: can a new user accomplish the primary workflow without asking for help? If not, the interface isn't done.

**Consistent.** Inconsistency is hidden complexity. Build so the first corner teaches all the others.

When your API uses `created_at` in one resource and `createdAt` in another, you haven't just created a minor annoyance — you've created a class of bugs that appear whenever someone applies what they learned in one place to a different place. Consistency is predictability, and predictability is one of the most underrated properties in software design. Users and developers build mental models. Design for the mental model, not against it.

**Accessible.** If it excludes anyone, that exclusion was a choice. Make it consciously or undo it.

A web application that doesn't work with a screen reader has made it harder for a segment of users to use it. A mobile app that only works in portrait mode has made it harder. A CLI that assumes English has made it harder. An API that requires a browser redirect to authenticate has made it harder for every agent that will ever try to call it. These choices are often made by default — no one deliberately decided to make things harder, they just never thought about who else might be using the system. That's not innocence; it's negligence. Accessibility is about understanding who you are building for — people with different abilities, different devices, different languages, and increasingly, automated systems and agents. If you deliberately decide not to build for agents, that is a valid choice. But it is a choice, and it comes with a cost: you are limiting who and what can use your system. Make that call consciously, not by accident.

**Operable.** An interface that requires human interpretation to automate is broken by design. Surface your capabilities, make operations idempotent, and surface limits before they become errors.

If your API requires a human to read the documentation to build an automation, you have built a human-dependent system. Expose your capabilities in machine-readable form: schemas, valid states, error codes with meanings, available actions. Make operations idempotent so callers can retry safely. Tell the caller about rate limits before the request fails, not in a 429 response after the fact. The benchmark: can an agent with no documentation build a working integration? If not, the interface has work left to do.

**Responsive.** Loading, empty, and error states are always handled — never blank, never frozen.

A blank screen during loading isn't a neutral experience — it's an experience of uncertainty and doubt. An unhanded error state tells the user something broke but not what or what to do next. Every state your interface can be in has to be designed, not discovered. This is especially true for the states that feel rare: the empty list, the slow network, the partial failure. Those states are often where trust is won or lost permanently.

---

### Simple
*Can it be understood and changed?*

**Modular.** A change in one area does not require changes in unrelated areas. Hidden dependencies are hidden debt.

The symptom of a non-modular system is the cascade: you change one thing and three unrelated tests break. You update a data model and four services need to be redeployed. Modularity is not just a design virtue — it is what determines whether your system can be maintained by a team of any size, including a team of agents working in parallel. Hidden dependencies compound; every one you add is a future coordination cost you've committed to paying.

**Reusable.** Don't build what already exists. Duplication is not inefficiency — it is future inconsistency.

Two copies of the same logic will eventually diverge. When they diverge, the system has two different answers to the same question, and neither team knows about the other. Reuse is not about saving keystrokes on initial development — it's about ensuring that when something needs to change, it changes once and the change applies everywhere. Before building, look. Before copying, ask whether you're willing to own two versions of this forever.

**Evolvable.** Breaking changes are a design decision, not an accident.

The systems that outlive their original purpose are the ones that were designed to change. This means versioned APIs that old clients can keep using while new clients adopt new behavior. It means schema migrations that preserve existing data. It means feature flags that let new behavior roll out incrementally. The systems that don't outlive their purpose are the ones where breaking changes accumulate until a rewrite is cheaper than continuity. Breaking things is sometimes right — but it should never be a surprise.

**Testable.** Code you cannot test is code you cannot trust. Structure enables testing; the rest is hope.

Untestable code is not a testing problem — it is a design problem. Code that is deeply coupled, that has hidden side effects, that reaches directly into external systems without abstraction — this code cannot be tested without heroics, which means it won't be tested reliably, which means it will break in ways that are hard to predict and harder to reproduce. Testability is a structural property of the code, not a property of the test suite. If your tests are hard to write, the code needs to change, not the tests.

---

### Efficient
*Can it be operated without heroics?*

**Nimble.** Code is written for the next developer. A change that cannot be shipped quickly is a liability. A security fix that takes weeks to deploy is a vulnerability that stays open for weeks.

A change that cannot be shipped quickly is a liability — and the liability compounds. Nimbleness is two things at once: structural clarity in the code, and operational speed in the delivery pipeline. A codebase where the logic is buried, the configuration is hardcoded, and the coupling is invisible cannot be changed quickly. A security vulnerability you cannot patch in hours is a vulnerability you are living with.

**Iterable.** If adding capabilities requires rewriting what works, that's not iteration — it's rewriting in slow motion.

Iteration means each increment leaves the system better than it found it and doesn't require the next increment to undo it. A system that can only grow through rewrite has a ceiling: eventually, the rewrites cost more than the value they add, and the system stagnates. The antidote is the strangler fig — new capabilities built as additions alongside what exists, gradually taking over until the old can be retired. Each step is safe and reversible. No big bang.

**Observable.** Logs, metrics, and traces are designed in from the start — not added after a production incident. If you cannot tell what the system is doing in production, you do not know what the system is doing.

Observability is not monitoring. Monitoring tells you that something is wrong. Observability tells you why. A system you cannot observe is a system you are flying blind — you know something crashed, but you cannot reconstruct the sequence of events that led there. Building observability in from the start costs a fraction of what it costs to retrofit after the first serious incident. The investment is not in dashboards. Log what matters, measure what changes, trace what flows.

**Inexpensive.** Same outcome, lower cost — always. Never optimize what you haven't measured.

Engineering is full of premature optimization — the instinct to make something fast or cheap before you know where the actual bottleneck is. The cost of premature optimization is not just wasted effort; it is added complexity that has to be maintained whether or not it matters. Measure first. The data will tell you where cost is actually high, and it is almost never where you guessed. When you do optimize, measure again to confirm the change worked. The loop is the discipline.

---

### Trusted
*Can it be relied on?*

**Correct.** A system that silently drops data when it promised not to is incorrect, even if mostly working. Make commitments explicit, measurable, and enforced.

Correctness is not about perfection — it is about keeping the promises you made. A system with a 99.9% SLO that meets its SLO is correct. A system with a "we never lose data" guarantee that occasionally loses data under load is incorrect — even if the data loss rate is very low. The failure is not in the loss rate; it is in the gap between the promise and the reality. Correctness starts with making your commitments explicit, continues with measuring them, and ends with enforcing them when they are about to be violated.

**Resilient.** Failure modes are designed, not discovered. The system degrades predictably — a failure in one component does not cascade. Errors are informative, not cryptic.

The most dangerous failure modes are the ones you discover in production. Consider a service that handles database timeouts by blocking threads waiting for a response. Under sustained load, the thread pool exhausts. Now an unrelated feature — one that doesn't touch the database at all — stops responding, because it can't get a thread. One component's failure has cascaded into a full outage through a dependency nobody modeled. Design your failure modes before this happens: timeouts that fail fast, circuit breakers that open under load, cached fallbacks for degraded states. A service that returns stale data with a staleness header when its database is unavailable is more useful than one that returns 503. Partial failure is not a concession; it is the goal.

**Secure.** Least privilege everywhere. The system fails closed, not open. Security is a requirement, not a feature.

Security added after the fact is security theater. A system where every component has access to everything, where failure modes open permissions rather than close them, where authentication is a wrapper around an otherwise open system — this is not a secure system with some risk, it is an insecure system with some locks. Least privilege means the payment service cannot read the user profile database, not because it's a nice constraint but because the blast radius of any compromise is bounded. Failing closed means that when something goes wrong, the system defaults to denying access, not granting it.

**Private.** Collect only what the system needs. Data never collected cannot be leaked. Data should expire, not accumulate.

Data you don't collect cannot be subpoenaed, stolen, or misused. Every piece of personal information you collect is a liability that has to be protected for as long as you hold it. The discipline of minimal collection is not a privacy nicety — it is risk management. Paired with this: data you do collect should have an explicit expiration. Data accumulated indefinitely creates compliance exposure, security risk, and storage cost that compounds. The default should be expiration, not retention.

**Compliant.** Meet the legal requirements of every jurisdiction you operate in. Compliance discovered after launch is not compliance — it is damage control.

Legal requirements are not a post-launch checklist. GDPR, CCPA, HIPAA, PCI-DSS, and the regulations specific to your industry have teeth — and they were almost certainly in force before you shipped. Compliance is a launch prerequisite, not an audit response. This means identifying the requirements before writing the first line of code, designing the data model with those requirements in mind, and testing against them with the same rigor you test functionality. The cost of getting it right before launch is a fraction of the cost of getting it wrong after.

---

## Write Yours Down

The principles don't change. The environment they operate in does.

The specific thing that has changed: agents are writing more of the code, and they have no access to the tacit knowledge your senior engineers carry. They will reproduce the patterns they find — good and bad, with equal confidence. In that environment, written principles are not a nicety. They are the only mechanism by which your team's judgment travels into the code an agent writes on your behalf.

Write them down. Argue about them. Update them when the world changes. Teach them to your team, your agents, and your systems. The alternative is principles that die when your most experienced people leave — and they always leave.

Use mine as-is if they fit. Use them as a starting point and make them yours. Or ignore them entirely and write your own from scratch. Any of those is fine. What isn't fine is not having them. Unwritten principles are just opinions — they don't travel, they don't scale, and they don't survive the people who hold them. Write them down. Then use them.

---

## Also in This Repository

[`personas/`](personas/) — Reviewer persona definitions for use with AI agents. Each persona captures a philosophy, core beliefs, communication style, and documented positions — enough for an agent to evaluate code, architecture, or process decisions in the voice of that specific person or role.
