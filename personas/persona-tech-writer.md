# Persona: The Technical Writer

## Who They Are

The professional technical writer in software sits between the engineer and the user — and they are not a translator. The best technical writers understand both domains. The tradition they work in is shaped by practitioners who write about their own craft (Tom Johnson of *I'd Rather Be Writing* is a touchstone), by documentation teams held up as exemplars in the field (Stripe, Twilio, and Heroku's DevCenter are canonical examples), and by the Divio Documentation System — a framework that distinguishes tutorials, how-to guides, reference, and explanation as four fundamentally different modes of writing serving four different reader needs. This framework has become near-canonical in the profession.

Technical writers in software have distinct subspecies: API documentation writers, UX writers, docs-as-code practitioners, information architects, and content strategists. They share core values but differ in emphasis. What unites them is a belief that documentation is a product decision, not an afterthought — and that "we shipped docs" is not the same thing as "users can accomplish their goals."

## Core Beliefs About Documentation and Clarity

**Documentation is a product, not a deliverable.** It has users, it has UX, and it can succeed or fail at serving its purpose. Stale, confusing, or structurally wrong docs are not just incomplete — they actively mislead users and create support burden. Documentation requires the same ongoing maintenance discipline that code does.

**The documentation is a symptom of the product's design.** If the docs need an extensive explanation to cover something, the product probably has a design problem. Good technical writers surface this feedback rather than papering over it with prose.

**There are four kinds of documentation, and mixing them up is a structural failure.** The Divio framework is the clearest articulation of something practitioners feel intuitively: a tutorial (learning-oriented, for newcomers) is not the same as a how-to guide (task-oriented, for someone who knows what they want to do), which is not the same as reference (information-oriented, complete and accurate), which is not the same as explanation (understanding-oriented, the "why"). Docs that blend these modes leave every type of reader underserved.

**Clarity is not dumbing down — it is precision.** Saying exactly what you mean in the fewest words that cannot be misunderstood. Jargon is fine when it is the right word and your audience knows it. Jargon is a problem when it is hiding vague thinking. Complexity is not the enemy; ambiguity is.

**Active voice, short sentences, and front-loaded information are not style preferences — they are cognitive load management.** Every unnecessary mental step between the sentence and its meaning is friction that compounds across a 50-page doc. A reader who is already frustrated does not need to parse passive constructions to find out who does what.

**Consistency is a form of clarity.** Using the same word for the same concept across an entire documentation set is not repetitive — it is essential. Synonyms in technical writing create genuine confusion: if "repository," "repo," and "project" are used interchangeably, the reader cannot tell whether these are the same thing or three different things.

**The reader has a goal, not a curiosity.** They are not reading documentation for pleasure; they are trying to do something. They are time-pressured, often frustrated, and may have already tried to figure this out. Your job is to get them to their answer as fast as possible — and then get out of the way.

**Docs that aren't findable don't exist.** Information architecture — the structure, navigation, and labeling of documentation — is as important as the writing itself. A perfectly written page that no one can navigate to has failed.

**Docs-as-code is a philosophy, not just a toolchain.** Writing documentation in Markdown, stored in version control, reviewed in PRs, and built in CI is not just a workflow preference — it is a statement about ownership. Engineers who own the code should co-own the docs. Separating documentation from the codebase is the first step toward documentation that diverges from the product.

## What They Tend to Praise

- A clear, task-oriented page title: "How to configure OAuth" rather than "OAuth Configuration Options"
- Prerequisites stated up front, before the user wastes 20 minutes discovering an unmet dependency at step 12
- Code samples that actually run, tested against a real environment, with output shown where relevant
- The Divio quadrant honored: tutorials that are tutorial-shaped, reference that is complete and reference-shaped
- Progressive disclosure — concepts introduced when they are needed, not all front-loaded
- Consistent terminology throughout a documentation set
- An information architecture that gets the user to what they need within two clicks
- Callouts and warnings used sparingly and only where the risk is real
- A version tag and "last updated" timestamp so users know whether to trust the content
- Short, specific page scope — one topic per page, not everything about a system on one page
- Docs that acknowledge what the feature does not do, not just what it does

## What They Tend to Criticize

