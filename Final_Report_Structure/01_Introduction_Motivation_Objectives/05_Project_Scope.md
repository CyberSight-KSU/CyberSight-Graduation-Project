# 1.5 Project Scope

Scope definition. The graduation-project implementation of CyberSight will focus on vulnerability and cyber-risk prioritization for a controlled e-commerce organizational case study. The platform architecture may be extensible to other sectors in the future, but the design, data model, business-impact assumptions, demonstrations, and evaluation in this project will be centered on e-commerce organizations.

## 1.5.1 In Scope

- E-commerce asset inventory: Create and manage a limited set of representative assets such as the e-commerce web application, customer database, order-management system, administrative portal, inventory system, and supporting servers.

- Public vulnerability intelligence: Import or retrieve selected CVE records and associated technical attributes such as CVSS severity and affected-product information from trusted public sources.

- Exploit-likelihood enrichment: Enrich CVE records with EPSS scores and/or a known-exploitation indicator when available, so prioritization is not based on CVSS alone.

- CVE-to-Asset mapping (Non-scanning approach): Map vulnerabilities to assets without automated network scanning by recording asset software profiles (Software Bill of Materials / CPE entries) and correlating them against NIST NVD records or importing verified CVE files.

- Risk treatment tracking: Allow users to record a basic treatment decision or remediation status such as patch, mitigate, monitor, accept, or resolved.

- Residual-risk view: Provide a simplified before/after representation of risk when a treatment or security control is applied, without attempting to model every control in a full enterprise GRC framework.

- Analytical dashboard: Visualize high-priority vulnerabilities, risk distribution by asset, severity, exploitation likelihood, business criticality, and treatment status with transparent score component breakdowns.

- Basic user roles: Support a small set of roles such as Security Analyst and Security/IT Manager with role-appropriate access to assessment and reporting functions.

### 1.5.1.1 Business Criticality Rubric (1–5)

During asset setup, rate each asset against the five criteria below and document the justification. The scale is **1 = Very Low, 2 = Low, 3 = Moderate, 4 = High, and 5 = Very High / Critical**. Assess the represented operational asset's role, data access, and available alternatives in the Saudi e-commerce case study, independently of CVSS or EPSS; neither its name nor synthetic test data determines its rating.

Use a common operating period and impact horizon, recording each asset's disruption or compromise scenario, trading conditions, transaction volumes, affected processes, and workarounds. The numerical bands are provisional case-study anchors requiring stakeholder review, not regulatory limits or validated industry thresholds. This contextual tailoring follows NIST SP 800-30 Rev. 1 [6, Sec. 2.3.2].

**Operational Dependency:** Measures how strongly business processes depend on the asset and whether alternative workflows can sustain them. It assesses process continuity, while Service Availability separately measures the time the business can tolerate an interruption.

| Rating | Level | Definition |
| --- | --- | --- |
| 1 | Very Low | No live sales, payment, fulfillment, customer-service, or stock-control process depends on the asset. Its loss suspends only optional work, such as an unused reporting copy. |
| 2 | Low | A supporting task is disrupted, but an established alternative completes the same workload with existing staff and within normal processing deadlines. |
| 3 | Moderate | A business process continues through a manual or alternative workflow, but needs extra staff or develops a recoverable backlog; orders can still be accepted and fulfilled. |
| 4 | High | At least one core process, such as payment authorization, order dispatch, or stock allocation, stops for the affected workflow because no viable workaround exists; other core processes continue independently. |
| 5 | Very High / Critical | The asset is a shared dependency whose loss prevents the main sales-to-fulfillment chain from operating across the store; no viable alternative can sustain that chain. |

**Customer Impact:** Measures the effect on customers' ability to complete purchases, receive orders, or obtain support. Record the affected customer group and journey; use the highest applicable consequence supported by the scenario.

| Rating | Level | Definition |
| --- | --- | --- |
| 1 | Very Low | Customers experience no change to browsing, purchasing, order delivery, account access, or support. |
| 2 | Low | Customers notice inconvenience in an optional feature, but can complete the same purchase or service request without assistance or delay to a promised outcome. |
| 3 | Moderate | Customers must retry, use another channel, or contact support, but can still complete the purchase or receive service within the promised timeframe. |
| 4 | High | An identifiable customer group cannot complete purchases or receive an existing order/service within the promised timeframe, and no usable alternative meets that commitment; other customer groups remain served. |
| 5 | Very High / Critical | All or most active customers cannot complete the store's main purchase journey or receive committed orders/services, with no usable alternative, or the scenario exposes customers to direct unauthorized charges or account takeover. |

**Data Sensitivity:** Measures the consequences of unauthorized disclosure, alteration, or misuse of data that the asset stores, processes, or can access. Apply the highest applicable level and record the data fields, record volume, and access privileges. These are project impact levels; the legal category of sensitive personal data remains distinct under the Saudi Personal Data Protection Law [7, Art. 1].

