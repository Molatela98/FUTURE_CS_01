FUTURE_CS_01

# Task 1: Vulnerability Assessment Report - Altoro Mutual

## Project Overview
Conducted a professional vulnerability assessment on demo.testfire.net to identify and remediate web security risks for the Future Ready Skills Cybersecurity Internship.

## Tools Used
* **Nmap**: Network reconnaissance and port scanning.
* **OWASP ZAP**: Automated vulnerability scanning and alert generation.

## Key Findings (15 Alerts Identified)
* **Absence of Anti-CSRF Tokens (Medium)**: Risk of unauthorized actions during user sessions.
* **Missing Anti-clickjacking Header (Medium)**: Vulnerability to UI redressing attacks.
* **Server Leaks Version Information (Low)**: Discloses Apache Tomcat/Coyote versioning.
* **X-Content-Type-Options Header Missing (Low)**: Risk of MIME-sniffing attacks.

## Remediation Strategy
Implemented fixes including the addition of `nosniff` headers, configuring `X-Frame-Options` to `DENY`, and enabling CSRF protection tokens.
