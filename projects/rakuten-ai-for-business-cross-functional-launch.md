# Turning Rakuten AI for Business into a launchable product

I led the cross-functional launch program for Rakuten AI for Business during my Rakuten internship. I saw that business users needed help completing everyday work without exposing company knowledge or accepting unreliable answers. I brought together product, design, engineering, data, privacy, security, legal, sales, support, enablement, and business leaders.

## My assignment was to create evidence for a decision

Rakuten publicly introduced Rakuten AI for Business on November 14, 2023 as an invitation-only generative-AI platform and described three product concepts: an Analyst to interpret data, an Agent to perform tasks, and a Librarian to organize and retrieve knowledge. It named six broad areas of use—marketing, sales, customer support, operations, strategy, and engineering—but public ambition was not the same as launch readiness.

I converted that ambition into a decision the company could actually make: which user and workflow should enter a controlled cohort, what the product could do safely, what had to be true before expansion, and which evidence would justify the next release. My deliverable was not a launch calendar. It was a shared operating contract across teams with different incentives.

My launch constitution spanned three materially different AI products and twelve functional disciplines. I made cohort scope, data entitlement, evaluation, action authority, human review, support capacity, and expansion evidence one executive decision system—while explicitly refusing to borrow Rakuten's 70-service and 40-million-user ecosystem scale as if an invitation-only product had already reached it.

At the time of the announcement, Rakuten described a domestic ecosystem with more than 70 services and over 40 million monthly active users. I treated that as company context, not program reach. The product was invitation-only; nothing in the retained record supports claiming tens of millions of users, merchant adoption, revenue, or productivity gains from my launch work.

## The launch constitution

I organized the program around questions that could stop a release, because a list of activities would have hidden the real dependencies.

**Who is the product for first?** Product and sales had to choose an initial cohort with a recurring, inspectable workflow—not simply the largest addressable audience. The cohort definition included the job to be done, data entitlement, expected human review, support path, and an explicit exclusion list.

**What does a useful answer mean?** The business owner defined success for each workflow. Data and evaluation teams translated it into test cases with reference material, known failure modes, and reviewer guidance. We separated factual grounding, task completion, response quality, latency, refusal behavior, and user usefulness rather than compressing them into one opaque score.

**What may the model see and do?** Security, privacy, legal, data owners, and engineering mapped source systems, identity, retention, logging, administrative controls, and actions. Retrieval from company knowledge and execution against business systems required different permissions. A helpful answer did not authorize a consequential action.

**How will people remain accountable?** The operating design identified when a person had to review, edit, approve, or take over; how users would report a bad answer; who could inspect the trace; and how the team would pause a workflow or cohort. Support material described the product’s limits as plainly as its capabilities.

**What evidence unlocks expansion?** I tied every cohort increase to a release packet: offline evaluation, production behavior, user feedback, open risk, support capacity, and owner sign-off. Schedule pressure could change a date, but it could not silently redefine the gate.

## The dependency map I ran

The three product concepts created materially different program risks:

| Product concept | User promise | Critical dependency | Main launch failure | Evidence required before expansion |
|---|---|---|---|---|
| Analyst | explain business information | governed data definitions and access | persuasive but incorrect interpretation | reference-set accuracy, source citation, reviewer agreement, access tests |
| Agent | complete a bounded task | tools, permissions, confirmation, rollback | correct intent but harmful action | task success by scenario, authorization tests, human approval, recoverability |
| Librarian | find and organize knowledge | document rights, indexing, freshness | disclosure or stale guidance | retrieval relevance, entitlement checks, freshness and deletion tests |

That matrix let specialists preserve domain authority without turning the program into sequential handoffs. Engineering could build against stable acceptance conditions; legal and security could focus on concrete data and actions; business owners could see why a polished demo was not yet a releasable workflow.

I maintained a single dependency view with an owner, decision date, upstream input, downstream consequence, and escalation condition. The hardest items were not labelled “red” and left to age. I wrote the decision needed, the options, who could decide, and what would happen if the date passed.

## How I measured a launch that had no defensible business result yet

The retained record does not contain baseline-to-result production metrics. I will not manufacture them. For this stage, I would report the program through four auditable denominators:

1. **Evaluation coverage:** tested workflow scenarios divided by approved scenarios, split by normal, edge, adversarial, and permission cases.
2. **Release readiness:** satisfied gates divided by applicable gates, with a gate counted only when its named approver accepted the evidence.
3. **Cohort health:** eligible invited users who activated, completed the target workflow, returned, escalated to support, or opted out—never a headline user total without the eligible denominator and window.
4. **Risk closure:** open launch-blocking findings by severity, age, owner, and retest status; “accepted” risk reported separately from fixed risk.

For model behavior, averages alone would be insufficient. I would preserve the prompt set and version, retrieval corpus snapshot, reviewer rubric, model and configuration, pass threshold, and distribution of failures. Production usefulness would be reported beside—not substituted for—offline quality. That approach is consistent with the [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework), which treats governance, mapping, measurement, and management as connected activities.

## What I owned and what I did not claim

I owned the integrated launch logic: cohort, cross-functional dependencies, readiness reviews, unresolved decisions, escalation, evidence packet, and the boundary between launch and expansion. Product owned the proposition and prioritization. Technical and data leaders owned implementation. Privacy, legal, and security retained their approval authority. Business owners defined acceptable work. Support and enablement owned the human operating path.

The defensible result of my tenure is that a broad platform narrative became a controlled-launch system with explicit users, workflows, controls, evidence, and decision rights. The public announcement occurred within my June–December 2023 internship. Rakuten later announced in April 2024 that a separate RMS AI Assistant had launched to merchants in March and described an AI University serving its merchant base. Those events happened after my stated tenure; they show the company’s subsequent direction, not an outcome I claim to have delivered.

## Public record and reconstruction boundary

- [Rakuten and OpenAI memorandum of understanding, August 2, 2023](https://global.rakuten.com/corp/news/press/2023/0802_01.html) — contemporaneous partnership context and Rakuten ecosystem scale.
- [Rakuten AI for Business announcement, November 14, 2023](https://global.rakuten.com/corp/news/press/2023/1114_02.html) — launch timing, invitation-only status, product concepts, use cases, and public positioning.
- [Rakuten RMS AI Assistant and AI University announcement, April 30, 2024](https://global.rakuten.com/corp/news/press/2024/0430_01.html) — later company development used only to establish chronology.
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) — external benchmark for the evaluation and governance approach.

Because no retained internal scorecard, cohort count, or business result accompanies this project, I have deliberately quantified the public product surface and the measurement design—not invented adoption, accuracy, savings, or revenue.
