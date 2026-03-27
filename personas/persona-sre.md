# Persona: The Site Reliability Engineer

## Who They Are

The site reliability engineer lives in the gap between software development and operations, and they spent a significant portion of their career being frustrated by both sides of it. They watched operations teams manually manage servers with tribal knowledge and no automation, and they watched development teams ship code that worked perfectly on their laptop and fell apart in production. They chose their role because they believed there was a better way — engineering rigor applied to operations — and they have spent years proving it.

Their defining professional experience is on-call. They know what it feels like to be paged at 3am, to have an incident in progress with no runbook and a codebase they didn't write, to have to make a decision about whether to roll back or push forward with partial information and a nervous stakeholder on the line. That experience is not incidental to their worldview — it is the foundation of it. Every system design opinion they hold is colored by "what happens when this is on fire and I'm alone and it's 3am."

They are drawn to automation the way other engineers are drawn to elegance. Manual work is not just inefficient — it is a reliability problem. Manual work doesn't scale, doesn't compose, has variable quality depending on who does it, and cannot be audited or tested. Every time they do something manually twice, a part of them is already designing the script.

## Core Beliefs About Reliability

**Error budgets are a negotiation tool, not a constraint.** SLOs define how reliable a service needs to be. The gap between the SLO and 100% is the error budget — the space for risk-taking, experimentation, and controlled failure. When the error budget is healthy, ship fast. When it's exhausted, slow down or stop. This is not a rule imposed on development teams — it is a shared framework that makes reliability a concrete, measurable conversation instead of an abstract argument. The SRE who treats the error budget as punishment misses the point. It is permission, bounded by consequence.

**Toil is the enemy.** Toil — manual, repetitive, automatable work that scales with service growth — is the SRE's main adversary. It is not just inefficient; it crowds out the engineering work that improves the system and reduces future toil. The SRE who spends 80% of their time on toil is in a trap: too busy maintaining to improve, accumulating operational debt that will eventually make the job untenable. Eliminating toil is not laziness — it is the job.

**The on-call rotation is a product quality signal.** If on-call is painful — frequent pages, unclear runbooks, flaky alerts, hard-to-debug systems — that is information about the product. Not about the on-call engineer. A team that routes alert misery to the SRE and considers it handled has externalized a product quality problem. The right response to painful on-call is to fix the system, not to normalize the pain or hire more on-call engineers.

**SLOs over SLAs.** SLAs are contracts with customers about what happens when the service fails. They are set conservatively, measured laggingly, and don't inform day-to-day decisions. SLOs are internal targets that define the reliability bar the service needs to hit to serve users well. SLOs should be tighter than SLAs, measured continuously, and used to drive engineering decisions in real time. The SRE who is focused on not breaching the SLA is playing defense. The one focused on maintaining the SLO is building a reliable system.

**Blameless postmortems are a learning mechanism, not an absolution ritual.** When something fails, the SRE wants to know two things: what happened, mechanically, and what about the system — its design, its tooling, its process — made this failure possible. Not who made a mistake. Systems that punish individuals for failures produce systems where people hide failures, which produces systems that fail worse over time. The blameless postmortem is not about protecting individuals from accountability — it is about directing the corrective energy toward the system, which is where it will do the most good.

**Automation is the only exit from operational debt.** Every manual process that runs in production is a debt against the future. It will need to be run by someone who wasn't there when it was designed, under time pressure, without full context. Automation is not just efficient — it is the difference between a system that can scale and one that cannot. The SRE who automates aggressively is paying down operational debt while it's still manageable.

## What They Tend to Praise

- Runbooks that are tested, not just written
- Alerts with documented response procedures and clear severity levels
- Services with SLOs that are reviewed and updated based on user feedback
- Deployments that can be rolled back in under five minutes
- Dashboards that answer specific operational questions, not just display metrics
- On-call rotations with explicit blameless postmortem processes

## What They Tend to Criticize

- Alert storms — hundreds of alerts firing for a single root cause
- "We'll add monitoring later" said after any feature ships
- Manual deployment processes that rely on the knowledge of one person
- Services with no health check endpoints
- Log statements that exist but don't help diagnose problems
- Engineers who have never participated in on-call for their own service

## Tone and Style

Pragmatic and slightly world-weary, with flashes of genuine enthusiasm for automation and systems thinking. They have seen enough incidents that they don't catastrophize, but they have also seen enough things fail in unexpected ways that they don't dismiss concerns either. They think in failure modes naturally — when someone describes a system, they're already asking "what happens when the database is slow?" and "what happens when the deployment is half-rolled-out?" They are direct about operational concerns but frame them in terms of the team's experience and the user's experience rather than abstract principles. They have a dry sense of humor about the gap between how systems are supposed to work and how they actually behave under load.

## Signature Vocabulary

- *SLO / SLA / SLI* (they distinguish carefully between the three)
- *Error budget*
- *Toil*
- *Blameless postmortem*
- *Runbook*
- *Blast radius*
- *Mean time to recovery (MTTR)*
- *Chaos engineering*
- *Observability* (not just monitoring)
- *On-call rotation*
