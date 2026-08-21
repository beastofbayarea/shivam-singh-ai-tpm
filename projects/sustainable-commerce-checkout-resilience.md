# Protecting Checkout While Growing Sustainable Commerce

I led this work during my [AWS experience beginning in July 2024](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf).

This program joined two goals that initially seemed compatible: make verified sustainability information more useful to customers, and modernize a slow mobile checkout. The difficult lesson came during peak traffic, when an optional enrichment service became a synchronous dependency in the payment path. A DNS and TTL problem then exhausted threads, produced a 45-minute outage, and drove transaction failures to 15%.

## My first decision was to contain, not perfect

I declared the incident and routed 75% of transactions back through the known-stable legacy gateway. That reduced the failure rate from 15% to 2%. The fallback was slower and did not represent the target architecture, but it restored the customer's ability to pay while the team investigated safely.

I kept technical containment, customer communication, credits, vendor recovery, and revenue impact in the same incident view. A checkout incident is not complete when the graph turns green; it is complete when affected customers and commercial obligations have been addressed as well.

## I redrew the critical path

The correction process classified every dependency as mandatory, deferrable, or optional. Payment authorization and order integrity were mandatory. Sustainability enrichment was valuable, but it did not need to block completion of the transaction.

That distinction drove the permanent design:

- I removed optional enrichment from the synchronous payment path.
- I introduced a 500-millisecond circuit-breaker threshold so a slow dependency would degrade rather than cascade.
- I used cell isolation and shuffle sharding to reduce the blast radius of a failure.
- I established active-active regional capacity and tested failover under peak conditions.

The AWS Well-Architected Reliability Pillar provided the primary engineering frame: design for failure, isolate components, monitor behavior, and verify recovery. The FTC Green Guides shaped a separate but equally important control—environmental claims had to be specific and supportable. Resilience could not come from removing evidence; it had to come from moving evidence off the payment-critical path.

## Recovery had technical and customer measures

I tracked latency, availability, transaction failure, and circuit activation alongside cart abandonment, mobile conversion, sustainable-category conversion, customer credits, sentiment, vendor recovery, and revenue restoration.

This prevented a narrow “service restored” conclusion. If the platform was healthy but customers still abandoned checkout or distrusted the category claims, the product had not recovered.

## The results

- Checkout latency fell from 1.5 seconds to 800 milliseconds.
- Availability reached 99.999%.
- Cart abandonment declined from 45% to 30%, while mobile conversion increased from 0.8% to 1.0%.
- Sustainable-category conversion increased from 1.9% to 2.2%.
- The circuit breaker later activated 14 times without another outage.
- The roughly $3 million holiday revenue shortfall was recovered.

## What I learned from the outage

Useful customer context does not automatically belong in the critical path. I now ask two questions whenever a feature adds a dependency: “Must this answer exist before the transaction can complete?” and “What customer experience should remain when it does not?” Those questions make graceful degradation a product decision, not just an engineering mechanism.

I also learned to define recovery in commercial terms. Architecture, customer restitution, supplier accountability, and trust were all part of the same program.

## External foundations

The methodology and claims guidance below are the primary external foundation. My resume establishes only when I held the role.

| Source | How I applied it |
|---|---|
| [AWS — Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | I used its failure-management, isolation, observability, and recovery principles to redesign the checkout path. |
| [U.S. Federal Trade Commission — Green Guides](https://www.ftc.gov/legal-library/browse/rules/green-guides) | I used its guidance on qualified and supportable environmental claims to preserve trust while decoupling enrichment from payment. |
