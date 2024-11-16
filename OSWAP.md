# OWASP Top 10 Web Security Risks

The OWASP (Open Web Application Security Project) Top 10 is a standard awareness document for developers and web application security. It represents the most critical security risks to web applications.

---

## 1. **Broken Access Control**
- **Description**: Improper enforcement of access control policies allows unauthorized users to perform restricted actions or access sensitive data.
- **Examples**:
  - Modifying URLs, cookies, or headers to access unauthorized resources.
  - Viewing or editing other users' accounts or data.
- **Mitigations**:
  - Use role-based access control.
  - Deny access by default and enforce least privilege.
  - Regularly test access control mechanisms.

---

## 2. **Cryptographic Failures**
- **Description**: Weak or missing cryptographic protections for sensitive data like passwords, credit card details, and personal information.
- **Examples**:
  - Storing passwords without hashing.
  - Using outdated encryption algorithms (e.g., MD5, SHA-1).
  - Transmitting data without encryption (HTTP instead of HTTPS).
- **Mitigations**:
  - Use strong encryption algorithms (e.g., AES, RSA).
  - Implement TLS for data in transit.
  - Hash passwords using modern algorithms like bcrypt or Argon2.

---

## 3. **Injection**
- **Description**: Improper handling of user input allows attackers to execute malicious code or queries on the server.
- **Examples**:
  - **SQL Injection**: Manipulating SQL queries.
  - **Command Injection**: Executing arbitrary system commands.
  - **LDAP Injection**: Exploiting LDAP queries.
- **Mitigations**:
  - Use parameterized queries and prepared statements.
  - Validate and sanitize user input.
  - Use Object-Relational Mapping (ORM) libraries.

---

## 4. **Insecure Design**
- **Description**: Failure to anticipate potential security threats during the design phase, resulting in insecure applications.
- **Examples**:
  - Lack of threat modeling.
  - Failing to include security measures in workflows or architecture.
- **Mitigations**:
  - Conduct secure design reviews.
  - Follow secure development lifecycle practices.
  - Implement defense-in-depth strategies.

---

## 5. **Security Misconfiguration**
- **Description**: Misconfigured or improperly secured settings that expose applications to attacks.
- **Examples**:
  - Default passwords or configurations left unchanged.
  - Exposed error messages revealing sensitive information.
  - Unpatched or outdated software.
- **Mitigations**:
  - Regularly update software and frameworks.
  - Remove unused features and components.
  - Use automated tools to verify configurations.

---

## 6. **Vulnerable and Outdated Components**
- **Description**: Using components with known vulnerabilities can lead to exploitation by attackers.
- **Examples**:
  - Using outdated libraries or frameworks.
  - Failure to monitor for vulnerabilities in dependencies.
- **Mitigations**:
  - Regularly update and patch third-party libraries.
  - Use tools to identify vulnerabilities (e.g., Dependabot, Snyk).
  - Maintain a list of components and their versions (SBOM).

---

## 7. **Identification and Authentication Failures**
- **Description**: Weak or flawed authentication mechanisms allow attackers to impersonate users.
- **Examples**:
  - Weak passwords or lack of password policies.
  - Failure to implement multi-factor authentication (MFA).
  - Poor session management practices.
- **Mitigations**:
  - Enforce strong password policies.
  - Use secure session tokens.
  - Implement MFA wherever possible.

---

## 8. **Software and Data Integrity Failures**
- **Description**: Issues related to integrity checks for software updates and critical data, allowing attackers to tamper with or replace trusted components.
- **Examples**:
  - Using software from untrusted sources.
  - Failing to verify the integrity of code or data.
- **Mitigations**:
  - Implement digital signatures for updates.
  - Use secure update mechanisms.
  - Validate inputs to prevent data tampering.

---

## 9. **Security Logging and Monitoring Failures**
- **Description**: Insufficient logging and monitoring prevent timely detection of and response to security breaches.
- **Examples**:
  - Missing logs for critical events.
  - Failure to alert on suspicious activities.
  - Logs that do not include enough detail for investigation.
- **Mitigations**:
  - Implement centralized logging solutions.
  - Configure alerts for unusual activities.
  - Regularly review logs for suspicious behavior.

---

## 10. **Server-Side Request Forgery (SSRF)**
- **Description**: Exploits the server’s ability to fetch resources, allowing attackers to make unauthorized requests.
- **Examples**:
  - Sending requests to internal systems not intended to be exposed.
  - Exploiting server privileges to access restricted data.
- **Mitigations**:
  - Validate and sanitize user-supplied URLs.
  - Restrict network access for requests.
  - Use allowlists for external resources.

---

## Tips for Competitive Exams
1. Memorize the **OWASP Top 10 list** in order, as it's a frequent question in exams.
2. Understand the **examples** for each risk.
3. Know common **mitigation strategies** for risks.
4. Be able to differentiate between risks, especially those with overlapping aspects like **insecure design** and **security misconfiguration**.

---

OWASP provides comprehensive documentation and tools to address these risks. Regularly updating your knowledge and implementing secure coding practices can significantly reduce vulnerabilities.
