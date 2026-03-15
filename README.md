# Task-3-FUTURE_CS_03
# API Security Risk Analysis🛡️
 

## Executive Summary
This project involves a comprehensive security assessment of a REST API to identify common vulnerabilities listed in the **OWASP API Security Top 10**. The goal was to simulate real-world threats and provide actionable remediation strategies.

## 🛠️ Tools Used
* **Postman:** For request manipulation and automated collection running.
* **JSONPlaceholder:** Targeted demo API.
* **GitHub:** For version control and documentation.

## 🔍 Identified Risks & Analysis

| Risk ID | Vulnerability | Severity | Impact | Remediation |
| :--- | :--- | :--- | :--- | :--- |
| **API-01** | **Excessive Data Exposure** | Medium | Leaks sensitive PII (Home addresses/GPS). | Implement data filtering to return only necessary fields. |
| **API-02** | **Lack of Rate Limiting** | High | Vulnerable to DoS and brute-force attacks. | Implement rate-limiting middleware (e.g., 100 req/min). |
| **API-03** | **Broken Authentication** | Critical | Unauthorized access to sensitive endpoints. | Enforce JWT or API Key authentication for all non-public routes. |

## 🧪 Proof of Concept (PoC)
1. **Data Exposure:** A `GET` request to `/users/3` revealed full residential details not required for a public profile.
2. **Rate Limit Testing:** Using Postman Runner, 30 requests were sent in <3 seconds. All requests were accepted (200 OK), confirming no throttling is in place.

