# Regulated FinTech Cloud — Regional Architecture & Data Sovereignty

> **Portfolio lens:** Regulated-cloud delivery, regional architecture, performance SLOs, compliance controls, and multi-market launch.

## Executive snapshot

Led two linked regulated-cloud recoveries: a time-critical trading workload and a ten-market sovereignty launch. Workload-priority lanes, data-layout changes, regional pods, immutable records, customer-controlled keys, and de-identified reporting became a reusable delivery playbook.

## Resume-ready impact

- Recovered a regulated trading workload from six-hour reconciliation to 480 ms, saving and expanding a cloud contract from $5M to $7M.
- Replaced a centralized architecture carrying $25M in regulatory exposure with automated regional pods for ten jurisdictions.
- Reduced reporting time from two hours to ten minutes, lowered reporting CPU roughly 40%, and launched all ten markets with clean audits.

## Interview story

### Situation

One client treated critical trading and routine reporting as equal queue traffic; another attempted to move regulated European and Chinese data through a U.S.-hosted monolith.

### Task

Meet hard performance and jurisdiction requirements while preserving global operational visibility and a repeatable deployment mechanism.

### Actions

- Introduced preemptive fast lanes for trade and risk work while moving reporting to a separate serverless path.
- Localized compute, storage, encryption, consent, retention, and audit controls by jurisdiction.
- Implemented WORM retention, customer-managed HSM keys, and row-level cross-border permission checks.
- Allowed only approved, de-identified signals to leave regional pods.

### Results

- Critical-query latency reached 480 ms.
- Reporting fell to ten minutes and supported 500 concurrent analysts.
- Ten sovereign deployments launched with zero audit exposure.
- The renewed contract expanded to $7M.

## Decisions and trade-offs

- Standardize deployment automation and evidence, not jurisdictional policy.
- Pause the multi-market launch when centralization became legally unsafe.
- Provide global risk insight through de-identification rather than identity export.

## Leadership signal

Coordinated architecture, security, compliance, client, and commercial teams around explicit SLO and jurisdiction gates, turning regulatory constraints into reusable program requirements.

## Skills and keywords

sovereign cloud · technical program management · data residency · regional architecture · SLO · WORM · HSM · compliance delivery · multi-market launch · risk governance

## Source

[Original Notion project page](https://app.notion.com/p/2fbf9e255f2180028abcfb9a0c9a852a)

