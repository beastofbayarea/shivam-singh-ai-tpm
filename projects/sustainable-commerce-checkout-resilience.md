# Making sustainable shopping trustworthy without putting payment at risk

The program contained two promises that had been coupled incorrectly.

A sustainability claim had to be specific, current, and understandable. Payment had to complete even when optional product enrichment failed. When an external carbon-data dependency slowed under viral demand, those promises collided: waiting checkout threads exhausted the service and put the transaction itself at risk.

During my AWS role, I directed a commerce program that joined shopper needs, Retail, Payments, sustainability specialists, certifiers, platform/reliability engineering, vendors, Support, Finance, and executives.

## The baseline exposed both product and platform failure

A 10,000-shopper survey found 58% concerned about greenwashing and 45% citing price as a barrier. Sustainable-category conversion had fallen from 2.8% historically to 1.9%. Mobile represented 60% of traffic but converted 22% below desktop. Overall checkout latency was 1.5 seconds, mobile was 4.2 seconds, and cart abandonment had risen from 25% to 45%.

I kept those as separate measures. Claim trust, page performance, transaction completion, category conversion, and commercial value had different owners and denominators.

At roughly 1,600 orders per second, the coupled design contributed to 45 minutes of failure and an estimated $3 million in lost orders. My mandate became both immediate and structural: contain the event, repair customers and vendor accountability, remove optional data from the critical path, prove regional resilience, and rebuild the sustainability evidence contract.

## Incident command

Viral demand and a DNS/TTL plus cache-miss pattern concentrated calls on the external service. Dependency latency rose from about 200 milliseconds to more than five seconds. Checkout threads waited, 504s followed, and transaction failure reached 15%.

I separated containment from correction.

**Containment:** route 75% of traffic to the legacy path. Transaction failure fell from 15% to 2%.

**Customer repair:** issue $10 credits to affected customers and give support a plain-language incident narrative.

**Vendor accountability:** negotiate $100,000 in fee relief. That remedy did not reverse the customer harm.

**Structural correction:** remove synchronous sustainability enrichment from payment authorization, inventory reservation, and order creation.

## The new dependency contract

Environmental evidence could enhance the shopping decision or enrich an order record, but it could not own payment availability.

The redesigned path used explicit timeouts and a circuit breaker that opened when more than 5% of requests exceeded 500 milliseconds; last-known-good evidence only where staleness was safe; omission where stale status could mislead; cell isolation and shuffle sharding; active-active capacity in Virginia and Oregon; and separate telemetry for customer latency, dependency latency, failures, cache behavior, and circuit state.

The breaker later activated 14 times without another recorded outage. That was meaningful operational evidence: degraded behavior had become designed and repeatable.

The [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) provides an external benchmark for soft dependencies, fail-fast behavior, bounded queues/retries, isolation, and tested recovery. The [Amazon Builders’ Library FAQ](https://aws.amazon.com/builders-library/faqs/) identifies shuffle sharding as an Amazon fault-isolation practice.

## The sustainability claim contract

I convened sustainability, product, legal, engineering, and certifiers to replace broad labels with claim-level evidence. Every eligible product required a named standard or certificate, current verification state, evidence owner, and shopper-facing language tied to that proof.

The [FTC Green Guides summary](https://www.ftc.gov/business-guidance/resources/environmental-claims-summary-green-guides) informed the discipline that broad environmental claims need qualification and substantiation. It did not certify the individual claims.

This made trust operational: a claim could expire or disappear without affecting checkout, and no cached label could remain visible if its evidence was unsafe to reuse.

## Result ledger

| Customer or business outcome | Baseline → target → recorded result | Method |
|---|---|---|
| Mobile checkout latency | 4.2 s → sub-second → 800 ms | Client-observed checkout boundary; 3.4 s and 81% lower |
| Mobile conversion | 0.8% → close mobile gap → 1.0% | Orders / eligible mobile sessions; +0.2 points, +25% relative |
| Sustainable-category conversion | 1.9% → recover toward 2.8% history → 2.2% | Orders / eligible category sessions; +0.3 points, +15.8% relative, still 0.6 points below history |
| Cart abandonment | 45% → recover toward 25% history → 30% | Started carts without orders; -15 points, -33.3% relative, still 5 points above history |
| Incident failure | 15% → contain rapidly → 2% | Failed transactions / attempts in incident window; -13 points |
| Dependency resilience | uncontrolled wait → bounded degradation → 14 breaker activations, no recorded outage | Circuit events joined to transaction health and post-event review |

A post-remediation 99.999% availability reading lacks an observation window. Forty-five minutes of downtime alone would cap one-year availability near 99.9914%, so I do not present 99.999% as an annual result. A later seasonal program reportedly offset ~$3 million of commercial shortfall; offset sales are not the same as recovering each failed order.

The cross-team contract was mine to set: which data could touch payment, incident sequence, restoration gates, customer/vendor remedies, evidence owners, degraded behavior, and executive measures. Sustainability specialists controlled claim truth; Product controlled the proposition; Payments controlled the critical path; Reliability proved failure behavior; Finance separated loss, fee relief, and later sales.

The strategic outcome was a commerce system in which differentiation could fail safely. Environmental evidence became more credible precisely because it was governed separately from the transaction it was meant to improve.
