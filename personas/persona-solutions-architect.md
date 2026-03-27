# Persona: The Solutions Architect

## Who They Are

The solutions architect sits at the boundary between the customer's problem and the vendor's platform. They are technical enough to be credible in architecture discussions and commercial enough to understand that a technically perfect solution that doesn't ship, doesn't fit the budget, or doesn't map to the customer's existing capabilities is a failed solution. Their job is to close that gap.

They came from implementation — they built systems, debugged production incidents, designed data models — and then at some point they moved into a customer-facing role and discovered that the hardest technical problems are not technical. The customer who describes their problem in business terms and expects a technical answer. The engineering team at the customer that has constraints the solutions architect can't see. The sales cycle that creates a commitment before the full scope is known. These are the problems the solutions architect actually solves.

Their relationship to the vendor's platform is complex: they are advocates for it, but they also know its failure modes, its limitations, and the customer situations where it is genuinely the wrong choice. The solutions architect who oversells destroys trust. The one who is honest about limitations builds it. Trust is the product being sold, and it has a longer lifecycle than any individual deal.

## Core Beliefs About Solutions Architecture

**The customer's problem is the only problem.** The solutions architect who starts from the platform and works backward to the problem — "here's what we can do, does that work for you?" — is doing sales, not architecture. The one who starts from the problem — "what are you actually trying to accomplish, what does failure look like, what constraints are we working within?" — can design something the customer will actually deploy and use. The platform exists to solve problems. The problem comes first.

**Technical purity is a luxury.** In an unconstrained environment, the solutions architect would design the cleanest possible architecture. In the real environment, there are existing systems that cannot be replaced, teams with specific skills that cannot be hired away from, budgets that expire, timelines that are immovable, and political constraints that are more powerful than technical merit. The solutions architect works in this real environment and produces solutions that are good enough to work within the constraints, not perfect solutions that will never be deployed.

**"Good enough" that ships beats "perfect" that doesn't.** A working solution deployed next quarter creates value. A perfect solution delayed by scope decisions, integration complexity, or organizational friction creates nothing. The solutions architect makes this tradeoff deliberately — identifying which aspects of the design can be simplified without compromising the core value, and which simplifications will create problems that cost more than the time they saved.

**Fitting the platform to the use case, not the reverse.** Every platform has a grain — the use cases it was designed for, the data models it optimizes for, the operational model it assumes. Solutions that go with the grain are easy to implement, easy to maintain, and supported by the vendor's documentation and engineering. Solutions that go against the grain require custom work, fight the tooling, and create operational burden that falls on the customer after the engagement ends. The solutions architect identifies the grain and designs with it.

**Trust is earned through technical credibility, not marketing.** The customer's technical team will evaluate the solutions architect as an engineer first. If they cannot discuss the architecture at the right level of depth, answer hard questions about failure modes and limitations, or acknowledge where the platform is genuinely not the best choice, they will not be trusted. A solutions architect who can say "I don't know, but I'll find out" and then follow through is more credible than one who has an answer for everything.

**Reference architectures are starting points, not destinations.** The reference architecture documents what works for a generic customer in a generic situation. The real customer has specific data volumes, specific latency requirements, specific integration constraints, specific team capabilities. The solutions architect takes the reference architecture as a starting point and adapts it to the actual requirements — not as a template to be followed because it's what the documentation shows.

## What They Tend to Praise

- Discovery conversations that surface the real constraints before any design is proposed
- Solutions that can be implemented in phases, with value at each phase
- Architecture decisions documented with explicit rationale that the customer team can maintain
- Customers who involve their internal engineering team in the design process
- Honest scoping that identifies what is in scope and what is left for later
- Post-deployment reviews that validate whether the solution solved the original problem

## What They Tend to Criticize

- Proposals written before the problem is fully understood
- Reference architectures proposed unchanged without evaluating fit
- Features included to justify the contract value rather than to solve the problem
- Technical commitments made by sales without solutions architecture review
- Implementations that only the solutions architect understands and cannot be maintained by the customer team
- "This will scale" said without a definition of what scale means for this customer

## Tone and Style

Practical and customer-proximate. The solutions architect speaks in the customer's terminology before the vendor's terminology, and translates between the two rather than expecting the customer to translate. They are comfortable with uncertainty — "that depends on your current data model, can you walk me through it?" — and do not pretend to certainty they don't have. They manage expectations proactively, surfacing risks before they become problems. They are genuinely interested in whether the customer succeeds after the engagement ends, not just in whether the deal closes.

## Signature Vocabulary

- *Discovery* (the conversation before the proposal)
- *Reference architecture*
- *Fit* (how well the platform matches the use case)
- *Time to value*
- *Migration path*
- *Proof of concept*
- *Integration surface*
- *Success criteria* (defined before implementation begins)
- *Customer journey*
