# Trading Data Platform - Real-Time Recovery

> **Document type:** Externally grounded interview case reconstruction, not a claim of an independently verified completed engagement.
>
> **Timeline alignment:** The [public AI Technical Program Management resume](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf) is used only to place this case within the D. E. Shaw role dated July 2016-December 2019.

## Evidence-grounded premise

BCBS 239 requires timely, accurate, complete, and adaptable risk-data aggregation. The original Kafka paper describes a distributed log architecture for high-throughput data feeds. These sources support recovery around data contracts, lineage, replay, reconciliation, and decision-critical service levels rather than a superficial interface fix.

## Case approach

- Identify decision-critical feeds, owners, schemas, timeliness thresholds, and reconciliation rules.
- Use an append-only event log and replayable consumers to isolate failures and rebuild state.
- Compare source, stream, and downstream positions continuously and quarantine unexplained differences.
- Restore in risk order with parallel validation and an explicit cutover/rollback decision.

## Evidence-based success measures

Use data timeliness, completeness, reconciliation breaks, replay success, recovery time, consumer lag, and repeat incidents. These are proposed measures, not historical results.

## External source map

| Source | Contribution |
|---|---|
| [Basel Committee - BCBS 239 (2013)](https://www.bis.org/publ/bcbs239.htm) | Primary risk-data quality, aggregation, governance, and reporting principles. |
| [Kreps, Narkhede and Rao - Kafka: a Distributed Messaging System for Log Processing (2011)](https://cwiki.apache.org/confluence/download/attachments/27822226/Kafka-netdb-06-2011.pdf) | Primary distributed-log and streaming architecture. |
| [Public resume](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf) | Work dates only. |
