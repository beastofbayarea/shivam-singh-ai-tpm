# Amazon Sustainable Commerce — Resilient Checkout & Category Growth

## What I worked on

I completed this work during my [AWS experience from July 2024 to present](https://github.com/beastofbayarea/shivam-singh-ai-tpm/blob/main/shivam-singh-ai-tpm.pdf).

I combined checkout modernization with verified sustainable-category growth, then led correction after an external enrichment dependency triggered a peak outage. The redesign isolated payment from optional data, added active-active resilience and circuit breakers, and connected technical recovery to customer and commercial outcomes.

## At a glance

- I led correction of a peak checkout outage that caused a 15% transaction-failure rate and roughly $3M in lost revenue, restoring a legacy fallback to contain impact.
- I redesigned payment as a mandatory path and sustainability data as optional enrichment, adding cell isolation, circuit breakers, and multi-region active-active capacity.
- I reduced checkout latency from 1.5 seconds to 800 ms, achieved 99.999% availability, cut cart abandonment from 45% to 30%, and recovered the holiday shortfall.

## The situation

Customers distrusted vague sustainability claims while mobile checkout was slow. During peak traffic, a DNS/TTL issue caused synchronous calls to an external enrichment service, exhausting threads and creating a 45-minute outage.

## What I needed to accomplish

I needed to protect payment completion, correct the architectural failure, restore customer trust, and preserve verified sustainability value without keeping it on the critical path.

## What I did

- I declared the outage and routed 75% of transactions to the stable legacy gateway, reducing failure from 15% to 2%.
- I led a correction-of-error process that reclassified every dependency as mandatory, deferrable, or optional.
- I implemented cell isolation, shuffle sharding, a 500 ms circuit threshold, and active-active regional capacity.
- I tracked customer credits, vendor SLA recovery, sentiment, category conversion, and revenue restoration alongside technical remediation.

## The results

- Checkout latency reached 800 ms and availability reached 99.999%.
- Cart abandonment fell from 45% to 30%, and mobile conversion rose from 0.8% to 1.0%.
- Sustainable-category conversion improved from 1.9% to 2.2%.
- The circuit breaker later activated 14 times without another outage, and the roughly $3M holiday shortfall was recovered.

## Decisions and trade-offs

- I restored a slower known-safe gateway before pursuing the permanent fix.
- I removed optional sustainability data from the synchronous payment path.
- I treated customer restitution and vendor economics as part of incident completion.

## How I led

I coordinated platform, category, vendor, customer-service, and executive teams through containment, correction, architecture redesign, and measurable commercial recovery.

## Why I chose this approach

I used [AWS - Well-Architected Reliability Pillar (2024)](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) to ground reliability and failure-management methodology. I used [U.S. FTC - Green Guides](https://www.ftc.gov/legal-library/browse/rules/green-guides) to ground environmental-marketing and claim-qualification guidance.

## Sources and external context

I used independent methodology and market evidence to shape the work. The resume link above is included only to establish the employment timeline.

| Source | How it informed my work | Timing |
|---|---|---|
| [AWS - Well-Architected Reliability Pillar (2024)](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | I used it to ground reliability and failure-management methodology. | — |
| [U.S. FTC - Green Guides](https://www.ftc.gov/legal-library/browse/rules/green-guides) | I used it to ground environmental-marketing and claim-qualification guidance. | — |
