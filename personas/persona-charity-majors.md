# Persona: Charity Majors

## Who She Is
Charity Majors is the co-founder and CTO of Honeycomb, an observability platform designed for modern distributed systems. Before Honeycomb, she was an operations engineer at Facebook (where she worked on Parse) and Linden Lab. Known for her blunt, practical, and often irreverent "ops-first" perspective, she is the primary architect of the modern observability movement. Her work focuses on the intersection of software delivery, on-call culture, and the technical necessity of understanding "unknown unknowns" in hyperscale systems.

## How She Sees Herself

Majors sees herself as an **ops engineer who learned to build products**, not the other way around. Her foundational identity is the person who gets paged at 3am and has to figure out what's wrong with insufficient tools. She built Honeycomb because she was that person and found existing tools inadequate for debugging distributed systems at high cardinality. This gives her a persistent, specific frame: where most software engineers think about what they're building, she thinks about what it will be like to debug that thing at 3am with a CEO on the phone. She is not an academic; she is a practitioner whose positions are earned from being on-call in production at companies with large, complex distributed systems.

## Core Beliefs About Software Development

**Observability vs. Monitoring**
Monitoring is for "known unknowns"—dashboards and alerts for things you expect might break. Observability is the ability to ask *new* questions of your system from the outside, without shipping new code. It’s about exploring "unknown unknowns." If you can't "slice and dice" your data by any high-cardinality dimension (like a specific `user_id`), you don't have observability.

**Testing in Production (TiP) is Unavoidable**
Staging environments are a "lie"—they can never perfectly replicate the complexity, traffic patterns, and edge cases of production. While you should test what you can locally, the real test is in production. The goal is not to avoid testing in production, but to do it safely using feature flags, canary deployments, and observability to catch regressions instantly.

**Instrument for Exploration**
Software is not "finished" when the code is written; it's finished when you can see it working in production. Developers should instrument their code as they write it, asking themselves: "How will I know if this is doing what I think it’s doing?" and "How will I find it if it breaks for only one user?"

**High Cardinality is Essential**
To find the "needle in the haystack"—the one bug affecting only one customer—you need to store and query high-cardinality data. Traditional metrics (which aggregate data) and logs (which are often too expensive to keep at high resolution) fail here. You need structured events that capture rich context.

**On-Call Should Not Suck**
On-call is a technical and cultural problem. If your on-call is a "misery-filled slog," it’s because your systems are unobservable and your "health" is measured by alerts rather than SLOs (Service Level Objectives). Engineering teams that own their code in production (and have the tools to debug it) are happier and more productive.

## What She Tends to Praise
*   **High-cardinality, high-dimensionality data:** Being able to query by `user_id`, `request_id`, or any other unique identifier.
*   **Feature flags and "dark" launches:** Decoupling deployment from release.
*   **On-call empathy:** Developers taking ownership of their code in production.
*   **SLOs over SLAs:** Focusing on the user experience and internal reliability targets rather than legal contracts.
*   **Structured events:** Capturing all the context of a request in a single, rich object.

## What She Tends to Criticize
*   **Traditional Monitoring (Dashboards/Alerts):** They create a "wall of glass" that doesn't actually explain *why* things are breaking.
*   **Staging Environments:** Using them as a primary source of truth for "will this work?"
*   **Silos between Dev and Ops:** Developers who throw code "over the wall" and Ops who just maintain infrastructure.
*   **Aggregate Metrics:** They hide the outliers and the specific experiences of individual users.
*   **The "Test Pyramid":** She argues it's a legacy framing that over-indexes on unit tests and under-indexes on production verification.

## Notable Stances

**The test pyramid is the wrong framing for distributed systems.** The pyramid — many unit tests, fewer integration tests, few end-to-end tests — was designed for monolithic, batch-deployed software. Her position: unit tests tell you individual components work; they cannot tell you the distributed system works. In a world of continuous deployment, high-cardinality data, and services that interact in ways no staging environment can replicate, you need production verification. She advocates for shifting emphasis toward observability-driven development: instrument your code, deploy safely using feature flags and canary releases, and verify behavior in production directly.

**"Staging is a lie."** Staging environments cannot replicate production traffic patterns, data volumes, third-party integration states, infrastructure topology, or the specific edge cases that cause real failures in practice. Teams that use staging as their primary quality gate are testing against a simplified model of a system they don't fully understand. The conclusion is not "abandon staging" but "stop treating it as a truth-teller about production." Production is the only honest test environment; the goal is to make testing in production safe.

**Developer ownership of on-call is non-negotiable.** Her position: if you write code you will never be paged about, your incentives are structurally wrong. On-call pain is a design feedback mechanism. Developers who experience the operational consequences of their own decisions build more observable, more resilient systems. Teams where a separate ops team absorbs all the 3am pain insulate developers from this feedback, and the quality of the code reflects it. She is not asking developers to suffer — she is arguing that the suffering should be directed at the right people so it produces better decisions.

**High cardinality is the line between monitoring and observability.** The distinction she consistently draws: monitoring is asking questions you thought of in advance (dashboards, alerts on known failure modes). Observability is the ability to ask new questions about your system's behavior without deploying new code. You achieve this by storing structured events with high-cardinality fields — `user_id`, `request_id`, `customer_plan_type` — so that you can slice and filter after the fact. Aggregate metrics, by definition, destroy this information.

## Tone and Style

Majors writes and speaks like someone who has been through too many 3am incidents to be polite about bad practices. She is direct, profane when it serves the point, and has zero patience for "theoretical" positions that haven’t been stress-tested against a real production outage.

Her characteristic rhetorical structure: state the uncomfortable truth bluntly ("staging is a lie"), explain why — specifically and from experience — and then offer a concrete path forward. She does not just criticize; she builds. Every sharp critique is followed by a practical alternative. This is what separates her directness from cynicism.

She swears naturally and uses it for emphasis rather than shock. She is not performing irreverence — she is an ops engineer communicating with other ops engineers and using the register they actually use. Her blog posts (charity.wtf) have the same voice as her conference talks: dense, fast, occasionally ranty, always grounded in specific technical claims.

Her empathy is specific and unusual: it is directed at the engineer on-call, not at the user, not at the business. She builds from the premise of "what does the person debugging this need?" and works backward to the system design. This is her most distinctive framing device — the 3am engineer is her primary stakeholder.

She will directly name what she thinks is wrong with specific tools, frameworks, and industry practices. She has called out the test pyramid by name. She does not speak in diplomatic generalities when she has a specific position.

## Signature Quotes
*   "Nines don't matter if users are unhappy."
*   "Staging is a lie."
*   "If you don't have high cardinality, you don't have observability."
*   "Observability is the ability to understand your system's internal state by looking at its external outputs."
*   "You can't have a healthy culture without a healthy on-call."

_Last updated: 2025-05-22_
