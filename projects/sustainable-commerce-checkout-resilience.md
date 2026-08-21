# Making sustainable shopping trustworthy without putting payment at risk

I led a commerce reliability and sustainability program during my AWS role. I had identified that shoppers could not trust broad environmental claims and could not complete payment reliably when optional product data slowed checkout. I worked with shoppers, retail and payments teams, sustainability specialists, certifiers, platform and site-reliability engineers, vendors, support, finance, and executive owners.

## The product decision hidden inside the reliability problem

The team was trying to improve two different customer promises at once. The first was epistemic: if the storefront described a product as sustainable, the claim needed a specific basis that a shopper could understand. The second was transactional: no enrichment service, however useful, should be able to stop a customer from paying.

I treated those promises differently. Certification status, claim provenance, price, and delivery information shaped the shopping decision; payment authorization, inventory reservation, and order creation formed the non-negotiable transaction path. That distinction changed the program from a catalogue feature with an uptime target into a critical-path redesign with a separately governed trust layer.

The initial evidence was uncomfortable:

- a survey of 10,000 shoppers found 58% were concerned that sustainability claims could be greenwashing and 45% saw price as a barrier;
- sustainable-category conversion had fallen from a historical 2.8% to 1.9%;
- mobile represented 60% of traffic but converted 22% below desktop;
- overall checkout latency was 1.5 seconds, while mobile checkout took 4.2 seconds; and
- cart abandonment had moved from 25% to 45%.

I would not allow those numbers to collapse into one success metric. Claim trust, page performance, payment completion, conversion, and commercial value each had a different owner and measurement method.

## How I changed the system

I convened product, sustainability, legal, engineering, operations, and external certifiers to replace generic labels with claim-level evidence. Each eligible product needed a named standard or certificate, a current verification state, and shopper-facing language tied to that evidence. The [FTC Green Guides](https://www.ftc.gov/business-guidance/resources/environmental-claims-summary-green-guides) informed the discipline: broad environmental claims require qualification and substantiation rather than optimistic copy.

For the transaction path, I made graceful degradation the default. Sustainability enrichment could improve a product page or order record, but its failure could not consume checkout threads indefinitely. The design used:

- explicit timeouts and a circuit breaker that opened when more than 5% of requests exceeded 500 milliseconds;
- cached or last-known-good enrichment where the use was safe, and omission where stale evidence would mislead;
- cell isolation and shuffle sharding so one noisy dependency or customer cohort could not exhaust the whole service;
- active-active service capacity in Virginia and Oregon; and
- independent telemetry for customer latency, dependency latency, transaction failures, cache behavior, and circuit state.

This architecture follows the current [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): turn appropriate hard dependencies into soft ones, fail fast, bound queues and retries, isolate faults, and use tested recovery mechanisms. I use it here as an external technical benchmark, not as proof of what the internal implementation contained beyond the retained project record.

## The incident that forced a clearer contract

During viral demand of roughly 1,600 orders per second, a DNS/TTL and cache-miss pattern pushed calls toward an external carbon-data service. Its response time rose from about 200 milliseconds to more than five seconds. Waiting requests exhausted checkout threads; 504 errors followed; transaction failure reached 15% for 45 minutes. The incident record estimated roughly $3 million in lost orders.

I ran containment and correction as two distinct jobs. The team routed 75% of traffic to the legacy path, which reduced transaction failure from 15% to 2%. We then removed synchronous enrichment from the payment-critical path, added the circuit breaker and isolation controls, and exercised region and dependency failures before restoring full traffic. The circuit subsequently activated 14 times without another recorded outage, evidence that degradation had become a controlled state rather than an improvised response.

I also led the non-technical repair. Affected customers received $10 credits, support received a plain-language incident narrative, and the vendor discussion produced $100,000 in fee relief. Those remedies did not erase customer harm; they made accountability visible while the engineering work addressed recurrence.

## What changed, and exactly how I would defend it

| Measure | Baseline | Program intent | Observed result | Measurement and boundary |
|---|---:|---:|---:|---|
| Mobile checkout latency | 4.2 s | sub-second | 800 ms | client-side checkout timing; 3.4 s and 81% reduction |
| Mobile conversion | 0.8% | reverse the mobile gap | 1.0% | completed orders / eligible mobile sessions; +0.2 percentage points, +25% relative |
| Sustainable-category conversion | 1.9% | recover toward 2.8% historical level | 2.2% | completed orders / eligible category sessions; +0.3 points, +15.8% relative, still 0.6 points below history |
| Cart abandonment | 45% | restore the prior direction | 30% | initiated carts without completed order; -15 points, -33.3% relative, still 5 points above the earlier 25% level |
| Incident transaction failure | 15% | rapid containment | 2% after diversion | failed transactions / attempts during the incident window; -13 points |

The project record also reports 99.999% availability after the redesign, but it does not retain the observation window. I therefore present it only as a post-remediation reading, not annual availability: 45 minutes of downtime alone would make a one-year figure no better than about 99.9914%, while 99.999% across a year permits only about 5.3 minutes.

Similarly, the record says the seasonal program later offset approximately $3 million of commercial shortfall. I do not call those orders “recovered.” A failed purchase cannot be assumed to return; later sales can offset an accounting gap without reversing the original customer loss.

## Why this was a program, not an incident fix

My lasting contribution was the decision system around the service. Sustainability specialists owned evidence quality. Product owned the customer proposition. Payments engineering owned the transaction path. Site reliability owned failure-mode tests and operational thresholds. Finance kept incident loss, vendor remedies, and later seasonal sales in separate ledgers. I owned the cross-team contract: which data could affect payment, who could stop a release, how degraded behavior should look, and what evidence was required to declare recovery.

That combination made the work strategically larger than a latency improvement. It connected a differentiated retail proposition to claim substantiation, protected the revenue path from optional services, and gave executives a measurement model that did not disguise partial recovery as full success.

## Evidence used to reconstruct the work

- The retained project record supplies the survey, latency, conversion, incident, remediation, and commercial figures above.
- [FTC: Environmental Claims — Summary of the Green Guides](https://www.ftc.gov/business-guidance/resources/environmental-claims-summary-green-guides) — external benchmark for qualified and substantiated environmental marketing claims.
- [AWS Well-Architected Framework: Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) — current external benchmark for graceful degradation, bounded failure, observability, isolation, recovery, and resilience testing.
- [Amazon Builders' Library FAQ](https://aws.amazon.com/builders-library/faqs/) — identifies shuffle sharding as an Amazon fault-isolation practice.

The source labels this an “Amazon Sustainable Commerce” program, while this portfolio assigns it to my AWS tenure. I have therefore described it as a commerce program led during that role and have not claimed employment in an Amazon retail organization or attributed company-wide retail scale to my direct ownership.
