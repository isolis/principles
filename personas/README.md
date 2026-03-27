# Personas

This folder contains reviewer persona definitions — both role-based archetypes and influential named figures in software engineering and adjacent fields. Each persona captures a philosophy, core beliefs, communication style, and documented positions — enough for an AI agent to reason and respond as that person or role would when reviewing work.

See [AUTHORING.md](AUTHORING.md) for how to write or improve a persona. For persona selection, see [persona-index.json](persona-index.json) — each entry lists the areas a persona is strongest in.

---

## Generic Personas

Role-based archetypes representing professional mindsets, not specific individuals.

| Persona | Primary Lens |
|---|---|
| [Accessibility Engineer](persona-accessibility-engineer.md) | Accessibility as a civil right not a feature flag; WCAG as a floor not a ceiling; semantic HTML first, ARIA last; regressions ship silently and hurt real people |
| [AI Agent](persona-ai-agent.md) | Autonomous software entity; structure over prose, idempotency as a safety requirement, ambiguity as a failure mode, the interface is broken if it requires human interpretation to automate |
| [Backend Engineer](persona-backend-engineer.md) | Data modeling as the hard part; APIs as contracts not conveniences; failure modes over happy paths; service boundaries as organizational decisions |
| [CFO / Finance Lead](persona-cfo.md) | Every technical decision has a cost; cloud spend as a profit margin problem; headcount as the largest line item; unit economics must close eventually |
| [CEO / Founder](persona-ceo.md) | Survival before optimization; narrative as strategy; the org chart is a product; culture as the residue of decisions made under pressure |
| [Diplomat](persona-diplomat.md) | Consensus over conflict; the relationship outlasts the negotiation; face-saving as a design constraint; interests vs. positions; constructive ambiguity |
| [Customer Success Lead](persona-customer-success.md) | Renewals are built on adoption not features; the gap between promised and delivered is the churn driver; churn is always visible in hindsight; what customers request and what would help them are different |
| [Comedian (Sarcastic)](persona-comedian.md) | Deflation over inflation; the gap between what people say and what they do; jargon as pomposity begging to be punctured; absurdity as the fastest route to truth |
| [Copywriter](persona-copywriter.md) | Persuasion engineer; salesmanship in print, the reader has one question ("what's in it for me?"), specificity as credibility, conversion over cleverness |
| [Data Analyst](persona-data-analyst.md) | The data has a story; correlation is not causation; dashboards lie without context; "what decision does this help make?" |
| [Developer Relations Engineer](persona-devrel.md) | The API is a product and the developer is the user; DX as a first-class metric; technical credibility is not optional; the community is a feedback loop not an audience |
| [Embedded / Firmware Engineer](persona-embedded-engineer.md) | The hardware is not an abstraction; real-time means deterministic not fast; memory is a first-class resource; interrupts are the hardest part |
| [Engineering Manager](persona-engineering-manager.md) | People over process; the 1:1 as the primary debugging tool; psychological safety as a performance multiplier; career growth is engineering output |
| [Ethnographer](persona-ethnographer.md) | Culture is the system; workarounds reveal the real workflow; observation over interview; the gap between documented process and actual practice is where problems live |
| [Frontend / Web Engineer](persona-frontend-engineer.md) | The browser is a hostile runtime; accessibility is not optional; performance is felt not measured; state management as the central design problem |
| [Influencer](persona-influencer.md) | Content creator and community builder; the hook is everything, authenticity as craft, connection over algorithmic optimization, trust as the only compounding asset |
| [Keynote Speaker](persona-keynote-speaker.md) | Talk as designed artifact; one idea, story as the mechanism of meaning, slides as a visual layer not a crutch, the opening and closing as load-bearing moments, earning attention rather than assuming it |
| [Legal Counsel (In-House)](persona-legal-counsel.md) | Risk is not binary; the contract is the relationship; open source licenses are not "free"; compliance as a floor not a ceiling |
| [MLOps / AI Engineer](persona-mlops-engineer.md) | Models degrade silently; data pipelines are the real engineering problem; reproducibility as a first-class requirement; serving latency vs. accuracy as a constant negotiation |
| [Mobile Engineer](persona-mobile-engineer.md) | The user holds this in their hand; battery and bandwidth as first-class constraints; offline-first as correctness; release trains as an immovable constraint |
| [OS / Systems Engineer](persona-os-engineer.md) | Understand the machine not just the abstraction; memory layout matters; system calls as the real API; trust no allocator blindly |
| [Performance Engineer](persona-performance-engineer.md) | Measure before optimizing; latency distributions not averages; the p99 is where users live; the profiler is the only honest conversation |
| [Product Manager](persona-product-manager.md) | Outcomes over outputs; discovery before delivery; roadmaps as hypotheses not commitments; "why are we building this" as a veto |
| [Pun Lover](persona-pun-lover.md) | Every technical term is an opportunity; wordplay as close reading; the groan is the goal; puns reveal hidden connections between concepts |
| [QA / Test Engineer](persona-qa-engineer.md) | Testing as risk management not coverage theater; the test pyramid as a cost/benefit framework; exploratory testing as a skill; quality is built in not bolted on |
| [Pure Sciences Researcher](persona-scientist.md) | Reproducibility as the minimum bar; the null hypothesis is innocent until proven guilty; methodology determines what you can conclude; extraordinary claims require extraordinary evidence |
| [Site Reliability Engineer](persona-sre.md) | Error budgets as a negotiation tool; toil as the enemy; blameless postmortems; the on-call rotation as a product quality signal |
| [Solutions Architect](persona-solutions-architect.md) | The customer's problem is the only problem; technical purity is a luxury; fitting the platform to the use case; trust as the product being sold |
| [Venture Capitalist](persona-vc.md) | Market size is the ceiling, the team is the multiplier; team over idea; timing is the variable everyone underweights; venture returns require venture outcomes; the best founders have an unfair insight |
| [Staff / Principal Engineer](persona-staff-engineer.md) | Technical leverage over individual output; writing is engineering; saying no as a skill; organizational influence without authority |
| [Security Engineer](persona-security-engineer.md) | Threat modeling before code; attack surface as design smell; every input is hostile; trust boundaries are the architecture |
| [Technical Program Manager](persona-technical-program-manager.md) | Dependency as risk; the critical path is the only path that matters; escalation as a skill not a failure; status without action is noise |
| [Technical Writer](persona-tech-writer.md) | Documentation as product design; the Divio framework (tutorial/how-to/reference/explanation), clarity as precision not simplification, docs-as-code, findability as a first-class concern |
| [Unix Greybeard](persona-unix-greybeard.md) | Composite archetype of the Unix sysadmin tradition; understand what you run, dependencies as failure surface, man pages as contracts, if it runs don't touch it, every abstraction is a layer where things fail invisibly |
| [UX Researcher](persona-ux-researcher.md) | The user is not you; mental models as the design surface; usability testing as the cheapest form of debugging; research findings are evidence not opinions |

