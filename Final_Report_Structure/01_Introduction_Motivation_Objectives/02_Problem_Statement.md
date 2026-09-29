# 1.2 Problem Statement

E-commerce organizations depend on interconnected digital assets such as web applications, customer databases, payment-related services, administrative portals, order-management systems, and supporting infrastructure. These assets may contain multiple known vulnerabilities at the same time. Security teams therefore face a practical prioritization problem: deciding which vulnerabilities require immediate attention when time, staffing, and remediation capacity are limited.

A purely technical view of vulnerability severity is not always sufficient for this decision. A vulnerability with a high technical severity score may exist on a low-criticality system, while another vulnerability with a lower technical score may affect a business-critical asset that supports online sales, customer data, order processing, or service availability. Treating both cases only by technical severity can lead to remediation priorities that do not fully reflect the organization's operational and business exposure.

**Business-Aware Hierarchy & Impact Flow:** CyberSight maps technical flaws to business exposure using a explicit 3-tier relationship:

Business Process → Supporting Asset → Vulnerability (CVE)

| Primary Business Process | Supporting Asset | Potential Business Impact upon Exploitation |
| --- | --- | --- |
| Checkout & Payment | Payment Gateway API | Direct revenue loss, payment processor penalties, lost transactions, PDPL fines. |
| Order Fulfillment | Order Management System | Logistics halting, warehouse operational delays, missed delivery SLAs. |
| Customer Data Management | Customer Database | Massive data breach of PII/credentials, regulatory enforcement, brand reputation loss. |

The problem is therefore not simply the existence of vulnerability data, but the difficulty of translating technical vulnerability information into business-aware priorities. E-commerce organizations need a structured way to combine technical severity and exploit likelihood with the criticality and business impact of affected assets, then present the result in a form that supports

[Text truncated in source PDF]
