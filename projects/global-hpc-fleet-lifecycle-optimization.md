# Global HPC Fleet — Lifecycle Cost & Reliability Optimization

## What I worked on

I completed this work during my [D. E. Shaw experience from July 2016 to December 2019](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf).

I created a closed-loop lifecycle control system for a global high-performance computing fleet. The program linked hardware telemetry and trading P&L to purchasing, deployment, tuning, relocation, retirement, and secure disposal decisions.

## At a glance

- I reduced annual HPC operating cost $1.2M by joining technical telemetry, vendor billing, and profitable-execution evidence.
- I removed 40 inactive servers, identified 15% of the fleet as over-provisioned, and relocated latency-insensitive workloads without reducing trading profit.
- I introduced 10x stress tests and secure retirement controls, sustaining 99.999% uptime through a 400% market-data surge.

## The situation

Engineering optimized speed, Finance optimized invoices, and Operations reacted to failures without a shared model of lifecycle value. A 17-minute incident and later FPGA resale exposed both reliability and intellectual-property risk.

## What I needed to accomplish

I needed to manage the fleet as an economic and operational system from capital request through secure end-of-life.

## What I did

- I connected buffer depth, packet loss, topology, temperature, and latency to trade profitability and fully loaded cost.
- I created functional, volume, thermal, reliability, and canary gates before rollout.
- I rejected overclocking changes whose heat and instability outweighed a marginal latency gain.
- I implemented cryptographic erasure, physical destruction where required, chain of custody, and finance-system closure.

## The results

- Annual OpEx fell $1.2M, including roughly $100K in immediate monthly savings.
- Forty inactive servers were removed, and 15% of the fleet was identified as over-provisioned.
- A London topology change reduced latency 400 nanoseconds.
- The fleet sustained 99.999% uptime through a 400% volume surge.

## Decisions and trade-offs

- I evaluated economic utilization rather than raw CPU activity.
- I rejected faster configurations when reliability-adjusted value is negative.
- I treated retirement as incomplete until technical, physical, and financial controls close.

## How I led

I created a shared decision model for engineering, finance, operations, vendors, and security, turning infrastructure lifecycle work into an observable investment discipline.

## Why I chose this approach

I used [Google SRE - Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/) to ground monitoring and service-signal methodology. I used [NIST - SP 800-53 Revision 4 (2015)](https://csrc.nist.gov/pubs/sp/800/53/r4/upd1/final) to ground configuration, maintenance, contingency, and audit-control framework.

## Sources and external context

I used independent methodology and market evidence to shape the work. The resume link above is included only to establish the employment timeline.

| Source | How it informed my work | Timing |
|---|---|---|
| [Google SRE - Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/) | I used it to ground monitoring and service-signal methodology. | — |
| [NIST - SP 800-53 Revision 4 (2015)](https://csrc.nist.gov/pubs/sp/800/53/r4/upd1/final) | I used it to ground configuration, maintenance, contingency, and audit-control framework. | — |