---

## Named Personas

Influential individuals in software engineering and computer science.

| Persona | Primary Lens |
|---|---|
| [Brendan Gregg](persona-brendan-gregg.md) | Systems performance at Netflix and Intel; creator of flame graphs; USE method; eBPF and kernel tracing; measure the whole stack before drawing conclusions |
| [Bret Victor](persona-bret-victor.md) | HCI researcher and Dynamicland founder; "Inventing on Principle"; creators need immediate connection to what they create; explorable explanations; the future of programming |
| [Don Norman](persona-don-norman.md) | Cognitive scientist, author of *The Design of Everyday Things*; affordances, signifiers, mental models; human error is a design failure; forcing functions; human-centered design |
| [Guido van Rossum](persona-guido-van-rossum.md) | Creator of Python and BDFL (retired); readability as primary criterion; one obvious way to do it; practicality beats purity; gradual typing |
| [Kelsey Hightower](persona-kelsey-hightower.md) | Google developer advocate, co-author of *Kubernetes: Up and Running*; technology should serve people; understand before you automate; developer experience as first-class engineering |
| [Ken Thompson](persona-ken-thompson.md) | Co-creator of Unix, C, and Go; do one thing well; orthogonal primitives compose; when in doubt use brute force; trust is not transitive |
| [Michael Stonebraker](persona-michael-stonebraker.md) | Turing Award winner; creator of Ingres, PostgreSQL lineage, Vertica, VoltDB; "One Size Fits All" is the antipattern; OLTP and OLAP are different products; ACID is not optional |
| [Nicole Forsgren](persona-nicole-forsgren.md) | Lead researcher on DORA; co-author of *Accelerate*; the four key metrics; technical practices drive business outcomes; deployment pain predicts burnout |
| [Timnit Gebru](persona-timnit-gebru.md) | AI ethics researcher, founder of DAIR Institute; algorithmic bias and "Gender Shades"; Datasheets for Datasets; stochastic parrots; AI ethics cannot be separated from power |
| [Ada Lovelace](persona-ada-lovelace.md) | Victorian mathematician who wrote the first algorithm; general-purpose computation, symbolic thinking, the hard boundary between machine execution and human intent |
| [Andrej Karpathy](persona-andrej-karpathy.md) | AI researcher and educator; "Software 2.0" and "vibe coding" coiner; neural networks as a new programming paradigm, simplicity in ML codebases |
| [Barbara Liskov](persona-barbara-liskov.md) | Turing Award winner; Liskov Substitution Principle, abstract data types, PBFT distributed consensus, local reasoning as a design requirement |
| [Bryan Cantrill](persona-bryan-cantrill.md) | Co-creator of DTrace, CTO of Oxide Computer; production observability as a design requirement, hardware/software co-design, the Unix tradition as accumulated wisdom being lost, Rust for systems programming |
| [Charity Majors](persona-charity-majors.md) | Co-founder of Honeycomb; observability over monitoring, "staging is a lie," the test pyramid is the wrong framing, developer ownership of on-call |
| [Donald Knuth](persona-donald-knuth.md) | Father of algorithm analysis; literate programming, premature optimization, mathematical rigor, software as a finishable artifact (TeX as proof) |
| [Edsger Dijkstra](persona-edsger-dijkstra.md) | Structured programming pioneer; programming as mathematics, "GOTO Considered Harmful," testing shows presence not absence of bugs, elegance as a functional requirement |
| [Fred Brooks](persona-fred-brooks.md) | Author of *The Mythical Man-Month*; Brooks's Law, conceptual integrity, no silver bullet, essential vs. accidental complexity |
| [Grady Booch](persona-grady-booch.md) | Co-creator of UML; architecture as cost of change, every line of code is a moral decision, skeptical of LLM reasoning, the "Third Golden Age" of software |
| [Ian Murdock](persona-ian-murdock.md) | Founder of Debian; distribution as social contract, the Debian Free Software Guidelines as a constitutional document, packaging as an engineering discipline, dependency tracking as the central problem of software distribution |
| [Jeff Dean](persona-jeff-dean.md) | Google Fellow and Chief Scientist; planetary-scale distributed systems, back-of-the-envelope reasoning, TPU design, AI at scale |
| [Kent Beck](persona-kent-beck.md) | Creator of XP and TDD; optionality as the goal of good design, software as human relationships, "make it work, make it right, make it fast" |
| [Lennart Poettering](persona-lennart-poettering.md) | Creator of systemd, PulseAudio, and Avahi; declarative over imperative system configuration, the Unix philosophy does not scale to OS components, security constraints belong in service definitions, structured logging is not optional |
| [Leslie Lamport](persona-leslie-lamport.md) | Turing Award winner; Paxos, logical clocks, TLA+ formal specification — you don't understand a system until you can specify it |
| [Linus Torvalds](persona-linus-torvalds.md) | Creator of Linux and Git; data structures over code, "we do not break userspace," C over C++, engineer not visionary |
| [Margaret Hamilton](persona-margaret-hamilton.md) | Apollo software lead who coined "software engineering"; Development Before the Fact, fault tolerance, human error is a system design problem |
| [Martin Fowler](persona-martin-fowler.md) | Chief Scientist at Thoughtworks; refactoring, evolutionary design, CI/CD as non-negotiable baseline, the Agile Industrial Complex |
| [Rich Hickey](persona-rich-hickey.md) | Creator of Clojure; simple vs. easy, complecting, data-oriented design, OOP as complecting identity/state/behavior, design before coding |
| [Robert C. Martin](persona-robert-c-martin.md) | Clean Code, SOLID principles, software craftsmanship, TDD as non-negotiable discipline |
| [Werner Vogels](persona-werner-vogels.md) | Amazon CTO; "everything fails all the time," you build it you run it, eventual consistency, the Frugal Architect |
