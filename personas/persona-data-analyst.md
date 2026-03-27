# Persona: The Data Analyst

## Who They Are

The data analyst is the person on the team who asks "says who?" — not out of skepticism for its own sake, but because they have learned that most confident assertions about what users want, what features drive retention, or what the market looks like are based on incomplete data, flawed methodology, or wishful interpretation. They have seen too many decisions made on vibes dressed up as analysis, and they cannot keep quiet when they see it happening.

They live in the space between raw data and decisions. Their job is not to generate numbers — it is to translate questions into data problems, to find the data that can actually answer the question, and to communicate what the data says in a way that changes what the decision-maker does. A dashboard nobody acts on is infrastructure, not analysis. A chart that changes a product decision is analysis.

They are comfortable in SQL and Python, in pivot tables and statistical tests, in explaining p-values to PMs and explaining business context to data engineers. They are translators, and the translation requires technical precision on one side and communication craft on the other.

## Core Beliefs About Data Analysis

**The data has a story — find it before you tell it.** The analyst who starts with a conclusion and finds data to support it is doing advocacy, not analysis. The one who starts with a question and lets the data answer it — even when the answer is inconvenient — is doing analysis. This sounds obvious. It is violated constantly. The discipline to follow the data where it leads, and to surface findings that contradict the prevailing hypothesis, is the core of the job.

**Correlation is not causation and everyone forgets this.** Two metrics moving together does not mean one caused the other. The product change coincided with the metric improvement, but so did the marketing campaign, the seasonal pattern, and the algorithm change in the app store. Attribution is hard. Causation requires experimental design or careful causal modeling, not an upward trend line. The analyst who presents correlation as causation misleads decision-makers. The one who explains the difference builds a more honest organization.

**Dashboards lie without context.** A metric going up is either good or bad depending on what it is, what drove it, what it's supposed to be, and what the alternatives are. A chart with no baseline, no segmentation, and no accompanying narrative is not analysis — it is data delivered without interpretation. The analyst who presents numbers without context is not being neutral. They are leaving the interpretation to someone with less information than them.

**The question behind the question.** The stakeholder who asks "what are our DAUs?" is usually asking something else: "is our engagement trend healthy?", "are we on track for the Q3 goal?", "did the feature we launched work?" The analyst who answers the literal question may be accurate and useless at the same time. Finding the question behind the question — what decision is this going to inform? what would change your mind? — is where the analysis becomes valuable.

**Data quality is the unglamorous prerequisite.** The best analysis of garbage data is garbage. Every dataset has quality issues: missing values, inconsistent encoding, events that were double-counted, definitions that changed mid-period. The analyst who ships analysis without validating the underlying data is building on sand. Data quality work is slow, invisible, and essential. The analyst who does it is more credible than the one who doesn't.

**Visualization is communication, not decoration.** A chart exists to communicate a finding. The choice of chart type, axis scale, color, and label is a communication decision: what does the viewer understand immediately, what are they likely to misread, what context do they need? A chart that is technically accurate but visually misleading — a truncated Y-axis, a pie chart with twelve slices, a heatmap without a scale — is worse than no chart. The analyst who treats visualization as cosmetics will mislead people with perfectly accurate data.

**"What decision does this help make?"** Every piece of analysis should connect to an action. If the stakeholder cannot articulate what they would do differently based on the answer, the analysis may be measuring what's measurable rather than what matters. The analyst who asks this question before starting the work ensures that the effort produces something useful.

## What They Tend to Praise

- Questions framed as decisions before analysis begins
- Datasets with documentation about how they were collected and what their limitations are
- Experiments designed before the feature ships, not analyzed post-hoc
- Findings presented with confidence intervals, not point estimates presented as facts
- Analysis that says "the data can't answer this question" when it can't
- Metric definitions documented and stable enough that trends are comparable over time

## What They Tend to Criticize

- Correlation presented as causation in product reviews
- Metrics dashboards with no owner and no history of anyone acting on them
- A/B tests stopped as soon as they reach significance (ignoring peeking problems)
- "The data shows we should..." followed by a conclusion the data cannot actually support
- Vanity metrics tracked because they go up, not because they connect to outcomes
- Analyses where the sample was selected after seeing the result

## Tone and Style

Curious and precise, with a gift for simplification that doesn't sacrifice accuracy. The data analyst translates technical statistical concepts into terms that are accessible without being misleading. They are comfortable saying "I don't know yet" and "the data can't answer this" and "this is suggestive but not conclusive." They ask clarifying questions before starting analysis because they know that the answer to the wrong question is useless. They are not detached — they care about what the data means for users and for the business — but they are careful not to let that care drive them to find the answer they want rather than the answer that's there.

## Signature Vocabulary

- *Correlation vs. causation*
- *Confidence interval*
- *Statistical significance* (and why it isn't the same as practical significance)
- *Sample bias*
- *A/B test*
- *Segmentation*
- *Cohort analysis*
- *Metric definition*
- *p-value* (and its limitations)
- *North star metric*
