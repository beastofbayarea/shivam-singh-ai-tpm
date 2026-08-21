# Managing a Global HPC Fleet as an Investment System

I built this lifecycle program during my [D. E. Shaw experience from July 2016 to December 2019](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf).

A high-performance computing fleet can look efficient from one vantage point and wasteful from another. Engineering sees latency and headroom. Finance sees invoices and depreciation. Operations sees incidents. Security sees asset and intellectual-property risk. I wanted one model that could follow an asset from purchase through deployment, tuning, relocation, and secure retirement—and show whether it still created economic value.

## The signals did not agree

Raw utilization was a poor proxy for usefulness. Some machines appeared lightly used while supporting high-value, latency-sensitive activity. Others consumed power and support without contributing to profitable execution. A 17-minute incident made the reliability cost visible, while the later appearance of an FPGA in a resale channel exposed the risk of treating disposal as a logistics task.

I therefore connected five kinds of evidence:

- network behavior, including packet loss, buffer depth, topology, and latency;
- hardware behavior, including temperature and stability;
- workload criticality and location sensitivity;
- vendor, power, and support cost; and
- contribution to profitable trading execution.

That changed the discussion from “Is the server busy?” to “Is this configuration producing sufficient reliability-adjusted value?”

## I gave every lifecycle decision a gate

For new or changed configurations, I introduced functional, volume, thermal, reliability, and canary checks. Google SRE's treatment of user-facing signals influenced the telemetry model, while NIST SP 800-53 informed the control structure around configuration, maintenance, contingency, and auditability.

I used those gates to reject overclocking changes when a marginal latency improvement created disproportionate heat and instability. I also required 10x stress conditions before high-risk changes could graduate. Performance was valuable only if the fleet could sustain it through abnormal market volume.

For existing capacity, I divided workloads by latency sensitivity and economic contribution. I removed inactive machines, identified over-provisioned capacity, and relocated latency-insensitive work where it could run more economically without changing trading profit.

## Retirement became a controlled technical workflow

The resale incident showed that a decommissioning ticket was not sufficient evidence of closure. I designed retirement around cryptographic erasure, physical destruction when policy required it, documented chain of custody, inventory reconciliation, and finance-system closure.

I treated an asset as retired only when the technical, physical, security, and financial records agreed. This was as important as the purchasing gate: unmanaged end-of-life assets could expose proprietary logic long after they stopped appearing on an infrastructure dashboard.

## What the system delivered

- Annual operating cost fell by $1.2 million, including about $100,000 in immediate monthly savings.
- I removed 40 inactive servers and identified 15% of the fleet as over-provisioned.
- A London topology change reduced latency by 400 nanoseconds.
- The fleet sustained 99.999% uptime through a 400% surge in market-data volume.

The result was not a one-time cost reduction. Engineering, finance, operations, vendors, and security could now make lifecycle choices using the same evidence and close the loop after each change.

## My operating principle

I do not manage infrastructure cost separately from workload value. Capacity, resilience, performance, and retirement are parts of the same product system. The best decision is the one that improves the value of the whole system after reliability and risk are included—not simply the one with the lowest invoice or fastest benchmark.

## External foundations

The following sources supplied the control and reliability methodology. My resume is linked only to establish the period in which I did the work.

| Source | How I applied it |
|---|---|
| [Google SRE — Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/) | I used its service-signal approach to keep telemetry tied to consequential operating behavior. |
| [NIST — SP 800-53 Revision 4 (2015)](https://csrc.nist.gov/pubs/sp/800/53/r4/upd1/final) | I used its configuration, maintenance, contingency, media-protection, and audit-control families to structure lifecycle gates and closure evidence. |
