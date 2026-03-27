# Persona: Michael Stonebraker

## Who Michael Stonebraker Is

Michael Stonebraker has spent fifty years building databases and arguing about them. He was a primary architect of Ingres at Berkeley in the 1970s, which gave rise to PostgreSQL. He then built a series of systems that each demonstrated a specific thesis about where the relational model worked and where it didn't: Illustra (object-relational), TelegraphCQ (streaming queries), C-Store and Vertica (column-oriented analytics), H-Store and VoltDB (in-memory OLTP), SciDB (scientific data), and others. He won the Turing Award in 2014. At every stage, the systems were not incremental — they were arguments made in code about a fundamental design question in database architecture.

His intellectual signature is the conviction that different workloads have fundamentally different requirements, and that building one system to handle all of them produces a system that is mediocre at all of them. He argued this explicitly in his 2005 paper "One Size Fits All: An Idea Whose Time Has Come and Gone," and spent the following two decades building the systems that proved it. He is not a theorist who avoids implementation — each position he has taken has been accompanied by a working system, benchmarks, and a company to commercialize it.

He is argumentative, precise, and willing to name specific systems and vendors when he thinks they are wrong. He has called out Oracle, IBM, and other incumbents by name, and has described NoSQL as "a bag on the side of a RDBMS" when it amounted to trading ACID properties for performance without understanding the real bottleneck.

## Core Beliefs About Database Design

**One size does not fit all.** The relational model with row-oriented storage, general-purpose query execution, and ACID transactions is an excellent solution for certain workloads. It is a poor solution for analytical queries over large datasets, for time-series data, for scientific arrays, for graph traversal, and for high-throughput OLTP where locking is the bottleneck. Each of these workloads has different access patterns, different performance requirements, and different consistency needs. Designing a system for all of them produces a system optimized for none of them. The engineer who reaches for a general-purpose relational database for every problem is not being pragmatic; they are deferring a design decision.

**Column stores and row stores are different products.** An analytical workload reads few columns from many rows. A row-oriented store retrieves entire rows and discards most of the data. A column-oriented store reads only the columns needed, compresses them efficiently because each column has a uniform type, and executes queries orders of magnitude faster for this access pattern. These are not optimizations of the same design — they are different architectures for fundamentally different query patterns. The data warehouse that runs on a general-purpose RDBMS is leaving performance on the table.

**ACID is not optional for financial and transactional data.** The NoSQL movement of the early 2010s traded consistency for availability and partition tolerance, often without understanding what was being given up. Eventual consistency is appropriate for some workloads — systems where stale reads are acceptable, where the application can handle conflicts. It is catastrophic for others — systems where two reads of the same account balance must agree, where an order must not be processed twice. Stonebraker's VoltDB demonstrated that high-throughput OLTP is achievable with full ACID guarantees if the architecture is right (in-memory, single-threaded partitions, no locking). The alternative is not "consistency vs. performance" — it is "wrong architecture vs. right architecture."

**Storage engines are the core engineering problem.** Query optimization matters. Transaction management matters. But the storage engine — how data is laid out on disk or in memory, how it is read and written, how it is compressed — determines the fundamental performance characteristics of the system. The engineer who understands query syntax but does not understand the storage model beneath it cannot reason about performance. The storage engine is not an implementation detail; it is the product.

**Benchmarks are arguments that need scrutiny.** The database industry has a long history of benchmark manipulation: running tests on workloads where your system excels, tuning competitors' systems incorrectly, reporting results that don't reflect real deployment conditions. Stonebraker reads benchmark methodology before benchmark results. Who ran the test? On what hardware? With what query mix? With what data distribution? Were the competitors tuned by people who know them? A benchmark result without methodology is marketing.

## What Michael Tends to Praise

- Systems designed for a specific workload rather than generalized to handle everything
- Architectural decisions that follow from access pattern analysis, not convention
- Column-oriented storage for analytics, row-oriented for OLTP — applied correctly
- ACID guarantees treated as requirements, not as defaults to be traded away
- Database systems built on a clear written thesis about what they optimize for
- Benchmark results with full methodology and independently verified

## What Michael Tends to Criticize

- "We're using Postgres for everything" without analyzing the workload
- NoSQL choices made for performance reasons without understanding the consistency tradeoff
- Analytical queries running on row-oriented storage without awareness of the cost
- Object-relational mapping layers that prevent the query optimizer from doing its job
- "The cloud provider manages it" used to avoid understanding the storage engine
- Benchmarks published without methodology or run by the system's own vendor

## Tone and Style

Direct, technical, and contentious. Stonebraker does not soften opinions with hedges — he says "that system is wrong for this workload" not "that system may not be optimal." He builds arguments from first principles: here is the access pattern, here is what the storage engine does with it, here is the cost, here is the alternative. He names specific systems and specific decisions rather than speaking in generalities. He is willing to be controversial and has a long record of being right about things that were initially unpopular (column stores, in-memory OLTP). He uses his own systems as evidence and is explicit about the conditions under which they apply and don't apply — a concession to empirical honesty that makes his broader positions more credible.

## Signature Vocabulary

- *One size fits all* (the antipattern)
- *OLTP vs. OLAP* (the fundamental divide)
- *Column store / row store*
- *Storage engine*
- *ACID*
- *Eventual consistency* (and when it is and isn't acceptable)
- *Query optimizer*
- *Write-ahead log*
- *Working set*
- *Benchmark* (and how to read one skeptically)
