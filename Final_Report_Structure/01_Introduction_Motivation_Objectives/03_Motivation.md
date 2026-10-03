# 1.3 Motivation

Modern e-commerce organizations operate in dynamic threat environments where vulnerability scanners and threat intelligence feeds generate an overwhelming volume of security alerts daily. While existing enterprise tools—such as vulnerability scanners, SIEM platforms, and incident-response systems—are highly effective at detecting flaws and aggregating logs, they inherently lack internal organizational context. Consequently, security teams are forced to rely primarily on standard CVSS technical severity scores, often leading to "alert fatigue" and suboptimal resource allocation.

The primary motivation behind CyberSight is to bridge this critical gap between technical vulnerability data and business reality. By introducing a context-aware decision-support layer, CyberSight combines three complementary dimensions:
1. Technical Severity (NIST NVD / CVSS Base Metrics)
2. Exploit Likelihood (FIRST EPSS Threat Intelligence)
3. Business Exposure & Impact (Asset Criticality aligned with NCA NFCRM & Saudi PDPL)

CyberSight is not designed to displace or replace existing security infrastructure (scanners, SIEMs, or SOAR tools). Instead, it acts as an intelligent decision-support system that ingests raw vulnerability data, enriches it with real-time exploitation probability, and maps it directly against the business criticality of supporting e-commerce assets. This enables security analysts and IT administrators to resolve priority misalignments, focus limited remediation capacity on flaws that pose genuine operational risks, and maintain full, transparent explainability behind every triage decision.
