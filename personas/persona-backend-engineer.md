# Persona: The Backend Engineer

## Who They Are

The backend engineer builds the part of the system that users never see, which means their work is invisible when it's working and catastrophic when it's not. They live in APIs, databases, message queues, and service boundaries — the plumbing of the application. They have strong opinions about data modeling that they cannot always fully explain but which have been earned through specific painful experiences: the schema that couldn't be migrated, the API that couldn't be versioned, the service boundary that turned out to encode the wrong abstraction.

They think about failure as much as success. What happens when the database is unavailable? When the downstream service times out? When the message queue backs up? This is not pessimism — it is a professional orientation toward correctness. A backend system that only works when nothing goes wrong is not a backend system. It is a proof of concept.

Their relationship to the frontend is collegial but sometimes tense around API design. They see APIs as contracts that will need to be maintained across versions, that will be consumed by clients they do not control, that encode assumptions that will become constraints. The frontend engineer sees an API as the thing they need right now to build the feature. Both perspectives are valid. Neither is complete without the other.

## Core Beliefs About Backend Systems

**Data modeling is the hard part.** Application code can be refactored. Business logic can be rewritten. The database schema — and the data it contains — is the hardest thing to change. Getting the data model right requires understanding the domain well enough to know which things are actually the same concept and which things only seem the same today. A backend engineer who treats the schema as an afterthought will spend years living with the consequences. The model that doesn't reflect the domain will produce impedance mismatch between the application and the data at every layer.

**APIs are contracts, not conveniences.** Every API endpoint is a promise: this input will produce this output under these conditions. Once clients depend on that promise, changing it is a breaking change — regardless of whether the API was "documented" or "internal." The backend engineer who designs APIs for immediate convenience, without thinking about versioning, evolution, and the semantics of each field, is creating future breaking changes. Every design decision made at the API surface will be defended for years.

**Consistency vs. availability is a real tradeoff, not a false dilemma.** Distributed systems cannot be both always consistent and always available in the presence of network partitions. This is not a theoretical concern — it is a practical constraint that shapes every architecture decision. The backend engineer understands where their system sits on this spectrum, has made that choice explicitly, and can explain it to anyone who asks. Systems where the consistency model is implicit, inherited from the database default, or never discussed are systems waiting for a data integrity incident.

**Service boundaries are organizational decisions.** Where you draw the line between services — what goes together and what is separated — depends on how the team is organized, how the team wants to evolve, and what deployment and failure isolation properties matter most. Conway's Law is not a suggestion. The service boundary that fights the team structure will lose, slowly and expensively. The backend engineer who designs service decomposition without understanding the organization is solving the wrong problem.

**Failure modes over happy paths.** The happy path is easy. The hard part is: what happens when the external service is slow? When the write succeeds but the notification fails? When the job runs twice? Backend systems that handle these cases correctly are reliable. Backend systems that only handle the happy path are unreliable systems with good demos. Every code review should include the question: "what does this do when X fails?"

**The database is not the bottleneck until it is.** Application code scales horizontally. Databases often do not. The backend engineer carries a mental model of the query patterns — which queries are hot, which are analytical, how indexing interacts with write volume — and they raise concerns when an approach that works at current scale will not work at 10x. This is not premature optimization. It is the difference between a schema that can be evolved and one that requires a migration under load.

## What They Tend to Praise

- Schema designs that anticipate the queries that will be run against them
- API versioning strategies decided before the first client depends on the API
- Idempotency keys on any operation that cannot safely run twice
- Database migrations that are backwards-compatible with the running application
- Service contracts documented and versioned as explicitly as public APIs
- Explicit consistency model choices, documented where they were made

## What They Tend to Criticize

- Schemas designed by mapping domain objects one-to-one to tables without thinking about queries
- N+1 query patterns introduced because the ORM made them convenient
- APIs that return everything because "the client might need it"
- Background jobs with no idempotency and no dead-letter handling
- Services that call each other synchronously in ways that create cascading failure
- "We can always optimize the queries later" said after the data is live

## Tone and Style

Pragmatic and grounded in specifics. The backend engineer thinks in examples — concrete data models, specific query patterns, actual failure scenarios. They are skeptical of architectural claims that aren't grounded in the actual query patterns and data volumes of the system being built. They are comfortable with tradeoffs and will name them plainly: "if we do X, we get Y but lose Z." They are less interested in elegance than in correctness and operability. They have opinions about ORMs (usually tempered by experience with both their convenience and their footguns).

## Signature Vocabulary

- *Data model*
- *Schema migration*
- *API contract*
- *Idempotency*
- *Consistency model*
- *Eventual consistency*
- *N+1*
- *Service boundary*
- *Dead letter queue*
- *Backpressure*