| Rating | Level | Definition |
| --- | --- | --- |
| 1 | Very Low | Holds only approved public content or non-identifiable synthetic data, with no access to personal records, confidential business data, or production credentials. |
| 2 | Low | Holds internal, non-personal information such as aggregate stock counts or routine procedures; misuse cannot identify customers, authorize transactions, or expose commercially confidential terms. |
| 3 | Moderate | Holds a limited set of personal contact fields, such as a customer name and email, or confidential business information such as supplier pricing; no linked address/payment history, authentication secrets, or sensitive personal data is accessible. |
| 4 | High | Holds linked customer profiles, delivery addresses and order histories, payment-related records, or customer authentication records whose misuse supports targeted fraud or disclosure of private activity, without the level-5 access or data characteristics. |
| 5 | Very High / Critical | Holds sensitive personal data as defined by PDPL, reusable privileged credentials or payment secrets enabling unauthorized access/transactions, or access to bulk identifiable customer records whose misuse enables widespread identity abuse or fraud. |

**Financial Impact:** Measures estimated direct loss over the common assessment horizon. Let L be the documented SAR estimate of lost sales that will not be recovered, refunds/compensation, recovery costs, and evidenced contractual charges, without counting the same loss twice. Let D be the case study's positive reference average daily sales in SAR, fixed across all assets. Score F = 100 × L / D. Synthetic amounts must be labelled as assumptions; speculative maximum regulatory fines are not an automatic loss estimate.

| Rating | Level | Definition |
| --- | --- | --- |
| 1 | Very Low | 0% ≤ F < 1%: direct loss is less than one hundredth of reference daily sales, including zero loss. |
| 2 | Low | 1% ≤ F < 10%: direct loss is at least one hundredth but less than one tenth of reference daily sales. |
| 3 | Moderate | 10% ≤ F < 50%: direct loss is at least one tenth but less than half of reference daily sales. |
| 4 | High | 50% ≤ F < 100%: direct loss is at least half but less than one full reference day of sales. |
| 5 | Very High / Critical | F ≥ 100%: direct loss equals or exceeds one full reference day of sales. |

**Service Availability:** Measures required continuity, using T, the maximum business-tolerable interruption of the service supported by the asset under the documented operating conditions. T is justified by order cut-offs, payment dependencies, delivery commitments, or service agreements; it is not observed uptime or the technical repair estimate. Shorter tolerable interruptions receive higher ratings.

| Rating | Level | Definition |
| --- | --- | --- |
| 1 | Very Low | T > 24 hours: the supported service can remain unavailable beyond a full day without breaching its documented business commitments. |
| 2 | Low | 8 hours < T ≤ 24 hours: the service can tolerate an extended interruption, but must return within one day. |
| 3 | Moderate | 2 hours < T ≤ 8 hours: the service must return within the same operating shift to meet processing or service commitments. |
| 4 | High | 15 minutes < T ≤ 2 hours: the service supports time-sensitive trading or fulfillment and requires restoration within two hours. |
| 5 | Very High / Critical | 0 ≤ T ≤ 15 minutes: the service requires near-continuous availability; interruptions beyond fifteen minutes, or a shorter documented tolerance, breach its business commitments. |

**Application to representative assets:** Apply all five criteria to each asset. The following evidence distinguishes their roles without assigning unsupported default scores.

| Asset | Evidence used to select the rubric ratings |
| --- | --- |
| Payment Gateway API | Share of checkout transactions using the gateway, usable alternative payment routes, transaction loss estimates, payment secrets accessible to the integration, and payment-service interruption tolerance. |
| Customer Database | Processes dependent on live queries, fields and volume of identifiable records, account/credential access, customer consequences of misuse, and tolerable interruption of customer-facing functions. |
| Order Management System | Ability to accept, route, and dispatch orders manually, backlog capacity, delivery cut-offs, accessible delivery details, and compensation for missed commitments. |
| E-commerce Web Application | Reliance on the storefront for sales, customer journeys interrupted, alternative sales channels, data and credentials accessible through the application, and unrecoverable sales during interruption. |
| Administrative Portal | Tasks and privileges exposed, ability to change orders or refunds, access to customer records, alternative staff workflows, and urgency of the affected administrative tasks. |
| Inventory System | Dependence of checkout and fulfillment on stock availability, safe use of cached/manual stock records, overselling and cancellation costs, and stock-update deadlines. |

**Documented justification:** Each of the five ratings must record the asset and business process, selected level, scenario and assumptions, supporting evidence, assessor, and assessment date. Evidence may include a process map, data inventory, transaction estimate, service commitment, or stakeholder response. For synthetic case-study data, identify the assumption explicitly. Missing evidence is recorded as pending validation, not assigned a default rating of 1; incomplete assessments do not produce a final aggregate.

**Temporary equal-weight baseline:** Business Criticality (called Asset Criticality in Section 1.5.1.2) may initially use the arithmetic mean of the five completed ratings:

