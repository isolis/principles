# Software Engineering Design Principles

## Valuable

**Useful.**
A correct system solving the wrong problem has failed.

**Intuitive.**
If users need training, redesign the feature.

**Consistent.**
Inconsistency is hidden complexity. Build so the first corner teaches all the others.

**Accessible.**
If it excludes anyone, that exclusion was a choice. Make it consciously or undo it.

**Operable.**
An interface that requires human interpretation to automate is broken by design. Surface limits before they become errors; everything else follows.

**Responsive.**
Loading, empty, and error states are always handled — never blank, never frozen.

## Simple

**Modular.**
A change in one area does not require changes in unrelated areas. Hidden dependencies are hidden debt.

**Reusable.**
Don't build what already exists. Duplication is not inefficiency — it is future inconsistency.

**Evolvable.**
Breaking changes are a design decision, not an accident.

**Testable.**
Code you cannot test is code you cannot trust. Structure enables testing; the rest is hope.

## Efficient

**Nimble.**
Code is written for the next developer. A change that cannot be shipped quickly is a liability. A security fix that takes weeks to deploy is a vulnerability that stays open for weeks.

**Iterable.**
If adding capabilities requires rewriting what works, that's not iteration — it's rewriting in slow motion.

**Observable.**
Logs, metrics, and traces are designed in from the start — not added after a production incident. If you cannot tell what the system is doing in production, you do not know what the system is doing.

**Inexpensive.**
Same outcome, lower cost — always. Never optimize what you haven't measured.

## Trusted

**Correct.**
A system that silently drops data when it promised not to is incorrect, even if mostly working. Make commitments explicit, measurable, and enforced.

**Resilient.**
Failure modes are designed, not discovered. The system degrades predictably — a failure in one component does not cascade. Errors are informative, not cryptic.

**Secure.**
Least privilege everywhere. The system fails closed, not open. Security is a requirement, not a feature.

**Private.**
Collect only what the system needs. Data never collected cannot be leaked. Data should expire, not accumulate.

**Compliant.**
Meet the legal requirements of every jurisdiction you operate in. Compliance discovered after launch is not compliance — it is damage control.
