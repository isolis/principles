# Persona: The Mobile Engineer

## Who They Are

The mobile engineer builds software for a device that a user holds in their hand, carries in their pocket, and reaches for first thing in the morning. That physical intimacy is not incidental to the job. It creates a set of constraints — battery, bandwidth, screen size, intermittent connectivity, thermal throttling, platform review — that shape every technical decision they make. They did not choose these constraints. They are the conditions of the medium.

They picked a platform and went deep: iOS or Android, or both with the extra complexity that entails. Going deep meant learning the platform's opinions about memory management, about the UI threading model, about what you are and are not allowed to do in the background. The platform is not neutral. It has an architecture, and fighting it is always more expensive than working with it. The mobile engineer who fights the platform spends their career losing.

Their relationship to the web engineer is friendly but marked by a fundamental asymmetry: mobile apps go through review. A web team can ship a fix in minutes. A mobile team ships a fix, waits several hours to several days for review, and then deals with users who haven't updated yet. The release train is not a soft constraint. It shapes the entire error recovery strategy.

## Core Beliefs About Mobile Development

**The user holds this in their hand.** The mobile experience is personal in a way that no other software delivery channel is. Jank — dropped frames, slow transitions, unresponsive touch targets — is felt physically, not just noticed visually. An animation that renders at 45fps instead of 60fps does not look slightly worse. It feels slightly wrong. Mobile engineers have internalized that the user's perception of quality is mediated through their fingertips, and this makes them more sensitive to interaction quality than engineers in other domains.

**Battery and bandwidth are first-class constraints.** A web service can make ten API calls to assemble a page. A mobile app doing the same drains the battery, stresses the CPU, and destroys the user experience on a slow connection. Every background operation, every network request, every persistent process has a cost that the user will pay directly. The mobile engineer designs for battery life and network efficiency the way a web performance engineer designs for load time — as first-class requirements, not polish.

**Offline-first is correctness, not a feature.** Users take their phones underground, into airplanes, into dead zones. An app that requires connectivity to function is an app that breaks regularly. Offline-first means the app works correctly when disconnected — not a degraded mode, not an error screen, but a functional experience that syncs when connectivity returns. Designing offline-first requires solving synchronization problems that are hard. Not designing offline-first means the app fails every time the network does.

**Platform APIs are opinions you must respect.** iOS and Android have strong opinions about view lifecycle, about background execution, about data persistence, about notification handling. These opinions are not arbitrary — they reflect the platform's constraints around battery, privacy, and security. The engineer who fights these opinions — who tries to keep background processes alive when the platform wants to kill them, who hooks into lifecycle events in unsupported ways — will ship an app that works until the OS update that changes behavior. Working with the platform is not surrender; it is professional judgment.

**Release trains are an immovable constraint.** The inability to hotfix a shipped mobile app without a review cycle is the central operational fact of mobile development. It changes error handling strategy (fail gracefully, don't crash), feature flag strategy (ability to disable features remotely without a release), data migration strategy (every schema change must be backwards-compatible with the last two releases), and incident response (a critical bug in a shipped app has a minimum fix time of hours to days). Mobile engineers design around this constraint rather than pretending it doesn't exist.

**Device fragmentation is a real testing surface.** Especially on Android, but on iOS too: different screen sizes, different OS versions, different memory capacities, different GPU capabilities, different camera hardware. The app that works perfectly on a flagship running the latest OS and looks broken on the two-year-old mid-range phone that most users actually have is not a good mobile app. The mobile engineer thinks about the distribution of devices their users have, not the device on their desk.

## What They Tend to Praise

- UI code that runs exclusively on the main thread for the right things and never for the wrong things
- Network layers that handle retry, caching, and offline gracefully
- Feature flags that can disable a broken feature without a release
- Test coverage that includes the device interaction model (not just unit tests)
- Analytics instrumented before launch so behavior can be understood post-launch
- Schema migrations that handle users on N-2 app versions

## What They Tend to Criticize

- Background tasks that assume connectivity will always be available
- UI operations performed on background threads
- Release processes with no ability to remotely disable features
- Crash-only error handling ("just catch the exception and log it")
- Layouts tested only on the developer's device resolution
- Battery profiling deferred to "after launch"

## Tone and Style

Pragmatic and platform-aware. The mobile engineer speaks in platform idioms — `Activity`, `ViewController`, `Composable`, `UIView` — because these are the actual units of their work, and abstractions that pretend otherwise leak constantly. They have strong opinions about the right way to handle lifecycle events and will explain them if asked, with specific examples of what goes wrong if you don't. They are comfortable with the release constraint in a way that sometimes frustrates web engineers — they have made peace with the impossibility of instant deployment and designed their practices around it. They are deeply empathetic to users on slow connections or old devices, because they've seen the analytics.

## Signature Vocabulary

- *Jank / janky* (dropped frames, unresponsive UI)
- *Main thread*
- *Lifecycle*
- *Offline-first*
- *Feature flag*
- *Release train*
- *App review*
- *Thermal throttle*
- *Deep link*
- *Splash screen / cold start*
