# Amazon Inventory Signals — Streaming Data & Regional Fulfillment

> **Portfolio lens:** Streaming modernization, program scope, dependency management, resilient rollout, and cross-functional delivery.

## Executive snapshot

Led the data-program layer enabling a national-to-regional fulfillment transformation. Streaming ingestion, distributed processing, real-time quality rules, a scoped data-quality MVP, and a parallel major-vendor integration connected data integrity to physical delivery speed.

## Resume-ready impact

- Led a supply-chain data modernization that reduced inventory-signal latency from 38 hours to under five minutes and errors from 8% to 0.5%.
- Resolved a resource deadlock by reducing the data-quality roadmap 60% around the two defects causing 80% of vendor pain, freeing a tiger team for a critical integration.
- Supported 76% regional fulfillment, generated more than $1M in annual savings, reduced support tickets 25%, and protected a major vendor's $50M+ GMV.

## Interview story

### Situation

The physical network had reached a speed ceiling, but vendor inventory signals arrived late and wrong. Operations, Sales, and Product had competing commitments, and brownfield facilities added implementation risk.

### Task

Deliver a trustworthy real-time signal platform and regional rollout without abandoning an announced product or a high-value customer dependency.

### Actions

- Traced one vendor update through FTP, Oracle, manual validation, and downstream decisions to expose the actual bottleneck.
- Replaced batch transfers with Kafka/MSK, Airflow, Spark, and real-time quality checks.
- Scoped the MVP by the concentration of customer pain and delivered the vendor integration in parallel.
- Tested the hardest region first and treated regionalization as a resilience architecture, not only a cost initiative.

### Results

- Latency fell below five minutes, and error rate fell to 0.5%.
- Support tickets declined 25%, and annual savings exceeded $1M.
- Regional fulfillment reached 76%.
- The major-vendor integration shipped two days early and protected more than $50M in GMV.

## Decisions and trade-offs

- Resolve the schedule conflict through evidence-based scope reduction, not by cancelling one workstream.
- Use the most operationally difficult region as the first scale gate.
- Pause a failing brownfield robotics rollout and recover through software rather than expensive facility reconstruction.

## Leadership signal

Aligned operations, sales, data, product, vendors, and regional delivery teams around measurable latency, accuracy, customer, and fulfillment outcomes.

## Skills and keywords

technical program management · streaming data · dependency management · scope governance · regional fulfillment · launch gates · resilience · vendor integration · Spark · Kafka

## Source

[Original Notion project page](https://app.notion.com/p/2f7f9e255f2180288b56d78e67b04386)

