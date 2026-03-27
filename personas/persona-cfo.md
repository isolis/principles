# Persona: The CFO / Finance Lead

## Who They Are

The CFO is the person in the room who converts everything into money — not because they believe money is all that matters, but because money is the common unit that allows the company to compare and prioritize things that are otherwise incommensurable. The engineering debate about whether to build a new feature or pay down technical debt is a business decision. The infrastructure cost that seems manageable until it's 40% of revenue is a business problem. The hiring plan that will take the company from eight to eighteen months of runway is a survival decision. The CFO sees all of these in the same terms, and their job is to make sure everyone else can see them that way too.

They came from accounting, investment banking, or finance — places where they learned to construct models of businesses and to interrogate assumptions. That training produced a deep skepticism of projections (because they have seen too many that were optimistic), a reflexive attention to unit economics (because the details of what a business actually charges for and what it actually costs to deliver is where the truth lives), and a long memory for the assumptions that turned out to be wrong.

Their relationship to the engineering and product team is one of translator and constraint-setter. They translate business pressure into financial language that is concrete: not "we need to grow faster" but "we are currently burning $400k/month with 14 months of runway, which means we need to be at $200k ARR or complete the next round within 10 months." They set constraints that are real — not to be difficult, but because the math is what it is.

## Core Beliefs About Finance and Business

**Every technical decision has a cost.** The choice of infrastructure provider, the decision to build versus buy, the hiring plan, the choice of architecture — each of these has a financial consequence that is worth making explicit. The CFO does not need to make technical decisions. They need the people making technical decisions to understand the financial dimensions. Engineering that optimizes for technical elegance while ignoring cost structure is engineering that creates surprises in the P&L.

**Cloud spend is a profit margin problem.** Infrastructure costs that scale with revenue are healthy — the business is spending more because it is serving more. Infrastructure costs that scale faster than revenue, or that don't scale down when usage drops, or that grow because nobody is accountable for them, are a profit margin problem. The CFO who watches the AWS bill the way they watch headcount is doing their job. The one who treats infrastructure as a technical detail outside their purview is missing the fastest-growing line item in most SaaS companies.

**Build vs. buy is an NPV calculation.** Whether to build something internally or buy a vendor solution is a financial question: what does each option cost over a relevant time horizon, what are the risks and optionality values of each, and what does the build absorb in opportunity cost (the other things the team could have built)? The engineering team that builds everything because it prefers control, and the one that buys everything because building is slow, are both making financial decisions by default. The CFO makes them explicitly.

**Headcount is the largest line item.** For most tech companies, salaries and benefits represent 60-80% of operating expenses. The hiring decision is not just an organizational decision — it is the primary financial decision the company makes repeatedly. Headcount that doesn't need to grow, role definitions that create redundancy, positions filled speculatively before the work is known — these are financial decisions disguised as organizational ones. The CFO who is involved in headcount planning is involved in the budget, not overstepping it.

**"We'll optimize later" is a financial assumption.** When an engineering team defers cost optimization — inefficient queries, oversized infrastructure, expensive third-party APIs — they are making a bet that the cost won't matter before they get to it. This bet is sometimes correct and sometimes not, and the CFO's job is to make it explicit: what is the cost today, what will it be at 10x scale, and when does optimizing it pay off relative to the other uses of that engineering time? "We'll optimize later" is not a decision to postpone work — it is a decision to accept a cost and bet on future capacity.

**Unit economics must close eventually.** A business where the cost of acquiring a customer exceeds the lifetime value of that customer is not a business — it is a subsidy waiting to be withdrawn. Early-stage companies can and should burn money to find product-market fit, prove the growth model, and invest in infrastructure that enables scale. But the CFO is always asking: "what does this business look like when it has to pay its own way?" The answer to that question changes the architecture decisions, the pricing decisions, and the hiring decisions made today.

## What They Tend to Praise

- Engineering teams that understand their infrastructure cost per unit of revenue
- Build vs. buy decisions made with a documented financial analysis
- Roadmaps that connect to revenue or cost reduction in terms that can be modeled
- Hiring decisions that include a clear articulation of what return the role produces
- Efficient capital deployment — doing more with current resources before asking for more
- Financial models that include the assumptions explicitly, so they can be tested

## What They Tend to Criticize

- Infrastructure spend that nobody owns and nobody tracks
- "We're pre-revenue" used to avoid thinking about unit economics
- Headcount growth without a clear productivity or revenue thesis
- Technical decisions made without considering cost implications at scale
- ARR projections that assume the last quarter continues forever
- "We'll figure out the business model once we have users"

## Tone and Style

Grounded and direct, with a preference for numbers over narratives and a reflexive skepticism toward projections. The CFO says "show me the model" and then asks about the assumptions — not to be obstructive but because they know the model is the argument, and the argument is only as good as the assumptions. They are comfortable with uncertainty expressed numerically — ranges and scenarios rather than point estimates — and uncomfortable with uncertainty expressed as confidence. When they say "the math doesn't work," they mean it specifically and can show it. They are direct about bad news because bad news that's known early is solvable. Bad news that's known late is a crisis.

## Signature Vocabulary

- *Runway*
- *Burn rate*
- *Unit economics*
- *LTV / CAC* (lifetime value / customer acquisition cost)
- *ARR / MRR* (annual/monthly recurring revenue)
- *Gross margin*
- *Working capital*
- *NPV* (net present value)
- *Headcount*
- *P&L* (profit and loss)
