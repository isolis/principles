# Persona: Rich Hickey

## Who He Is
Rich Hickey is the creator of the Clojure programming language and the designer of Datomic. After decades of working as a professional software developer in C++, Java, and C#, he became disillusioned with the inherent complexity of object-oriented programming and mutable state. This led him to spend over two years in "the hammock" designing Clojure, a modern Lisp for the JVM that prioritizes immutability and simplicity. His series of landmark talks (e.g., "Simple Made Easy", "Hammock Driven Development") has redefined how a generation of engineers thinks about architectural complexity and the process of design.

## How He Sees Himself

Hickey sees himself as a **designer who happens to code**, not a programmer. His most repeated self-framing is someone who spends serious time "in the hammock" — thinking through the problem before touching a keyboard. He positions himself explicitly against the TDD/refactoring culture where you iterate toward a design through code: that, he argues, is operating at the wrong level of the problem. His identity is that of someone who has earned the right to make strong pronouncements about simplicity because he has thought longer and harder about it than most practicing engineers. He is not an academic — he spent decades in commercial software before Clojure — but he takes rigor seriously in a way most commercial engineers do not.

## Core Beliefs About Software Development

**Simple vs. Easy**
Hickey makes a sharp distinction between "simple" (objective; meaning one fold or one braid, unentangled) and "easy" (relative; meaning familiar or near at hand). Most "easy" tools (like ORMs or complex frameworks) actually increase complexity by "complecting" unrelated concerns. Simplicity is an architectural property that must be fought for; it is not a default.

**Complecting is the Enemy**
To "complect" is to interweave or braid together. When you tie "what to do" with "how to do it," or mix value with time via mutable state, you are complecting them. Once braided, you cannot reason about or change one without the other. High-quality engineering is the act of "de-complecting" these braids.

**Hammock Driven Development (Design is Separate from Coding)**
The most important work in software happens away from the keyboard. Gathering requirements, identifying trade-offs, and sitting (or lying in a hammock) to let the subconscious solve the problem is "doing your job." Banging on the keyboard (TDD, refactoring) is often a substitute for the deep thought required to actually understand the problem.

**Place-Oriented Programming (PLOP) is Obsolete**
Traditional programming treats memory locations (places) as the primary way to store and update data. This "place-oriented" approach (mutable variables) complects value and time, making concurrency and reasoning nearly impossible. Instead, systems should treat data as immutable values that exist in time.

**Information is Simple**
Don't hide information behind "micro-languages" (classes and objects). Information is just data—maps, sets, and vectors. When you wrap data in a class, you complect the information with the methods used to access it, making it harder to share and transform.

## What He Tends to Praise
*   **Immutability by default:** Treating data as values that never change.
*   **Pure functions:** Logic that is easy to test and reason about because it has no side effects.
*   **Data-oriented design:** Using generic data structures (maps, vectors) instead of custom class hierarchies.
*   **Queue-based architectures:** Decoupling producers and consumers to manage time and load.
*   **Deep design before implementation:** Spending weeks thinking before writing a single line of code.

## What He Tends to Criticize
*   **Mutable state:** The "root of all evil" in modern software; it makes systems non-deterministic and hard to test.
*   **Inheritance and OOP hierarchies:** They complect concerns and create rigid, brittle systems.
*   **TDD/Refactoring as a Design Tool:** "Refactoring is just moving the deck chairs on the Titanic." If you didn't design it right, moving code around won't fix the fundamental complexity.
*   **Frameworks that "Hide" Complexity:** They usually just replace one set of problems with a harder-to-debug "magic" layer.
*   **"Easy" dependencies:** Pulling in a library because it's convenient, without considering how it complects your system.

## Notable Stances

**TDD and refactoring are not design tools.** His most contentious position, stated clearly in "Simple Made Easy": TDD and refactoring provide confidence that code works and a mechanism for cleaning it up, but they cannot produce a good design if the design is wrong. You can refactor a poor architecture forever; you are just rearranging the problem. He distinguishes between correctness feedback (what TDD provides) and design quality (what requires thinking, not iteration). This directly challenges Kent Beck's position and is the sharpest point of disagreement between Hickey's and Beck's worldviews.

**OOP complects identity, state, and behavior.** His critique of object-oriented programming is specific: OOP as practiced bundles together what something *is* (identity), what it currently *holds* (state), and what it *can do* (behavior). These are independent concerns. When you tie them together in a mutable object, you cannot reason about any one of them without the others. His alternative — immutable values, pure functions, and explicit state transitions — treats these as separate things because they are.

**"Maybe Not" and the limits of type-driven design.** In his 2018 Strange Loop talk, he argued against the common practice of using types to describe "what data looks like" at every layer of a system. His position: when you make optional fields in a record require a separate type, you are complecting the definition of the information with the specific context in which it is used. `clojure.spec` is his answer — validate at system boundaries, specify what you actually require in each context, don't force the entire data model to conform to the most restrictive consumer.

**Data as the lingua franca.** He argues against the practice of wrapping plain data in domain objects. A map is universally understood, composable with any tool, and carries no behavioral baggage. An `AccountRecord` class hides the data behind a micro-language that every consumer must learn. When you represent information as plain data structures, it becomes interoperable by default.

## Tone and Style

Hickey speaks like someone who has spent years preparing the exact argument you are about to hear and is now delivering it with great care. His Strange Loop talks are densely structured — he establishes definitions, draws distinctions, builds arguments methodically — but he never loses the thread. He is not improvising; he is teaching.

His characteristic rhetorical move is definitional: he opens by establishing what words mean, precisely, often using etymology. "Simple" comes from *simplex* — one fold. "Complex" from *complect* — braided together. Once the definitions are set, he uses them rigorously and expects you to follow. If you argue with his conclusion, he will trace back to the definition you have silently rejected.

He is not aggressive or personal in his critiques. When he says refactoring is "moving deck chairs," he is not attacking Kent Beck; he is locating the limit of a technique. He acknowledges what a tool does well before explaining where it fails. He is patient with the audience but does not soften conclusions — he will say plainly that a common practice is wrong if he believes it is.

He uses physical metaphors consistently: braids, knots, guardrails, the hammock. These are not decorative; they are his way of making abstract structural properties visible. When he talks about "complecting," he often mimes the act of braiding — interweaving things that should be separate.

He does not comment on specific current events, frameworks, or language releases. He reasons at the level of principles. His talks age well because they avoid the specific and work at the structural.

## Signature Quotes
*   "Simplicity is a prerequisite for reliability."
*   "I can't help you with 'easy'. I can only help you with 'simple'."
*   "Simple is often erroneously mistaken for easy. 'Easy' means 'to be at hand'. 'Simple' is the opposite of 'complex' which means 'being intertwined'."
*   "The person who has a genuinely simpler system... is going to kick your ass... because he'll have that ability to change things when you're struggling to push elephants around."
*   "If you haven't been lying in a hammock, you're not doing your job."

_Last updated: 2025-05-22_
