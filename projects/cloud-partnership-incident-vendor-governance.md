# Recovering a cloud partnership when technical trust had collapsed

Twenty startups, roughly one million end users, and about $10 million in annual cloud spend sat inside one partnership—but the crisis was not one incident.

A fintech estimated $500,000 lost during a two-hour event. An analytics company saw engagement fall 15%. Three provider APIs were late. Founders wanted remedies, engineers wanted stability, the provider wanted architectural time, and account leaders wanted to preserve the relationship.

In Microsoft’s regulated-cloud organization, I led the recovery across startup founders, their engineers and customers, Microsoft product, support and account teams, the cloud provider, finance, procurement, legal counsel, and executives. I converted 20 different failure experiences into one prioritized recovery without erasing their distinct causes or impact.

## Ledger one: restore service from the user backward

I established a shared operating view for availability, saturation, database capacity, latency, errors, changes, and recovery. Startup-side and provider-side telemetry had to reconcile at agreed boundaries. A contractual SLA could not substitute for the user’s experience.

The technical review exposed a coupled chain: load-balancer behavior, an under-provisioned database tier, incomplete autoscaling, weak anomaly detection, and delayed upgrades. I separated provider infrastructure, startup configuration, and jointly agreed reference architecture so no party could hide behind a blended “shared responsibility” label.

Recovery followed customer harm:

- **Days 1–14:** stabilize traffic, database headroom, alerting, and incident communication.
- **Weeks 3–6:** deliver three delayed APIs and finish priority database/integration work.
- **Months 2–3:** prove redundant architecture, representative load, and repeatable recovery.

I secured a $250,000 package and two engineers, each tied to failure modes and exit criteria rather than generic hardening.

## Ledger two: make every promise acceptably complete

The three delayed APIs entered a commitment register with scope, technical owner, dependency, customer, acceptance test, date, and escalation trigger. All three were delivered within 30 days.

A weekly founder forum handled material changes and commercial confidence; a working technical cadence handled evidence and blockers. Founders did not need every implementation detail, but they needed to know which promise changed, why, who owned it, and what proof would close it. Engineers needed fast decisions without renegotiating the partnership at every stand-up.

“Delivered” meant customer acceptance against the agreed test, not provider code completion.

## Ledger three: negotiate accountability without waiting for perfect causality

Technical remediation and commercial remedy ran in parallel. Waiting for unanimous root cause would have delayed accountability; negotiating credits without fixing the system would have purchased temporary silence.

The provider agreed to a 15% concession. Applied mechanically to the recorded $10 million annual relationship, that represents $1.5 million of gross annual contract value. It is not cash received, startup revenue restored, or loss avoided; executed terms, eligible spend, period, and billing realization determine the actual benefit.

## The evidence required to leave incident mode

I would call the partnership recovered only when five independent claims held:

1. **Observed service stability:** 99.9% recorded availability over the recovery window, backed by reconciled telemetry. The window is missing, so I do not present this as annual performance.
2. **Stronger future obligation:** a 99.95% availability commitment in service terms. A commitment is not measured performance.
3. **Delivery closure:** three APIs accepted within 30 days.
4. **Funded remediation:** $250,000 and two engineers assigned to named work.
5. **Commercial accountability:** a 15% concession executed and realized through the contract.

Over 365 days, 99.9% permits about 8 hours 46 minutes of downtime; 99.95% permits about 4 hours 23 minutes. Without the observation period, the percentages cannot be compared honestly.

## The temporary command center became permanent governance

I converted the recovery into a quarterly provider scorecard covering:

- availability, latency, and error performance;
- high-severity incidents, detection, and restoration;
- saturation, capacity, failover, and load-exercise evidence;
- overdue product commitments and acceptance status;
- support response and recurring problems;
- commercial remedies and contract realization; and
- founder confidence by company, not only portfolio average.

Every measure required a source, denominator, time window, owner, and decision.

Google’s [SRE guidance on monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) informed the separation between user-facing symptoms and system causes. [BCBS operational-resilience principles](https://www.bis.org/bcbs/publ/d516.htm) were useful for challenging concentration and third-party dependency where relevant; I do not claim all 20 startups were governed by Basel requirements.

I owned impact triage, evidence standards, recovery sequencing, cross-company cadence, executive escalation, the resource case, commercial-workstream coordination, and the permanent vendor scorecard. Engineers owned changes in their systems; the provider owned its platform and promises; procurement and legal owned amendments; startup leaders owned customer decisions.

The program’s enduring result was not a green incident status. It was a relationship in which reliability, product delivery, and commercial accountability became separately measurable—and therefore jointly governable—after the crisis team left.
