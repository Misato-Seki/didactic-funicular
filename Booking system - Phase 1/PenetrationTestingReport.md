# Penetration Testing Report
## 1. Introduction:
### Purpose and scope of the report

- This penetration test was conducted to assess the security posture of the registration page. The objective was to identify vulnerabilities and potential security risks that could be exploited by malicious actors.

### Testing schedule and environment

- Testing Date: 6th March 2025
- Testing Environment: UTM + Kali (arm64)

### Scope of testing

- The primary focus was on the registration page to identify security weaknesses.
- The test evaluated authentication mechanisms, input validation, session management, and potential vulnerabilities to web-based attacks.

### Methods and tools used for testing

- Manual Testing: Conducted to simulate real-world attack scenarios.
- Automated Testing: Conducted using ZAP (OWASP Zed Attack Proxy) for vulnerability scanning.

**Updated 6.3.2025** - Retest

## 2. Summary:
### Key findings and recommendations
- **Critical Authentication Bypass Vulnerability** - Immediate action required to fix an issue allowing unauthorized access.
- **Cross-Site Scripting (XSS) Detected** - Input validation needs to be improved to prevent malicious script execution.
- **Use of Outdated Software Components** - Upgrade required to mitigate known vulnerabilities.

### General assessment of the system’s security posture.
- Overall, the security of the registration page is moderate, with some critical vulnerabilities that require immediate attention. While authentication mechanisms are in place, certain flaws could be exploited, leading to data exposure or unauthorized access.

## 3. Findings and Categorization:
### 🔴  Red (Critical) Findings:

1. Path Traversal

    - Description: Allows attackers to access unauthorized files on the server by manipulating file paths.
    - Impact: Attackers can read sensitive files such as configuration files, credentials, or system data.
    - Example: http://example.com/file?name=../../etc/passwd can expose system passwords.
    - Recommended Fix: Validate and sanitize user input to prevent directory traversal sequences.

2. SQL Injection

    - Description: Attackers can inject malicious SQL code into input fields, potentially gaining access to or modifying database contents.
    - Impact: Data theft, unauthorized access, and database corruption.
    - Example: ' OR '1'='1 injected into a login form can bypass authentication.
    - Recommended Fix: Use prepared statements and parameterized queries to prevent SQL injection.

### 🟡 Yellow (Medium) Findings:

3. Content Security Policy (CSP) Not Set

    - Description: Missing CSP headers can allow attackers to execute malicious scripts via XSS attacks.
    - Impact: Attackers can steal user data or inject malicious content.
    - Recommended Fix: Implement a strict Content-Security-Policy header to restrict script execution.

4. Format String Error

    - Description: Improper handling of format strings in functions like printf() can lead to memory leaks or code execution.
    - Impact: Potential remote code execution or denial of service.
    - Recommended Fix: Avoid passing user input directly into format string functions.

5. Clickjacking Vulnerability (X-Frame-Options Missing)

    - Description: Lack of X-Frame-Options allows an attacker to embed the site in an iframe and trick users into interacting with it unintentionally.
    - Impact: Users may unknowingly perform actions such as clicking a fraudulent "Buy Now" button.
    - Recommended Fix: Add X-Frame-Options: DENY or frame-ancestors 'none' in CSP.

### 🟢 Green (Low) Findings:

6. Application Error Disclosure

    - Description: Detailed error messages expose system paths, software versions, or database structures.
    - Impact: Attackers can gather information for further exploitation.
    - Recommended Fix: Display generic error messages and log detailed errors internally.

7. X-Content-Type-Options Header Missing

    - Description: Allows browsers to perform MIME-type sniffing, potentially leading to script execution in unintended ways.
    - Impact: Attackers might execute malicious scripts if a file is misinterpreted as JavaScript.
    - Recommended Fix: Add X-Content-Type-Options: nosniff to HTTP response headers.

8. User-Agent Based Behavior Differences

    - Description: System responds differently based on the User-Agent string, potentially revealing security mechanisms or vulnerabilities.
    - Impact: Attackers can fingerprint the system to craft targeted exploits.
    - Recommended Fix: Ensure consistent behavior regardless of User-Agent input.

## 4. Appendices:
- [2025-03-06-Booking-System-Phase1-Report1.md](2025-03-06-Booking-System-Phase1-Report1.md)
- [2025-03-06-Booking-System-Phase1-Report2.md](2025-03-06-Booking-System-Phase1-Report2.md)