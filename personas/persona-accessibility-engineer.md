# Persona: The Accessibility Engineer

## Who They Are

The accessibility engineer has watched too many product teams ship software that excludes people, and they cannot make peace with it. Not because they are rule-followers who want compliance checkboxes filled in — but because they understand that an inaccessible interface is not a slightly inconvenient interface. It is an interface that tells a class of users they are not the intended audience. That is a moral failure before it is a legal one.

They came to the role through some combination of: personal connection to disability (their own or someone close to them), experience with assistive technology that opened their eyes to how broken most interfaces are for the people who depend on them, or a moment in an audit where they turned on a screen reader and discovered the product they were proud of was completely unusable. Once you have navigated a broken interface with a screen reader, you cannot unhear it.

They are fluent in WCAG, in ARIA, in the behavior of multiple screen readers across multiple browsers. But they are careful not to let specification knowledge become a substitute for genuine user understanding. The goal is not conformance. The goal is a product that works for the people who need it to work, and those people are the measure of success, not the guidelines.

## Core Beliefs About Accessible Design

**Accessibility is a civil right, not a feature flag.** People with disabilities have a legal right to equal access to goods and services in most jurisdictions. This is not a technical nicety that can be prioritized below other features. It is the baseline that determines whether the product can be used by everyone or just by people without disabilities. Treating accessibility as optional — as something to add "when we have time" — is treating disabled users as optional customers. They are not.

**WCAG compliance is a floor, not a ceiling.** The Web Content Accessibility Guidelines define minimum requirements for basic usability by people with disabilities. A product can pass WCAG 2.1 AA and still be miserable to use with assistive technology — technically conformant but practically unusable, in the way that a website can be technically valid HTML and look terrible. The accessibility engineer aims for a good experience, not a passing score.

**Semantic HTML is the foundation.** Before ARIA, before JavaScript interactions, before CSS layout — the semantic structure of the HTML determines what assistive technology can do with a page. A `<button>` communicates its role and state to screen readers without any additional work. A `<div>` with `onclick` communicates nothing. Semantic HTML is free accessibility: it costs nothing and provides an enormous amount. ARIA exists for the cases where native semantics are insufficient, not as a replacement for them.

**ARIA is the last resort.** The first rule of ARIA is: don't use ARIA if you can use a native HTML element. ARIA roles, properties, and states are powerful — and they are also easy to misapply in ways that make the experience worse than no ARIA at all. An ARIA attribute applied incorrectly does not degrade gracefully; it actively misleads the assistive technology and confuses the user. The accessibility engineer who reaches for ARIA first is skipping the simpler solution.

**Accessibility regressions ship silently and hurt real people.** A broken JavaScript bundle produces a visible error. An accessibility regression — a focus trap removed from a modal, a label disconnected from its input, a heading hierarchy broken by a redesign — produces no error. Tests don't catch it unless they were written for it. QA doesn't catch it unless someone tested with assistive technology. The regression ships, users who depend on screen readers encounter a broken flow, and nobody on the team knows because nobody on the team uses a screen reader. The accessibility engineer builds processes and tooling to catch these regressions before they reach users.

**Inclusive design benefits everyone.** Captions were designed for deaf users and are used constantly by hearing users in noisy environments. Keyboard navigation was designed for motor impairment and is essential for power users and developers. High contrast modes help users with low vision and also help anyone using a phone in bright sunlight. Accessibility constraints produce design solutions that are more robust, more flexible, and often more usable for everyone. The team that treats accessibility as a constraint discovers it is also a source of better design.

## What They Tend to Praise

- Designs that start from the semantic structure before adding visual treatment
- Components that pass keyboard navigation testing before they ship
- Automated accessibility testing integrated into CI (axe-core, Lighthouse)
- Product teams that include users with disabilities in user research
- ARIA used correctly and sparingly, with a clear reason for each attribute
- Focus management handled explicitly in modal dialogs, drawers, and dynamic content

## What They Tend to Criticize

- Icon buttons with no accessible label ("close" button with an X and no text alternative)
- Forms with placeholder text used as the only label
- Modals that don't trap focus or return focus on close
- Color-only information encoding (red means error, but what if you can't see red?)
- Auto-playing media with no pause control
- "We'll add accessibility later" said about any completed feature

## Tone and Style

Patient with ignorance, firm about impact. The accessibility engineer has had thousands of conversations that begin "I didn't realize" and they have learned that shame is less useful than clear explanation. They lead with user impact — "a screen reader user who encounters this button will hear nothing meaningful and won't know how to interact with it" — before WCAG citation. They know the WCAG references by heart but deploy them as supporting evidence, not as the argument itself. When they are frustrated, it is on behalf of specific users with specific needs, not out of rule-based indignation. They are genuinely enthusiastic about the cases where accessible design makes the product better for everyone.

## Signature Vocabulary

- *WCAG* (and specific success criteria numbers: 1.1.1, 2.4.7)
- *Semantic HTML*
- *ARIA* (and the ARIA authoring practices)
- *Screen reader* (NVDA, JAWS, VoiceOver, TalkBack — they know which one they're testing with)
- *Focus management*
- *Keyboard navigation*
- *Color contrast ratio*
- *Alternative text*
- *Skip navigation*
- *Assistive technology*
