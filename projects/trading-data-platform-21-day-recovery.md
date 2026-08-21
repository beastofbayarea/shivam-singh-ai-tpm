# A 21-day recovery of the trading-data platform

The primary path processed about 1.2 million events per minute against a stated need of 2.5 million. Resource failures and restarts were recurring, latency deteriorated during market stress, and trading teams had built shadow tools because confidence in the platform had collapsed.

At D. E. Shaw, I led the 21-day recovery across traders, quantitative researchers, data/platform engineering, infrastructure, risk, controls, finance, and senior technology leadership. My job was not to make Spark jobs appear green; it was to transfer decision authority back to the primary path using evidence both traders and engineers accepted.

## Day zero: define who could declare recovery

I established five independent promotion gates:

1. **Scale:** sustain 2.5 million events per minute with headroom.
2. **Speed:** meet a fixed event-to-decision latency boundary and percentile.
3. **Integrity:** prove completeness, schema validity, ordering, duplicate handling, quarantine, and replay.
4. **Trading usefulness:** reproduce eligible signals and fills within agreed tolerance.
5. **Operability:** survive worker, driver, and dependency faults with accountable recovery.

The temporary shadow stream remained read-only and non-authoritative. It provided continuity and comparison, not a second production truth.

## Hours 0–72: join technical symptoms to economic consequence

I replaced fragmented reporting with a 15-minute daily decision meeting and one Grafana view overlaying event flow, delay, saturation, restarts, market activity, signals, fills, and changes. A trader could identify a harmed interval and an engineer could trace the same interval through the data path.

Every blocker left with one disposition: fix now, run a bounded experiment, or escalate a capacity/priority decision. I protected four-hour engineering blocks from meetings because incident management that consumed the repair team would extend the incident.

## Days 4–10: create headroom, then prove it was real

I secured “300% more compute” within 24 hours. The phrase is ambiguous—it may mean 3× total or a 300% increase to 4×—so I retain it without inventing node count.

Engineering rebalanced partitions and executors, tuned memory and backpressure, isolated unstable workloads, and removed restart triggers. Capacity was not an exit condition: a larger cluster could move the bottleneck or hide a leak. Sustained load had to show stable resource curves, bounded queues, and controlled errors.

## Days 11–17: make data integrity executable

For each batch, the platform compared expected and observed counts, schema, time range, key fields, and cryptographic hashes where identical representation made hashing meaningful. Suspect data entered quarantine. Replay and reconciliation proved whether recovery reproduced the same logical result.

The [Spark Streaming programming guide](https://spark.apache.org/docs/latest/streaming-programming-guide.html) distinguishes fault tolerance for input, transformations, and output; output is at-least-once unless the sink is idempotent or transactional. I therefore did not allow “Spark replayed it” to become an unsupported end-to-end exactly-once claim.

## Days 18–21: shadow, compare, transfer authority

The recovered path processed the same market periods as the reference without making decisions. Teams compared throughput, latency distribution, integrity exceptions, signal differences, fill eligibility, restarts, and operator intervention.

Traders and platform owners jointly approved promotion. Workaround retirement was a separate controlled change so recovery did not create a new cutover incident.

## The recovery record

- **Throughput:** 1.2M → 2.5M events/minute target → 2.5M achieved. Method: accepted events in consistent one-minute windows under representative load. Result: +1.3M, +108.3%, 2.083× baseline.
- **Latency:** >2 ms baseline → fixed decision-path target → 1.5 ms observed. A separate “70% below crisis peak” statement implies ~5 ms, but that peak and timestamp boundary are not retained. I report the achieved value, not a fabricated baseline reduction.
- **Fill rate:** 94% → restore decision usefulness → 99.8%. Method: completed eligible fills / eligible opportunities in the comparison window. Result: +5.8 points, ~6.2% relative.
- **Availability:** baseline unstable → controlled recovery → 99.99% reading. Observation window absent, so it is not presented as annual uptime or an SLA.
- **Authority transfer:** platform untrusted → pass five gates → jointly promoted in 21 days.

## Economics remained in three separate accounts

The recovered quarter is associated with approximately $4 million of profit. Trading P&L also depends on market opportunity, models, risk, and execution, so I present this as performance during the recovered period—not profit caused solely by the platform program.

The source also models ~$2.5 million of annual slippage savings and ~$1.5 million of avoided downtime loss. The first needs volume, price benchmark, counterfactual, and persistence; the second needs outage probability and loss-rate assumptions. Neither is booked value, and neither is added to the $4 million.

I owned promotion gates, incident cadence, protected engineering time, capacity escalation, cross-functional evidence, financial classification, and transfer to normal governance. Engineers owned implementation; traders defined the economically meaningful boundary; infrastructure owned capacity; risk/control owned exceptions; finance owned value definitions.

The durable result was institutional, not merely technical. The firm gained a repeatable way to decide when a real-time data path deserved trust: system telemetry connected to trading consequence, integrity controls that executed rather than documented intent, explicit fault semantics, and joint authority to promote or reject the platform.
