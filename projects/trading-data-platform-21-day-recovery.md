# A 21-Day Recovery for a Real-Time Trading Data Platform

I led this recovery during my [D. E. Shaw experience from July 2016 to December 2019](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf).

The platform needed to process 2.5 million events per minute, but throughput had stalled at 1.2 million and latency had moved beyond two milliseconds. Recurring failures were pushing traders toward shadow workflows. The technical problem was serious; the more immediate program problem was that Trading, Engineering, and Compliance did not share the same evidence or even the same definition of “ready.”

We had 21 days to recover the platform inside a fixed market window without putting capital or data integrity at risk.

## Day one: one outcome board, one decision rhythm

I created a 15-minute daily session around three questions: What changed in production evidence? What is blocked? What decision is needed today? The session was short because its job was to unblock work, not describe activity.

I also replaced competing reports with live views of event flow, tail latency, resource behavior, order-fill rate, and integrity checks. Basel Committee guidance on risk-data aggregation influenced this choice: trustworthy, timely, complete evidence had to be available to the people making risk-sensitive decisions.

## I removed three different constraints

The recovery was not one tuning exercise. I separated it into capacity, focus, and proof.

First, I secured 300% more compute capacity so engineering could test the target envelope instead of optimizing inside an artificial ceiling. Second, I protected deep-work blocks, which stopped engineers from losing the day to fragmented escalation meetings. Third, I translated compliance requirements into executable cryptographic batch checks. That made integrity evidence repeatable and kept governance inside the delivery loop.

The original Kafka paper provided a useful architectural foundation for reasoning about a distributed log, consumer behavior, and streaming throughput. I used that foundation alongside observed bottlenecks rather than assuming that more hardware alone would solve flow and latency.

## Shadow traffic made the cutover reversible

I mirrored live traffic through a non-authoritative stream and compared the new path with production behavior. The shadow path could process realistic volume and reveal divergence without controlling orders.

Promotion required five gates:

1. target throughput under representative load;
2. latency within the agreed boundary, including the tail;
3. cryptographic integrity checks passing;
4. stable recovery and uptime behavior; and
5. audit evidence accepted by Compliance.

If any gate failed, the team had specific evidence to investigate; we did not compress governance to meet the date.

## What happened by day 21

- Throughput reached the 2.5-million-events-per-minute requirement.
- Latency reached 1.5 milliseconds.
- Order fill improved from 94% to 99.8%.
- Uptime reached 99.99%.
- The market window produced $4 million in immediate quarterly profit.
- I estimated that improved execution reduced annual slippage by $2.5 million.

## The recovery mechanism that mattered most

Additional capacity was necessary, but the shared evidence plane changed the program. Traders could see whether execution improved. Engineers could locate resource and flow constraints. Compliance could verify integrity through executable controls. Executives could make decisions from outcomes rather than narrative status.

That is the operating model I carry into high-pressure programs: shorten the time from evidence to decision, protect the people doing the work, and make the release safer through observable, reversible transitions.

## External foundations

These sources supplied the primary data-governance and streaming methodology. The resume link is used only for employment chronology.

| Source | How I applied it |
|---|---|
| [Basel Committee — Principles for effective risk data aggregation and risk reporting (BCBS 239, 2013)](https://www.bis.org/publ/bcbs239.htm) | I used its emphasis on accurate, complete, timely, and adaptable risk data to create one decision-grade evidence plane. |
| [Kreps, Narkhede and Rao — Kafka: a Distributed Messaging System for Log Processing (2011)](https://cwiki.apache.org/confluence/download/attachments/27822226/Kafka-netdb-06-2011.pdf) | I used its distributed-log model to reason about throughput, consumers, and shadow-stream validation. |
