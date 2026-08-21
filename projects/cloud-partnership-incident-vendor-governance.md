# Recovering a Cloud Partnership After Reliability Broke Trust

I led this recovery during my [Microsoft experience from January 2020 to August 2022](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf).

The cloud relationship was worth $10 million annually and supported 20 startups serving roughly one million users. It was also failing in two different ways. The services were unstable, and the vendor's reporting made it difficult to see what was actually happening. A technical repair alone would leave the same accountability gap in place; a contract negotiation alone would not restore service.

## Two incidents made the cost concrete

Outages, delayed APIs, weak load balancing, constrained database capacity, and incomplete autoscaling had accumulated. One fintech lost $500,000 in two hours. Another portfolio company saw engagement decline 15%. Three promised APIs were late.

I treated those facts as customer and business impacts, not a collection of disconnected tickets. They gave the recovery a common priority model: immediate customer loss, regulatory dependency, data-integrity exposure, and the number of companies sharing the affected component.

## I established an independent evidence plane

The first operating change was to stop relying on provider-authored summaries. I brought together startup reports, service logs, configurations, capacity measures, and delivery commitments to reconstruct the incident timeline. That gave engineering teams and commercial leaders the same version of events.

Google's SRE guidance shaped the monitoring discipline: I focused the shared view on signals that described user-facing behavior and required an action. Basel's operational-resilience principles shaped the wider recovery model—critical operations, impact tolerances, dependency mapping, response, and learning.

## The recovery ran on two synchronized tracks

On the technical track, I coordinated fixes for load balancing, autoscaling, database capacity, redundancy, anomaly detection, and the three delayed APIs. Every phase had exit evidence. I also insisted that validation represent the portfolio's real operating conditions—market spikes, flash sales, and streaming loads—rather than a convenient average-load test.

On the commercial track, I documented verified service-level breaches, dated roadmap commitments, decision owners, and remedies. I escalated the evidence to provider executives and tied the next review and renewal discussion to a jointly visible scorecard.

The scorecard was deliberately small. It covered availability, recovery behavior, capacity headroom, API delivery, unresolved risk, and contractual performance. Its purpose was to prompt decisions, not create another reporting ritual.

## How I kept 20 companies aligned

I used a concise daily update during stabilization and moved to weekly governance as risk declined. Each update separated what had happened, current customer impact, work completed, remaining uncertainty, the next decision, and its owner. Startup teams could see progress without joining every technical session, while engineers could work without repeated ad hoc escalations.

## The recovery outcome

- Uptime returned to 99.9%.
- All three delayed APIs shipped within 30 days.
- A 15% contract concession saved $1.5 million annually.
- Independent performance evidence replaced trust-based vendor summaries as the basis for governance.

The concession mattered, but the more durable result was a different relationship. Reliability, delivery, and commercial accountability were now managed through observable evidence.

## What this changed in my program practice

When a partner operates part of the customer experience, vendor management is part of service design. I now establish the telemetry, impact model, escalation path, and commercial consequences before a major incident forces those conversations.

## External foundations

These sources provided the primary operating methodology. The resume link establishes employment chronology only.

| Source | How I applied it |
|---|---|
| [Basel Committee — Principles for operational resilience (2021)](https://www.bis.org/bcbs/publ/d516.pdf) | I used its focus on critical operations, tolerances, dependencies, response, and learning to frame the recovery beyond infrastructure repair. |
| [Google SRE — Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/) | I used its monitoring principles to build an actionable, customer-facing evidence plane rather than accept broad provider summaries. |
