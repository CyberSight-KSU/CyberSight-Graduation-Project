# 1.5 Project Scope

Scope definition. The graduation-project implementation of CyberSight will focus on vulnerability and cyber-risk prioritization for a controlled e-commerce organizational case study. The platform architecture may be extensible to other sectors in the future, but the design, data model, business-impact assumptions, demonstrations, and evaluation in this project will be centered on e-commerce organizations.

## 1.5.1 In Scope

- E-commerce asset inventory: Create and manage a limited set of representative assets such as the e-commerce web application, customer database, order-management system, administrative portal, inventory system, and supporting servers.

- Public vulnerability intelligence: Import or retrieve selected CVE records and associated technical attributes such as CVSS severity and affected-product information from trusted public sources.

- Exploit-likelihood enrichment: Enrich CVE records with EPSS scores and/or a known-exploitation indicator when available, so prioritization is not based on CVSS alone.

- Business criticality assessment: Assign each asset a structured business-criticality rating on a 1 to 5 scale based on criteria such as operational dependency, customer impact, data sensitivity (Saudi PDPL), financial impact, and service availability. Ratings are justified using a structured rubric form during asset setup.

**Business-aware risk prioritization:** Combine technical vulnerability information with asset criticality using an explainable Weighted Sum Model (WSM) aligned with NIST SP 800-30 and Saudi NCA NFCRM frameworks:

```text
Risk Score = (0.35 × CVSS) + (0.25 × EPSS × 10) + (0.40 × Asset Criticality × 2)
```

- CVE-to-Asset mapping (Non-scanning approach): Map vulnerabilities to assets without automated network scanning by recording asset software profiles (Software Bill of Materials / CPE entries) and correlating them against NIST NVD records or importing verified CVE files.

- Risk treatment tracking: Allow users to record a basic treatment decision or remediation status such as patch, mitigate, monitor, accept, or resolved.

- Residual-risk view: Provide a simplified before/after representation of risk when a treatment or security control is applied, without attempting to model every control in a full enterprise GRC framework.

- Analytical dashboard: Visualize high-priority vulnerabilities, risk distribution by asset, severity, exploitation likelihood, business criticality, and treatment status with transparent score component breakdowns.

- Basic user roles: Support a small set of roles such as Security Analyst and Security/IT Manager with role-appropriate access to assessment and reporting functions.

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