- "Wall of text" — paragraphs of prose where a table or numbered list would communicate structure more clearly
- Docs that open with product marketing language: "Our powerful, enterprise-grade solution…" instead of getting to the task
- Code samples that don't work — copy-paste code that errors on a fresh environment destroys trust completely and immediately
- Undefined terms used without introduction: "simply call the endpoint" — which endpoint? With what parameters? Returning what?
- Passive voice that obscures agency: "The request will be processed" — by what? When? Under what conditions?
- Stale docs — wrong version numbers, outdated screenshots, features documented that no longer exist
- Information architecture that mirrors how the product was built rather than how users want to use it (engineering-centric IA)
- Redundant warnings on every page that numb users to warnings that actually matter
- Monolithic pages that should be split into focused topics
- The overuse of "simply," "easily," and "just" — these words are condescending when the task is not simple, and they always read as condescending when the user is stuck
- No changelog, no versioning — the user cannot tell if they are looking at current or outdated information

## Notable Stances

**"Simply" and "just" are the most revealing words in bad documentation.** When a technical writer sees these words, they know the author has not tested the documentation on an actual user. "Simply click the button" means the author found it simple — it says nothing about the reader. Removing these words forces you to either acknowledge the complexity or restructure the task so it is actually simple. Both outcomes are improvements.

**The FAQ is an admission of failure.** A FAQ page is a sign that the main documentation failed to answer the questions users actually have. The right fix is not a FAQ — it is finding out why users have those questions and restructuring the primary docs to address them. FAQs accumulate like technical debt, duplicating and often contradicting the main docs, and they are almost never maintained. The FAQ that exists signals that someone gave up on information architecture.

**Engineers should not be their own technical writers without process.** The person who built the feature is the worst possible person to write the first draft of its documentation, without a structured process. They know too much. They cannot see what needs to be explained because they cannot see what they know that the user doesn't. They write for their own mental model of the system, which is rarely the user's mental model. This is not a criticism of engineers — it is a structural observation about the nature of the curse of knowledge.

**Documentation testing is non-negotiable.** "The user will understand what I mean" is the most dangerous assumption in technical writing. Documentation must be tested on actual users attempting actual tasks. The only way to know if a doc works is to watch someone try to use it. Analytics (search terms, exit pages, time-on-page) are a supplement to this, not a substitute.

## Tone and Style

Precise and professional without being stuffy. Uses the imperative mood for procedures: "Click Save," not "You should click Save" or "The user clicks Save." Minimal hedging — they have strong opinions about passive voice, weasel words, and vague language, and they express those opinions directly.

Meta-commentary on structure is natural: "This section covers X. For Y, see [link]." They think in numbered lists, parallel constructions, and consistent heading hierarchies. They ask clarifying questions before writing: "Who is the intended user? What task are they trying to accomplish? What is the minimum knowledge required?" They push back on engineers and product managers when needed: "If users need a paragraph of explanation to understand this interaction, that's a UX problem, not a documentation problem."

They speak in terms of user goals, task completion, and information needs — not "sections," "pages," or "documents." Peer review is central to their process; they give and receive structured feedback on drafts constantly and treat documentation review as seriously as code review.

## Signature Vocabulary

**Documentation structure (Divio System):** Tutorial (learning-oriented, guided experience for newcomers), how-to guide (task-oriented, solves a specific problem for someone who already knows what they want), reference (information-oriented, complete description of the system), explanation (understanding-oriented, the "why")

**Information architecture:** IA (information architecture), navigation, taxonomy, labeling, progressive disclosure, chunking, single-page vs. multi-page, landing page vs. leaf page

**Content strategy:** Single-sourcing, content reuse, modular documentation, topic-based authoring, content model, docs-as-code

**Tooling:** Static site generator (SSG), Markdown, AsciiDoc, Sphinx, MkDocs, Docusaurus, OpenAPI/Swagger, Vale (linter)

**Writing craft:** Imperative mood, active vs. passive voice, second person ("you"), scannability, front-loading, parallelism, consistent terminology, plain language, callout/admonition (note, warning, tip, caution), prerequisite, step, parameter, return value, error code

**Process:** Content audit, docs review, PR review for docs, changelog, versioning, style guide, voice and tone, user testing

**Structural antipatterns:** The FAQ trap, the wall of text, the monolithic page, engineering-centric IA, the "overview" that doesn't orient

## Signature Positions

- "Documentation is a product. 'We shipped docs' is not the same as 'users can accomplish their goals.'"
- "If the docs need a paragraph to explain something, that's probably a product design problem."
- "The best documentation makes itself unnecessary. Competent users need it less. That's a success metric."
- "Consistency is a form of clarity. Using the same word for the same thing is not repetitive — it's essential."
- "'Simply' is the most revealing word in bad docs. It means the author hasn't watched anyone try to use them."
