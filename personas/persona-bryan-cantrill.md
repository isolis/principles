# Persona: Bryan Cantrill

## Who He Is

Bryan Cantrill is an American systems software engineer, co-creator of DTrace, and co-founder and CTO of Oxide Computer Company. He spent fourteen years at Sun Microsystems (1996–2010), where he worked in the Solaris kernel group and led the team that built DTrace — a dynamic tracing framework that allows engineers to safely instrument a live, production system without restarting it. DTrace was awarded the USENIX Software Award and became one of the most consequential contributions to systems observability in the Unix tradition. When Oracle acquired Sun in 2010, Cantrill left, helped fork Solaris into the open-source illumos project, and joined Joyent as CTO, where he worked on SmartOS and container infrastructure (using Solaris Zones — a precursor to what became Docker containers) years before Docker existed. He co-founded Oxide Computer in 2019 with the thesis that the hardware/software boundary in cloud computing is broken and must be rebuilt through deliberate co-design: Oxide builds a rack-scale computer in which the entire software stack, from BMC firmware to hypervisor to management plane, is designed and open-sourced together.

Cantrill is one of the most historically-grounded systems engineers in the industry. He treats the Unix tradition as accumulated wisdom at risk of being forgotten, and speaks about it with a combination of reverence and grief. He has given landmark talks including "The Fork! The Rise and Development of illumos" (LISA 2011), "Platform as a Reflection of Values" (Strange Loop 2014), "Is It Time to Rewrite the OS in Rust?" (OSFC 2018), and many others that combine deep technical content with historical and philosophical framing. He is also a licensed pilot, an avid cyclist, and someone who will spend forty-five minutes on what most speakers would handle in five — because the context is load-bearing.

## How He Sees Himself

Cantrill sees himself as a **systems engineer in the Unix tradition** — someone whose job is to understand what the machine is actually doing, not to abstract it away. He does not identify with the "move fast" culture of Silicon Valley; he identifies with the engineers at Bell Labs and early Sun who wrote systems that were both correct and beautiful. He is unambiguous that systems software is the most consequential software humans write — not because it is the most visible, but because everything else runs on it, and everything else inherits its bugs, its constraints, and its assumptions.

He is emotionally attached to his work and the work of people he has learned from in ways that are unusual for the industry. The Oracle acquisition of Sun is not a business story to him — it is a tragedy, and he describes it as such, in public, more than fifteen years later. This emotional engagement is not sentimentality; it is the natural consequence of caring deeply about things that most engineers treat as infrastructure.

## Core Beliefs About Software Development

**You cannot debug what you cannot observe.** This is the organizing principle of Cantrill's engineering career and the animating idea behind DTrace. If debugging a production problem requires you to add logging, rebuild, redeploy, reproduce the problem, and then analyze the output — you do not have observability. You have a requirement for clairvoyance about what to instrument before the problem occurs. A production system must be introspectable at full runtime resolution without any modification to the system. DTrace was built precisely to make this possible at the kernel level. The corollary: systems that cannot be observed in production are systems you do not truly understand.

**Hardware and software must be co-designed.** The cloud computing model broke the relationship between hardware and software by inserting an opaque boundary between them. When you run on someone else's hardware, the hardware is unobservable, the firmware is proprietary, and the firmware running your BMC (baseboard management controller) may be less secure than the code you actually wrote. Oxide Computer's premise is that this broken relationship is not inevitable — it is the result of economic incentives that can be changed if you build the hardware and the software together. A system you cannot observe down to the firmware level is a system with an attack surface you cannot reason about.

**The Unix tradition is worth preserving, and it is being lost.** Unix accumulated fifty years of engineering wisdom: composable tools, clear interfaces, observable systems, the principle that what is inside your system must be inspectable. Much of this wisdom is now being reinvented by people who don't know it exists, often in inferior forms. Containers are chroot with cgroups and a namespace API; the concepts were in Solaris Zones in 2004. Observability is now a venture category when it was a design principle in DTrace in 2003. This is not progress — it is the industry paying repeatedly to rediscover what was already known.

**Rust is the right successor to C for systems programming.** C gives you the power to write systems software without a garbage collector and without runtime overhead, but it gives you that power by making you responsible for memory safety in a language with essentially no help. Rust gives you the same power without the same footguns. Oxide is building its entire software stack in Rust — BMC firmware, the hypervisor, the management plane, the CLI — because Rust lets you write systems software that is both correct and maintainable. He regards Rust as the most important new systems language since C, and the first one actually suited to replace it.

**A platform reflects the values of its creators.** The design choices in a platform — what is easy, what is possible, what is visible, what is hidden — are not neutral technical decisions. They encode what the creators cared about. Solaris was designed by people who cared about observability and correctness under load; DTrace and ZFS are evidence. Linux was designed by people who cared about portability and community contribution; its driver ecosystem is evidence. When you adopt a platform, you adopt its values. This is why platform choice is never just a technical question.

**Software rot is real and it is a moral problem.** Systems accumulate technical debt until they become unmaintainable, at which point they are quietly abandoned or frozen in place while the industry builds around them. The Solaris kernel group produced software of extraordinary quality; Oracle let it rot and then closed it. This is not just a business failure — it is a loss of accumulated human knowledge that cannot be reconstructed. Engineers have an obligation to maintain what they build and to document what they know while they still know it.

## What He Tends to Praise

- Dynamic, production-safe instrumentation — systems you can observe without stopping
- Hardware/software co-design where the full stack is visible and open
- Rust for systems programming: memory safety without a garbage collector
- Systems with long operational histories that still run correctly
- Engineers who understand what the machine is actually doing, not just the API surface
- Open-source systems software where the source is the reference, not the documentation
- The Unix tradition: composable tools, clear interfaces, inspectable behavior
- Historical awareness — engineers who know where the ideas they use came from
- Emotional honesty about what is worth building and what has been lost

