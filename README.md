FUTURE_CS_01

# Task 1: Vulnerability Assessment Report - Altoro Mutual

## Project Overview
This project involved conducting a professional vulnerability assessment on **demo.testfire.net**. The primary goal was to identify, analyze, and provide remediation strategies for web security risks as part of the Future Ready Skills Cybersecurity Internship.

## Tools & Methodology
* **Nmap (Network Mapper)**: Performed network reconnaissance and port scanning to identify active services and potential entry points.
* **OWASP ZAP (Zaproxy)**: Conducted automated vulnerability scanning to detect common web application security flaws and generate detailed alerts.

## Key Findings (15 Total Alerts)
After a thorough scan, 15 security alerts were identified and categorized by risk level:

### **Medium Risk**
* **Absence of Anti-CSRF Tokens**: I identified that critical forms lack protection against Cross-Site Request Forgery, which could lead to unauthorized user actions.
* **Missing Anti-clickjacking Header**: The application is vulnerable to UI redressing attacks because the `X-Frame-Options` or `Content-Security-Policy` headers are not configured.

### **Low Risk**
* **Server Information Leakage**: The HTTP response headers disclose specific versioning for Apache Tomcat/Coyote, assisting attackers in footprinting.
* **Missing X-Content-Type-Options Header**: The lack of the `nosniff` directive puts users at risk of MIME-sniffing attacks.

## Remediation Strategy
To secure the application, I recommend the following implementations:
1. **Header Hardening**: Add `X-Content-Type-Options: nosniff` and configure `X-Frame-Options` to `DENY` or `SAMEORIGIN`.
2. **Session Security**: Enable and enforce Anti-CSRF tokens for all state-changing requests.
3. **Information Masking**: Configure the server to suppress version information in HTTP headers.

## Evidence
* [**Full Presentation (Canva)**](INSERT_YOUR_LINK_HERE): A detailed visual breakdown of the assessment.
* **Screenshots**: Raw evidence of the Nmap scan and ZAP alerts are included in the repository files.
*