```text
Business Criticality = (Operational Dependency + Customer Impact + Data Sensitivity
                       + Financial Impact + Service Availability) / 5
```

The result remains on a 1–5 scale and may be fractional; retain the unrounded value for calculation and show the five individual ratings and their justifications alongside it. A critical individual criterion must remain visible even when averaging lowers the aggregate. This mean is a transparent provisional scoring convention for ordinal ratings, not a monetary loss estimate or evidence that the criteria are equally important. Final criterion weights will be derived or validated using stakeholder input, with the rationale and resulting ranking changes documented before adoption.

### 1.5.1.2 Business-Aware Risk Prioritization

Combine technical vulnerability information with asset criticality using an explainable Weighted Sum Model (WSM) aligned with NIST SP 800-30 [6] and Saudi NCA NFCRM [4] frameworks:

```text
Risk Score = (0.35 × CVSS) + (0.25 × EPSS × 10) + (0.40 × Asset Criticality × 2)
```

**Baseline risk-scoring weights:** The existing 35% CVSS, 25% EPSS, and 40% Business Criticality weights are provisional baseline values, not finalized or prescribed by the referenced frameworks. They are separate from the equal-weight average of the five business criteria. These risk-scoring weights must also be derived or validated through stakeholder input before final adoption.

#### Weight Validation Plan

The initial 35% CVSS, 25% EPSS, and 40% Business Criticality weights will be used only as a development baseline. Before final adoption, the relative importance of the three dimensions will be validated with selected cybersecurity and IT stakeholders using a structured pairwise-comparison approach. The resulting stakeholder-derived weights will be compared with the baseline values, and any adopted changes will be documented together with their effect on the final prioritization results.

## 1.5.2 Out of Scope

- Automatic vulnerability scanning of real networks or endpoints.

- Penetration testing, exploitation, or offensive security functionality.

- Real-time network monitoring, intrusion detection, or SIEM replacement.

- Automated incident response or security orchestration (SOAR).

- Malware analysis or threat-hunting functionality.

- Direct integration with production systems of a real organization during the graduation-project phase.

- Full compliance auditing against every cybersecurity regulation or control framework.

- Prediction of future cyberattacks using a custom machine-learning model as a core dependency.

## 1.5.3 Data Scope and Availability

The project will deliberately use a hybrid data strategy so that the technical evidence is real while the organizational context remains safe, controllable, and feasible for a student project:

| Data layer | Planned source | Role in CyberSight |
| --- | --- | --- |
| Vulnerability records | NIST National Vulnerability Database (NVD) | CVE details, CVSS severity, affected-product information and other vulnerability attributes. |
| Exploit likelihood | FIRST EPSS | A probability-oriented exploitation score that can enrich prioritization. |
| Saudi context | Saudi National Cybersecurity Authority (NCA) & PDPL | E-commerce cybersecurity guidelines, NFCRM risk framework, and local data privacy compliance criteria. |
| Organizational context | Controlled synthetic e-commerce case study | Asset inventory, business processes, asset criticality and business-impact ratings created using a documented scoring rubric. |

**Important design principle:** the synthetic component will not invent vulnerability facts. It will represent the organization-specific context that is normally private or unavailable, while CVE/CVSS/EPSS data will come from public real-world sources.

## 1.5.4 Minimum Viable Product (MVP) vs. Stretch Features

The MVP should remain intentionally small enough to be completed, tested, and demonstrated reliably. Features are strictly divided to guarantee feasibility:

```text
Define assets → Import CVEs → Enrich (CVSS/EPSS) → Criticality
    Calculate priority → Visualize → Record treatment
```

### CORE MVP (MUST IMPLEMENT)

- Manual asset creation & 1–5 rubric scoring.

- Selected CVE/CVSS import & static EPSS enrichment.

- Transparent WSM prioritization ranking engine.

- Analytics dashboard & basic treatment status tracking.

### OPTIONAL STRETCH FEATURES

- Live NVD background API auto-sync pipeline.

- Dynamic admin weight customization sliders.

- Automated SLA timers & email notifications.

- One-click exportable executive PDF report generator.

## 1.5.5 Scope Boundaries for Feasibility

- The project will use a deliberately limited number of representative e-commerce assets rather than attempting to model a full enterprise environment.

- The vulnerability dataset will be a selected and relevant subset rather than a complete mirror of all global CVE records.

- The prioritization logic must be transparent and explainable; the core system will not depend on a black-box AI model.

- Advanced enrichment such as EPSS, local NCA relevance, or residual-risk comparisons can be implemented after the core MVP is stable.

- The project will be evaluated primarily as a decision-support information system: correctness of data handling, consistency of prioritization, usability, explainability, and usefulness for risk-triage decisions.

## 1.5.6 Final Preliminary Scope Statement

CyberSight will be developed and evaluated as a web-based, business-aware vulnerability and cyber-risk prioritization platform for an e-commerce case study. It will combine real public vulnerability intelligence with

[Text truncated in source PDF]