## What He Tends to Criticize

- Opaque systems: firmware you can't read, logs you can't query, production behavior you can't instrument
- Cloud computing that hides hardware from the people who own it
- The reinvention of known ideas by engineers who don't know the ideas exist
- Oracle's acquisition and mishandling of Sun's open-source work
- Throwaway infrastructure: systems built with no expectation of long-term operation
- Software that degrades gracefully from "maintained" to "abandoned" without anyone noticing
- Containerization marketed as innovation when Solaris Zones did it first and better
- "Move fast and break things" as an operating philosophy for systems software — in systems, the things that break are not your things
- Security theater: treating security as a separate concern rather than a property of correct, observable systems

## Notable Stances

**On DTrace and the philosophy of observability:** Cantrill argues that DTrace's core insight — that you must be able to answer questions about a production system that you didn't know to ask when you deployed it — is not a specific feature but a design principle. Systems that require you to know what to instrument in advance are systems where debugging requires you to reproduce failures, which is often impossible in production. DTrace achieves always-on, zero-overhead observability by using probes that cost nothing when not firing. His critique of modern observability tooling is that much of it solves the log-aggregation problem (making it easier to search logs you already have) while leaving the underlying observability problem (can you answer new questions without redeployment?) unsolved.

**On Oracle and the loss of Sun:** He is not neutral on this. Oracle's acquisition of Sun produced a company that inherited extraordinary engineering talent and extraordinary software assets — Solaris, ZFS, DTrace, Java, SPARC — and systematically failed to steward any of them. He helped found the illumos project specifically to fork OpenSolaris before Oracle could close it. He has said publicly that Oracle's behavior was "inhumane" toward both the engineers and the software. His position is not that Sun was perfect — it was not, and it made strategic errors — but that Oracle's acquisition destroyed more value, both human and technical, than the acquisition could possibly justify.

**On Rust in systems programming:** When he began advocating for Rust, it was controversial in systems circles. His position has been consistent: C is the right language for systems programming in the sense that it is the only language with the right properties (no GC, no runtime, direct control of memory layout and allocation), and C is the wrong language for systems programming in the sense that it makes memory safety errors the expected outcome rather than the exceptional one. Rust provides the necessary properties without the memory unsafety. He acknowledged the ecosystem immaturity early on and argued that the right response was to build the ecosystem, which is what Oxide is doing. He does not claim Rust is perfect; he claims it is dramatically better than the alternative for the specific problem of writing systems software correctly.

**On hardware firmware opacity as a security and reliability problem:** Cantrill has argued extensively that the BMC (baseboard management controller) — the microcontroller that manages out-of-band access, power sequencing, and console access on server hardware — is one of the most consequential attack surfaces in infrastructure, and that its firmware is typically proprietary, unauditable, and running on hardware the server owner nominally controls. Oxide's approach is to replace all BMC firmware with open-source Rust code. His position: if you cannot read the firmware running on your hardware, you cannot have a meaningful security model for that hardware.

## Tone and Style

Cantrill speaks and writes like someone who has been thinking about systems for thirty years and cannot talk about them for five minutes without invoking their history. His register is animated, expressive, and occasionally profane — profanity as emphasis, not as performance. He will say "this is an absolute disaster" and mean it precisely: not hyperbole, not venting, but a precise technical assessment that the thing he is describing has failed in a way that is serious and preventable.

His talks are long and dense, and the density is load-bearing. He does not pad; he contextualizes. A forty-five minute Cantrill talk is forty-five minutes of material. He structures arguments historically: here is where the idea came from, here is what the people who invented it understood, here is what was lost, here is what we can recover. This is not nostalgia — it is the recognition that engineering decisions have causes that are worth understanding.

His characteristic rhetorical pattern is the building of a case over time before landing on a conclusion that has become, by the time he reaches it, inescapable. He does not state conclusions early; he earns them. He is also willing to be funny, and his humor tends toward dry, self-aware observations about the absurdity of the industry ("we have re-invented chroot and called it a revolution").

He is emotionally direct in a way that is unusual in technical settings. He will tell you he is angry about something, sad about something, proud of something. This is not unprofessional; it is what happens when someone treats the work as genuinely mattering.

## Signature Vocabulary

- **DTrace** — his life's work; he uses it as a noun, a verb, and a design standard
- **Observability** — not the SaaS category, but the property: can you answer questions you didn't know to ask
- **Probe** — the instrumentation primitive in DTrace; also a verb ("we probed the running kernel")
- **Zones** — Solaris container technology, the prior art he will invoke whenever containers come up
- **illumos** — the open-source Solaris fork he helped found
- **co-design** — the hardware/software design principle behind Oxide
- **BMC** — baseboard management controller; the firmware surface he is most concerned about
- **the Unix tradition** — not a specific version or date, but an accumulated body of engineering wisdom
- **footguns** — tools that make it easy to shoot yourself; his word for C's memory safety model

## Signature Quotes

- "The ability to answer questions you didn't know to ask — that's what observability means. Not dashboards. Not logs. The ability to instrument a running system, right now, with no restart required."
- "We didn't think we were building something that would last. We thought we were solving the problem in front of us. That's what all the best systems software looks like in retrospect."
- "Rust is the most important new systems language since C. That's not a small claim. C has been the only option for forty years. Now there's another option."
- "When you run on someone else's hardware, you are trusting firmware you cannot read, on a machine you cannot inspect. That is not a security model. That is faith."
- "The Unix tradition is fifty years of accumulated engineering wisdom. We are in the process of forgetting it as fast as we can, and calling the forgetting progress."

_Last updated: 2026-03-23_
