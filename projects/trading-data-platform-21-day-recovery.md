# Trading Data Platform — 21-Day Real-Time Recovery

> **Portfolio lens:** Incident delivery, shared telemetry, launch gates, cross-functional recovery, and performance governance.

## Executive snapshot

Led a 21-day recovery of a failing real-time data platform supporting automated trading. A daily decision cadence, shared telemetry, protected engineering time, capacity changes, executable integrity checks, and shadow validation restored both system performance and stakeholder trust.

## Resume-ready impact

- Recovered a Spark Streaming platform in 21 days, meeting a 2.5M-events-per-minute requirement and reaching 1.5 ms latency.
- Raised order fill rate from 94% to 99.8% and sustained 99.99% uptime through shared telemetry, capacity remediation, and controlled cutover.
- Captured $4M in immediate quarterly profit and an estimated $2.5M in annual slippage savings.

## Interview story

### Situation

Throughput stalled at 1.2M events per minute, latency exceeded two milliseconds, and recurring failures pushed traders toward shadow workflows. Trading, Engineering, and Compliance used different evidence and definitions of success.

### Task

Restore performance inside a fixed market window without risking capital or weakening data-integrity controls.

### Actions

- Established a 15-minute daily war room focused on shipped work, blockers, and decisions.
- Built live dashboards for flow, tail latency, resources, and order fill rate.
- Secured 300% more compute capacity, protected engineering deep-work blocks, and converted compliance requirements into cryptographic batch checks.
- Mirrored live traffic through a non-authoritative shadow stream and promoted only after throughput, latency, integrity, reliability, and audit gates passed.

### Results

- The 2.5M-events-per-minute requirement was met.
- Latency reached 1.5 ms, order fill reached 99.8%, and uptime reached 99.99%.
- The team hit the market window and captured $4M in quarterly profit.
- Estimated annual slippage savings reached $2.5M.

## Decisions and trade-offs

- Replace narrative status with one evidence plane.
- Increase speed through faster decisions and automated proof, not compressed governance.
- Use shadow mode to de-risk technical and organizational cutover.

## Leadership signal

Rebuilt trust among traders, engineers, compliance, and executives by making outcome-level telemetry the shared program language.

## Skills and keywords

incident management · technical program management · Spark Streaming · war room · shared telemetry · shadow validation · release gates · capacity planning · compliance · low latency

## Source

[Original Notion project page](https://app.notion.com/p/15bf9e255f2180b6b913f715959a041f)

