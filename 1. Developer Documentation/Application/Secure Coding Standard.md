# Secure Coding Standard for Developers

Engineers are first line of defense for their security. Writing secure code is not a separate task - it is a fundamental part of writing high-quality code.

This document provides the essential security standards that all developers are expected to follow. Adhering to these guidelines helps us:

1. Protect  Customers and Data: Preventing breaches is the most critical responsibility.

2. Build Resilient Products: Secure applications are more robust and less prone to unexpected failures.

3. Maintain Compliance: The ability to meet standards like SOC 2 and ISO 27001 depends directly on the security of the code you write.

4. Increase Velocity: Finding and fixing security flaws early in the development lifecycle is exponentially cheaper and faster than fixing them after a breach.

## The Core Principles
1. Principle of Least Privilege: Grant services and users only the permissions they absolutely need to perform their function. Never use overly permissive roles (e.g., admin, *).

2. Defense in Depth: Don't rely on a single security control. Layer defenses so that if one fails, others are in place to stop an attack.

3. Never Trust User Input: Treat all data received from a user or another service as potentially malicious.

## Key Development Standards
1. Secrets Management
DO NOT hardcode secrets (API keys, passwords, database credentials, tokens) in your code, configuration files, or environment variables.

2. DO use the company's approved secrets management tool (e.g., AWS Secrets Manager, HashiCorp Vault) to store and retrieve all secrets programmatically.
Relevant Compliance: SOC 2: CC6.1; ISO 27001: A.9.4.1

3. Input Validation and Output Encoding
DO validate all incoming data for type, length, format, and range on the server-side.

4. DOuse parameterized queries or prepared statements to prevent SQL injection. Never construct database queries by concatenating strings.

5. DO properly encode all data before rendering it in a user's browser to prevent Cross-Site Scripting (XSS). Use the encoding functions provided by your framework.
Relevant Compliance: SOC 2: CC7.2; ISO 27001: A.14.2.5

6. Dependency Management
DO use the Software Composition Analysis (SCA) tool integrated into the CI/CD pipeline to scan for vulnerabilities in your third-party libraries.

7. DO NOT  use libraries with known critical or high-severity vulnerabilities.

8.  DO  keep  dependencies up to date and follow the company's policy for patching vulnerabilities within the required timeframe.
Relevant Compliance: SOC 2: CC9.2; ISO 27001: A.12.6.1

9. Authentication and Authorization
 DO  use the company's standard authentication services. Do not build your own authentication.

10.  DO  enforce authorization checks on every request for a protected resource, ensuring the authenticated user has the explicit right to perform that action.
Relevant Compliance: SOC 2: CC6.1, CC6.3; ISO 27001: A.9.2, A.9.1.2

11. Secure Logging
 DO   log all security-relevant events, such as successful/failed logins, access control decisions, and significant transactions.

12.  DO NOT  log sensitive data, such as passwords, session tokens, API keys, or personally identifiable information (PII), in plain text.
Relevant Compliance: SOC 2: CC7.3; ISO 27001: A.12.4.1

### Our Commitment to You
Security is committed to making it easy to write secure code. Security will provide you with the tools (SAST, SCA, DAST), training, and support you need. Security is a collaborative effort, and your work is essential to our success.

- Post examples of their tools and or videos of how to use them. 