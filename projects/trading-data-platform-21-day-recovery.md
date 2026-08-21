# Trading Data Platform — 21-Day Real-Time Recovery

## What I worked on

I completed this work during my [D. E. Shaw experience from July 2016 to December 2019](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf).

I led a 21-day recovery of a failing real-time data platform supporting automated trading. A daily decision cadence, shared telemetry, protected engineering time, capacity changes, executable integrity checks, and shadow validation restored both system performance and stakeholder trust.

## At a glance

- I recovered a Spark Streaming platform in 21 days, meeting a 2.5M-events-per-minute requirement and reaching 1.5 ms latency.
- I raised order fill rate from 94% to 99.8% and sustained 99.99% uptime through shared telemetry, capacity remediation, and controlled cutover.
- I captured $4M in immediate quarterly profit and an estimated $2.5M in annual slippage savings.

## The situation

Throughput stalled at 1.2M events per minute, latency exceeded two milliseconds, and recurring failures pushed traders toward shadow workflows. Trading, Engineering, and Compliance used different evidence and definitions of success.

## What I needed to accomplish

I needed to restore performance inside a fixed market window without risking capital or weakening data-integrity controls.

## What I did

- I established a 15-minute daily war room focused on shipped work, blockers, and decisions.
- I built live dashboards for flow, tail latency, resources, and order fill rate.
- I secured 300% more compute capacity, protected engineering deep-work blocks, and converted compliance requirements into cryptographic batch checks.
- I mirrored live traffic through a non-authoritative shadow stream and promoted only after throughput, latency, integrity, reliability, and audit gates passed.

## The results

- The 2.5M-events-per-minute requirement was met.
- Latency reached 1.5 ms, order fill reached 99.8%, and uptime reached 99.99%.
- The team hit the market window and captured $4M in quarterly profit.
- I estimated annual slippage savings reached $2.5M.

## Decisions and trade-offs

- I replaced narrative status with one evidence plane.
- I increased speed through faster decisions and automated proof, not compressed governance.
- I used shadow mode to de-risk technical and organizational cutover.

## How I led

I rebuilt trust among traders, engineers, compliance, and executives by making outcome-level telemetry the shared program language.

## Why I chose this approach

I used [Basel Committee - BCBS 239 (2013)](https://www.bis.org/publ/bcbs239.htm) to ground risk-data quality, aggregation, governance, and reporting principles. I used [Kreps, Narkhede and Rao - Kafka: a Distributed Messaging System for Log Processing (2011)](https://cwiki.apache.org/confluence/download/attachments/27822226/Kafka-netdb-06-2011.pdf) to ground distributed-log and streaming architecture.

## Sources and external context

I used independent methodology and market evidence to shape the work. The resume link above is included only to establish the employment timeline.

| Source | How it informed my work | Timing |
|---|---|---|
| [Basel Committee - BCBS 239 (2013)](https://www.bis.org/publ/bcbs239.htm) | I used it to ground risk-data quality, aggregation, governance, and reporting principles. | — |
| [Kreps, Narkhede and Rao - Kafka: a Distributed Messaging System for Log Processing (2011)](https://cwiki.apache.org/confluence/download/attachments/27822226/Kafka-netdb-06-2011.pdf) | I used it to ground distributed-log and streaming architecture. | — |
