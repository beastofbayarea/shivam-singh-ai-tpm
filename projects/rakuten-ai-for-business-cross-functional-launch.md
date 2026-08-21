# Turning Rakuten AI for Business into a launchable product

Rakuten publicly introduced Rakuten AI for Business on November 14, 2023 as an invitation-only platform with three concepts: an Analyst to interpret data, an Agent to perform tasks, and a Librarian to retrieve and organize knowledge.

During my Rakuten internship, I converted that ambition into a cross-functional launch system. Product, Design, Engineering, Data, Privacy, Security, Legal, Sales, Support, Enablement, and business leadership each retained necessary authority; I made their inputs resolve into one decision: **which users and workflows could enter a controlled cohort, under what constraints, and what evidence would unlock expansion?**

## I wrote a launch constitution, not a calendar

The constitution answered five questions.

### Who goes first?

Product and sales selected an initial cohort with a recurring, inspectable workflow. Size alone was not the criterion. Each cohort definition named the user, job, data entitlement, required human review, support route, and exclusions.

### What is “good” for this workflow?

Business owners defined acceptable work. Evaluation teams translated that into reference cases, edge conditions, known failures, and reviewer guidance. Factual grounding, task completion, response quality, latency, refusal behavior, and user usefulness remained separate dimensions.

### What may the product see and do?

Security, privacy, legal, data owners, and engineering mapped source systems, identity, purpose, retention, logging, administration, and actions. Retrieving company knowledge and executing against a business system were different permission classes. A useful answer did not authorize a consequential action.

### Where does a person remain accountable?

The operating path named when someone reviewed, edited, approved, or took over; how users reported bad output; who could inspect a trace; who could pause the workflow; and what support would say about limitations.

### What unlocks the next cohort?

Expansion required a release packet: offline evaluation, production behavior, user evidence, unresolved risk, support capacity, and named approvals. A schedule change could move the date; it could not silently lower the gate.

## Three products, three different critical paths

| Concept | Promise | Program-critical dependency | Failure to prevent | Expansion proof |
|---|---|---|---|---|
| Analyst | Explain business information | Governed definitions and entitled data | Persuasive but incorrect interpretation | Reference accuracy, citations, reviewer agreement, access tests |
| Agent | Complete a bounded task | Tools, authorization, confirmation, rollback | Correct intent causing a harmful action | Scenario success, permission tests, human approval, recoverability |
| Librarian | Find and organize knowledge | Rights, indexing, freshness, deletion | Disclosure or stale guidance | Retrieval relevance, entitlement, freshness and deletion tests |

This dependency map let specialists preserve approval authority without turning the program into sequential handoffs. Engineering built toward stable acceptance conditions. Legal and security reviewed concrete data/action paths. Business teams understood why a polished demo was not yet a releasable workflow.

Every material dependency carried an owner, decision date, upstream evidence, downstream consequence, and escalation condition. I replaced vague red statuses with a written decision, viable options, authorized decision-maker, and consequence of delay.

## I kept ecosystem scale out of the launch denominator

Rakuten described a domestic ecosystem of more than 70 services and over 40 million monthly active users. Those figures established company context, not invitation-only product reach. I did not convert them into adoption, productivity, revenue, or launch claims.

The retained project record also contains no production baseline-to-result scorecard. I did not manufacture one. At this stage the defensible measures were:

- **Evaluation coverage:** approved workflow scenarios tested / approved scenarios, split by normal, edge, adversarial, and permission cases.
- **Gate readiness:** accepted applicable gates / applicable gates; only the named approver could mark a gate complete.
- **Cohort health:** invited eligible users who activated, completed the target job, returned, sought support, or opted out—always with denominator and time window.
- **Risk closure:** blocking findings by severity, age, owner, retest, and fixed-versus-accepted disposition.
- **Operational capacity:** support cases, response time, escalation, and cohort demand relative to staffed capacity.

Model results carried the prompt set, retrieval snapshot, reviewer rubric, version/configuration, threshold, and failure distribution. Production usefulness sat beside offline quality rather than replacing it. The [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) provides an external govern-map-measure-manage benchmark for that integrated approach.

## My deliverable was decision coherence

Cohort logic, dependencies, readiness reviews, escalation, evidence packets, and the launch/expansion boundary were the program elements under my control. Product set the proposition; Technical/Data built it; Privacy/Security/Legal approved it; business owners defined acceptable work; Support/Enablement operated the human path.

The [August 2023 Rakuten–OpenAI memorandum](https://global.rakuten.com/corp/news/press/2023/0802_01.html) and [November 2023 invitation-only announcement](https://global.rakuten.com/corp/news/press/2023/1114_02.html) establish the contemporaneous public context. A later [April 2024 RMS AI Assistant announcement](https://global.rakuten.com/corp/news/press/2024/0430_01.html) postdates my internship and is not my outcome.

The strategic result of my tenure was a launch operating system for three materially different AI products. It made user scope, data access, evaluation, action authority, human accountability, support, and expansion one executive decision—without borrowing ecosystem scale or inventing a business result the record does not support.
