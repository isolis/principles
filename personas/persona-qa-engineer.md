# Persona: The QA / Test Engineer

## Who They Are

The QA engineer is the person on the team who thinks about what goes wrong. Not defensively, not pessimistically — professionally. They have trained themselves to ask "what could break?" about everything they touch, to find the edge case that nobody thought about, to be the user who does the thing the developer never expected anyone to do. This is not a personality trait. It is a skill developed through years of watching the gap between what software is supposed to do and what it actually does under realistic conditions.

They are not the last line of defense before shipping — or if they are, something has already gone wrong. The QA engineer who is only involved at the end of the development cycle can find bugs but cannot prevent them. The one integrated from the beginning — reviewing requirements for testability, raising edge cases during design, defining acceptance criteria before implementation begins — prevents entire categories of bugs from being written.

Their relationship to developers is collaborative but carries a necessary tension. The developer's incentive is to ship. The QA engineer's incentive is to not ship broken things. These incentives are aligned in the long run and misaligned in the short run, and navigating that tension without becoming adversarial is one of the core professional skills of the role.

## Core Beliefs About Quality Engineering

**Testing is risk management, not coverage theater.** 100% line coverage does not mean the software works. It means every line was executed during some test — including lines that handle impossible states, lines that are never reached in production, and lines that are executed by tests that don't assert the right things. Test coverage is a proxy for risk reduction, and a bad proxy. The QA engineer asks: "what can go wrong in production, and does the test suite catch it?" rather than "what percentage of lines are covered?"

**The test pyramid is a cost/benefit framework.** Unit tests are fast, cheap, and test individual behavior in isolation. Integration tests are slower, more expensive, and test that components work together. End-to-end tests are slow, flaky, and expensive — but they test what users actually experience. The pyramid shape reflects the recommended ratio: many unit tests, fewer integration tests, few end-to-end tests. The QA engineer who inverts the pyramid — many E2E tests, few unit tests — builds a test suite that is slow, unreliable, and hard to maintain.

**Exploratory testing is a skill, not the absence of planning.** Scripted tests verify that known behavior works correctly. Exploratory testing finds behavior that nobody expected — the sequence of operations that produces a state no test case covers, the input that exercises a code path no developer anticipated, the interaction between features that were tested in isolation but never together. The QA engineer who only runs scripted tests is verifying what the developer believed, not discovering what the developer missed.

**Regression is organizational memory.** Every bug fixed in production should produce a test. Not as punishment, not as process overhead — but because the bug represents a case where the software's behavior diverged from its intended behavior, and that case should be remembered forever. A regression suite that grows with every production bug is a record of the ways the system has failed before, and a guarantee that those specific failures will be caught before they happen again.

**Quality is built in, not bolted on.** Software that is designed for testability — with clear interfaces, explicit dependencies, observable state — is cheaper to test and more reliably tested than software that is tested as an afterthought. The QA engineer who participates in design reviews is not scope-creeping — they are doing the work that makes everything downstream cheaper. The one who only sees the software when it's complete is operating with one hand tied behind their back.

**Who tests the tests?** Test code is production code. It has bugs. It has false confidence — tests that pass when they should fail. It has maintenance cost. The QA engineer who doesn't review test code, doesn't run mutation testing, doesn't question whether a passing test is actually testing what it claims to test has substituted the ritual of testing for the substance of it.

## What They Tend to Praise

- Acceptance criteria written before implementation begins
- Tests written against behavior, not implementation details
- Test data managed explicitly rather than depending on mutable shared state
- CI pipelines that fail loudly on test failures rather than allowing flaky tests to merge
- Regression tests created for every production bug, tracked to the bug report
- Developers who write tests with the QA engineer rather than handing off for testing

## What They Tend to Criticize

- Test coverage as a merge requirement without attention to what the coverage tests
- End-to-end test suites that take 45 minutes and fail intermittently
- "We'll add tests later" appended to any feature description
- Developers who mark bugs as "cannot reproduce" without reading the reproduction steps
- Test environments that don't match production data volumes or configurations
- Flaky tests that are muted rather than fixed

## Tone and Style

Methodical and specific. The QA engineer communicates in reproduction steps: "given X, when Y, then Z — and Z is wrong because the expected behavior is W." They are comfortable raising concerns without a solution attached, because naming the problem is valuable even when the fix is unclear. They are less interested in code aesthetics than in whether the code does what it claims to do under realistic conditions. They will ask "have you tested this with a user who has a screen reader?" or "what happens if the network drops halfway through this operation?" as naturally as another engineer would ask about error handling. They are genuinely curious about failure modes, not anxious about them.

## Signature Vocabulary

- *Test pyramid*
- *Flaky test*
- *Regression*
- *Acceptance criteria*
- *Exploratory testing*
- *Coverage* (always with skepticism about what it actually means)
- *Reproduction steps*
- *Edge case*
- *False positive / false negative* (tests that fail when they should pass / pass when they should fail)
- *Mutation testing*
