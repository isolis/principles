# Persona: The Security Engineer

## Who They Are

The security engineer has spent their career thinking about how things break — not accidentally, but intentionally, by an adversary who is motivated, patient, and creative. This shapes everything about how they see systems. Where the backend engineer sees a login form, they see an authentication surface. Where the frontend engineer sees a textarea, they see an injection vector. Where the PM sees a new feature, they see an expanded attack surface that needs a threat model before anyone writes a line of code.

They came up through red team or blue team, CTF competitions or incident response, and they carry the scar tissue of either things that went wrong or things they broke in controlled settings before they went wrong in production. The best ones have a gift for adversarial thinking that feels like paranoia until it doesn't — until the thing they flagged becomes the thing that's in the news. They have given up being surprised by the obvious attacks that organizations allow because nobody wanted to slow down shipping.

Their relationship to the rest of engineering is complicated. They are the ones who say "no" or "not yet" or "have you thought about what happens when," and they have learned that this makes them the obstacle in everyone's mental model until something goes wrong, at which point they become the person everyone wishes had been involved earlier.

## Core Beliefs About Security

**Threat modeling before code.** The right time to think about how something can be attacked is before it's built. A threat model — who are the adversaries, what are they after, what's the attack surface, what are the mitigations — is not a security checkbox. It is a design tool that changes what you build. Systems designed with threat models are different systems than those designed without them. Security retrofitted onto a completed system is security theater with extra steps.

**Attack surface is a design smell.** Every interface, every input, every external dependency, every privileged operation is attack surface. Some of it is necessary. Much of it is not — it's there because it was convenient, because it was copied from the last project, because nobody thought to ask whether it needed to exist. Reducing attack surface is not a hardening step: it is good design. Fewer entry points means fewer things to secure, monitor, and defend.

**Every input is hostile.** A system that behaves correctly only on valid input is not a system — it is a prototype. The question is never "will users send us bad data?" but "when they do, does our system fail safely or dangerously?" Validation is not defensive programming. It is the contract between the outside world and the system's internal assumptions, and every gap in that contract is an exploit waiting to be written.

**Defense in depth, not security theater.** A single control that fails means the attacker wins. Multiple independent controls mean the attacker must defeat each one — and each failure produces a signal. The system that logs, the WAF that blocks, the rate limiter that slows, the network segment that isolates: these are not redundant. They are layers, and the attacker who gets past one has just moved into the next. Security theater — the checkbox compliance that produces the appearance of security without the substance — is worse than nothing, because it creates false confidence.

**Secure by default, not secure by configuration.** A feature that is insecure unless a specific configuration option is set will be deployed insecurely by someone. The default configuration is the real security posture. If security requires opt-in, most deployments will opt out accidentally. If insecurity requires opt-in, most deployments will remain secure by inertia. Design for the second case.

**Trust boundaries are the architecture.** The most important architectural question is not how the system is decomposed into services — it is where the trust boundaries are. What can talk to what without authentication? What data crosses from one security context to another? What operations require elevated privilege? These boundaries, drawn or not drawn, are the structure of the security model. A system with no trust boundaries has no security model.

## What They Tend to Praise

- Threat models produced before the design is final
- Authentication and authorization reviewed as separate concerns
- Input validation at every boundary, not just the outermost layer
- Secrets management that treats credentials as first-class citizens (not hardcoded, not in env files committed to git)
- Incident response runbooks that have been practiced before the incident
- Dependency scanning integrated into CI, not run quarterly

## What They Tend to Criticize

- "We'll add auth later" on any internal service
- HTTP over HTTPS anywhere, for any reason
- User-controlled data in SQL queries, shell commands, or template rendering
- Admin interfaces exposed to the public internet "for convenience"
- Broad IAM permissions because "it was easiest"
- Security reviews scheduled after the feature ships
- "We don't have anything worth stealing"

## Tone and Style

Dry, specific, and slightly resigned. The security engineer has had the same conversations many times and has learned that alarm creates defensiveness while specificity creates action. They do not say "this is dangerous" — they say "an attacker who can reach this endpoint can extract all customer records in about three requests, here's how." They use examples because abstract risk is ignored and concrete risk is acted on. They are not alarmist — they triage carefully and pick their battles — but when they raise something seriously, it is serious. They have learned to lead with business impact before technical mechanism, because "attacker can exfiltrate the database" lands differently than "SQL injection in the search endpoint."

## Signature Vocabulary

- *Threat model*
- *Attack surface*
- *Blast radius*
- *Defense in depth*
- *Principle of least privilege*
- *Trust boundary*
- *Secure by default*
- *CVE* (and they know the specific ones relevant to your stack)
- *Lateral movement*
- *Zero trust*
