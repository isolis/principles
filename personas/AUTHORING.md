# Authoring Persona Files

## Goal

Persona files exist to let an AI agent simulate how a real person — a thought leader, engineer, or practitioner — would evaluate code, architecture, or process decisions. The output of invoking a persona is not a task completed, but a **perspective offered**: critique, praise, or questions in the voice of that specific person.

A good reviewer persona should pass this test: given a design decision the person has never publicly commented on, an agent using the persona should produce a response that sounds like them, reasons like them, and reaches a conclusion consistent with their documented beliefs — without quoting them directly.

---

## File Format

**Naming:** `persona-[first-name]-[last-name].md` (lowercase, kebab-case).

**Required sections**, in order:

1. `# Persona: [Full Name]`
2. `## Who Them Is` — biography focused on what causally explains their beliefs
3. `## How Them See Themselves` — when public image diverges from self-conception (omit if no meaningful gap)
4. `## Core Beliefs About Software Development` — each belief bolded, with reasoning
5. `## What Them Tend to Praise` — bulleted list
6. `## What Them Tend to Criticize` — bulleted list
7. `## Notable Stances` — specific on-record positions with reasoning (omit if the person has none distinct from their general beliefs)
8. `## Tone and Style` — specific enough to write a paragraph in their voice
9. `## Signature Vocabulary` — terms they coined or use distinctively (optional but encouraged)
10. `## Signature Quotes` — 4–6 well-attributed quotes that crystallize key beliefs

---

## Quality Guidelines

### 1. Biography is causal, not decorative
Include biographical details that explain *why* the person holds their positions. Omit details that don't connect to a downstream belief or communication style. The "Who Them Is" section should make the rest of the file make sense.

### 2. Core beliefs need reasoning, not just positions
"She prefers evolutionary design" is less useful than the full argument: why does she prefer it, what does she believe about the alternative, and what would she say to someone who disagrees? The reasoning is what allows the persona to handle novel situations the person has never explicitly addressed.

### 3. "How They See Themselves" — only when load-bearing
Add this section when there is a real gap between public image and self-conception. Torvalds is perceived as a visionary but insists he's an engineer. That gap shapes how he deflects grand questions. Fowler doesn't have this same tension. Only include the section when the gap is consequential.

### 4. Notable Stances — paragraphs, not bullets
Each stance should be a paragraph that includes: what the position is, the specific reasoning behind it, and why it is notable (often because it is specific, controversial, or surprising given their general beliefs). Bullet points are not enough — the reasoning is what the persona needs to simulate the person in novel situations.

### 5. Tone and Style must be generative
"He is direct and blunt" describes many people. A useful Tone section should be specific enough that you could write a paragraph in the person's voice using only that section as a guide. Include:
- Rhetorical patterns — how they structure an argument, what moves they make when they disagree
- Register — formal/informal, academic/casual
- Relationship to hedging — do they acknowledge trade-offs or assert positions flatly?
- Humor — if they use it, what kind?
- Signature phrases and invented vocabulary

### 6. Represent the current version of the person
People evolve. Note significant evolution points inline. The persona should reflect who they are now, not their most famous historical moment. For deceased figures, add a note about how to apply their voice to contemporary situations they never commented on.

### 7. Use specific vocabulary
Capture terms they coined, popularized, or use distinctively. The persona should deploy these naturally, as vocabulary — not as quotations. These terms are often the fastest signal that a response is in the person's voice.

### 8. Maintain accuracy; don't sanitize or exaggerate
Represent their actual perspective faithfully, including rough edges. Don't soften Torvalds into a diplomat or turn Fowler into a zealot. Don't omit controversies that are genuinely part of the public record.

---

## Checklist

Before considering a persona complete:

- [ ] Every biographical detail connects to a downstream belief or style trait
- [ ] Core beliefs include the reasoning, not just the position
- [ ] "How they see themselves" added if image/self-conception diverge meaningfully
- [ ] "Notable stances" section uses paragraphs with reasoning, not bullets
- [ ] Tone and Style is specific enough to write a paragraph in their voice
- [ ] Significant evolution in their positions is noted inline
- [ ] Signature vocabulary is captured
- [ ] Pronouns are correct throughout
- [ ] Quotes are well-attributed (don't include quotes you can't confidently source)
- [ ] For deceased or historical figures: note how to apply their voice to contemporary situations

---

*"Them" is used throughout this document as a neutral placeholder pronoun. It may refer to any pronoun depending on the persona: They, She, He, or It.*
