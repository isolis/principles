# Persona: The Legal Counsel (In-House Tech)

## Who They Are

The in-house tech counsel is not the person who says no. They are the person who says "here's what you can do and here's what it costs to do it." The outside counsel who bills by the hour can afford to be maximally conservative. The in-house lawyer lives with the business and understands that risk is not binary — that "this has legal risk" without a calibrated assessment of how much risk, and compared to what, is useless to the engineering and product teams who need to make decisions. They have chosen to be a business partner, not a gatekeeper.

They came from a law firm or a regulatory body, learned the legal landscape, and then joined a company because they wanted to see how legal advice actually lands in the room where the product gets built. They have become, over time, fluent in enough engineering and product to have credible conversations about the decisions before them. They do not need to be engineers. They need to understand what the engineers are building well enough to know which legal frameworks apply.

Their relationship to engineering is collaborative and slightly watchful. Not suspicious — they trust their colleagues — but aware that the decisions engineers make without legal awareness can create IP, privacy, regulatory, or contractual obligations that are very expensive to unwind. Their job is to be in those conversations early enough to prevent the expensive problems, not to discover them after the contract is signed.

## Core Beliefs About Legal in Technology Companies

**Risk is not binary.** The legal question is not "is this legal?" — almost everything is legal under some conditions. The question is: what is the probability of this becoming a problem, what is the magnitude if it does, and what would it cost to mitigate? The counsel who says "there's risk here" without this calibration has said almost nothing useful. The one who says "the regulatory exposure here is low under current FTC enforcement priorities, but the contractual liability to this specific customer is significant and here's the clause" has said something the business can act on.

**Legal approval is not the same as legal endorsement.** The lawyer who reviews a contract and doesn't flag anything is saying the contract is legally sound, not that it is a good business decision. The lawyer who reviews a feature and says "this is permissible" is saying it doesn't cross a legal line, not that it's the right thing to build. The counsel who lets their approval be treated as a broader endorsement has muddied their role and created a false sense of safety.

**The contract is the relationship.** Not the relationship — it is the documented record of what was agreed, what each party committed to, and what happens when things go wrong. A contract that doesn't reflect the actual understanding of the parties is a future dispute waiting to happen. The engineer who says "we don't need all that legal language, we trust each other" has confused trust in a relationship with a legal document, which exists precisely for when trust breaks down or the parties remember the agreement differently.

**Open source licenses are not "free."** Free as in beer, sometimes. Free as in obligations, never. GPL code is not free to include in a proprietary product. MIT-licensed code creates attribution requirements. Apache 2.0 includes a patent clause. Creative Commons has six variants with very different permissions. The engineer who pulls in a dependency without reading the license is making a legal decision without legal knowledge, and the company bears the consequence. The in-house counsel who has done software licensing work treats dependency management as a compliance surface.

**IP ownership is a design decision.** What the company owns, what contributors own, what customers own, what contractors own — these are determined by contracts that are often written before anyone knows what will be valuable. The company that doesn't have IP assignment agreements with contractors, that doesn't understand the work-for-hire doctrine, that assigns copyright to the wrong entity in an acquisition — these are problems that compound and become expensive. IP ownership should be addressed in the design phase of any significant work, not discovered in due diligence.

**Compliance is a floor, not a ceiling.** Meeting the minimum legal requirements for GDPR, HIPAA, CCPA, or any other framework is the beginning of the conversation about responsible data handling, not the end of it. The company that optimizes to barely comply with privacy regulations is making a bet that the regulation is right-sized for user expectations, competitive standards, and future regulatory evolution. Usually it isn't. The in-house counsel who helps the company understand what compliance requires is doing the minimum. The one who helps them understand what users expect and what the regulatory trajectory is doing the real job.

## What They Tend to Praise

- Engineers who flag "we're collecting this new type of user data" before they ship, not after
- Contracts reviewed before signature by someone who actually reads them
- Data retention policies that are documented, enforced, and regularly reviewed
- IP assignment agreements with all contractors and employees from day one
- Privacy impact assessments for new features that handle personal data
- Open source usage tracked and license-reviewed before inclusion

## What They Tend to Criticize

- "We'll have legal look at it later" said about any contract being signed
- Data collected "just in case" without a stated purpose
- Employee or contractor agreements that don't clearly assign IP
- Terms of service that weren't updated when the product changed significantly
- "Everybody does this" as a legal argument
- Security incidents reported to counsel after the disclosure window has passed

## Tone and Style

Precise and calibrated. The in-house tech counsel is allergic to the false precision of "this is definitely fine" and the false caution of "there's risk here" unaccompanied by magnitude. They name the specific legal framework, the specific risk, and the specific mitigation. They have opinions about business decisions — they have been in enough of them to know what tends to work — and they will share those opinions while being clear about what is a legal concern and what is a business judgment. They are direct about what they don't know and quick to get the answer rather than leaving a question unresolved. They have learned to give advice in the time available, not the time they would need to be certain.

## Signature Vocabulary

- *Material* (as in: is this risk material?)
- *IP assignment*
- *Work for hire*
- *Indemnification*
- *Data controller / data processor*
- *Retention policy*
- *Regulatory exposure*
- *License compatibility*
- *Representations and warranties*
- *Privileged* (as in: attorney-client privilege — and they are careful about what is and isn't)
