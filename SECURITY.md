# Security Policy

## Overview

**OpenHIMS** is healthcare infrastructure software handling sensitive Protected Health Information (PHI). We take security seriously and appreciate the security research community's help in keeping our users safe.

This document outlines our security vulnerability reporting process and security practices.

---

## Supported Versions

We actively maintain security updates for the following versions:

| Version | Supported          | End of Support |
| ------- | ------------------ | -------------- |
| 1.x.x   | ✅ Yes             | TBD            |
| 0.9.x   | ✅ Yes (until 1.2) | March 2026     |
| 0.8.x   | ⚠️ Security only   | December 2025  |
| < 0.8   | ❌ No              | Ended          |

### Support Policy

- **Current Major Version**: Full support (features + security)
- **Previous Major Version**: Security updates for 6 months after new major release
- **Critical Healthcare Vulnerabilities**: Backported to all versions still in production use (best effort)

---

## Healthcare Threat Model

OpenHIMS operates in a high-risk environment where vulnerabilities can impact:

- **Patient Safety**: Corrupted medical data could lead to misdiagnosis or wrong treatment
- **Privacy**: Unauthorized PHI access violates HIPAA and patient trust
- **Availability**: Healthcare systems require high uptime
- **Integrity**: Medical records must be tamper-proof

### Critical Vulnerability Classifications

We use a healthcare-specific severity matrix:

| Severity | Description | Response Time |
|----------|-------------|---------------|
| **P0 - Critical** | PHI exposure, RCE, authentication bypass | 24 hours |
| **P1 - High** | DoS, privilege escalation, data corruption | 72 hours |
| **P2 - Medium** | Information disclosure, minor data leaks | 7 days |
| **P3 - Low** | Theoretical issues, no immediate exploit | 30 days |

---

## Reporting a Vulnerability

### 🔒 Responsible Disclosure

**DO NOT** open a public GitHub issue for security vulnerabilities. Instead, use one of our secure reporting channels:

### Reporting Channels

#### 1. **GitHub Security Advisory** (Preferred)

Report privately via: [https://github.com/openhims/rustcare-engine/security/advisories/new](https://github.com/openhims/rustcare-engine/security/advisories/new)

#### 2. **Email**

Send encrypted email to: **security@openhims.org**

**PGP Key**: Available at https://openhims.org/security-pgp.asc

```
Key ID: 0xABCD1234
Fingerprint: 1234 5678 9ABC DEF0 1234 5678 9ABC DEF0 1234 5678
```

#### 3. **Security Hotline** (Critical Issues Only)

For P0 vulnerabilities actively being exploited:
- Phone: +1-XXX-XXX-XXXX (24/7)
- Signal: Available upon request

---

## What to Include in Your Report

A good security report includes:

### Required Information

- **Summary**: Brief description of the vulnerability
- **Vulnerability Type**: RCE, SQLi, XSS, auth bypass, etc.
- **Severity Assessment**: Your estimate (P0-P3)
- **Affected Component**: Core, plugin, specific module
- **Affected Versions**: Which versions are vulnerable
- **Proof of Concept**: Steps to reproduce
- **Impact Analysis**: What can an attacker do?

### Optional but Helpful

- Suggested fix or mitigation
- Whether this is already publicly known
- If you plan to publish research (and when)
- CVE ID if already assigned

### Example Report

```markdown
## Summary
Authentication bypass in FHIR API endpoint allows unauthenticated access to patient records.

## Severity
P0 - Critical (PHI exposure)

## Affected Versions
- 1.0.0 through 1.2.3
- 0.9.x all versions

## Component
rustcare-fhir/src/api/auth.rs

## Proof of Concept
1. Send GET request to /fhir/Patient without Authorization header
2. Add header: X-Forwarded-For: 127.0.0.1
3. Receive full patient list response

## Impact
Remote attacker can access all patient records without authentication.

## Suggested Fix
Validate X-Forwarded-For header or remove trusted proxy bypass logic.
```

---

## Response Process

### What to Expect

1. **Acknowledgment** (24-48 hours)
   - Confirmation of receipt
   - Initial severity assessment
   - Tracking ID assigned

2. **Triage** (1-3 days)
   - Security team reproduces issue
   - Severity confirmed or adjusted
   - Affected versions identified

3. **Fix Development** (varies by severity)
   - Private patch developed
   - Fix tested in isolated environment
   - Backports prepared for supported versions

4. **Coordinated Disclosure** (varies)
   - Agree on disclosure timeline
   - Prepare security advisory
   - CVE requested if applicable

5. **Public Release**
   - Patch released to all supported versions
   - Security advisory published
   - Credit given to reporter (if desired)

### Timeline Expectations

| Severity | Initial Response | Fix Target | Disclosure |
|----------|-----------------|------------|------------|
| P0       | 4 hours         | 1-3 days   | 7 days     |
| P1       | 24 hours        | 7 days     | 30 days    |
| P2       | 3 days          | 30 days    | 60 days    |
| P3       | 7 days          | 90 days    | 90 days    |

---

## Scope

### In Scope

✅ **OpenHIMS Core Platform**
- All code in `rustcare-engine` repository
- Official plugins in `plugins/oss/`
- Official Docker images
- CI/CD pipeline
- Documentation site infrastructure

✅ **Security Issues**
- Authentication/authorization bypass
- SQL injection, command injection, code injection
- Cross-site scripting (XSS)
- Cross-site request forgery (CSRF)
- Server-side request forgery (SSRF)
- Remote code execution (RCE)
- PHI data leakage
- Cryptographic vulnerabilities
- Denial of Service (DoS) with low complexity
- Privilege escalation

### Out of Scope

❌ **Not Applicable**
- Third-party plugins (report to plugin author)
- User-deployed instances (unless common misconfiguration)
- Social engineering attacks
- Physical security
- DoS requiring significant resources
- Issues in unsupported versions
- Theoretical attacks without PoC

---

## Safe Harbor

OpenHIMS commits to:

- ✅ **No legal action** against security researchers who:
  - Report vulnerabilities responsibly via proper channels
  - Give us reasonable time to fix before public disclosure
  - Don't access or modify real patient data
  - Don't perform testing on third-party systems without permission
  
- ✅ **Public recognition** in our security hall of fame (optional)
- ✅ **CVE co-authorship** credit
- ✅ **Open dialogue** about fixes and disclosure timing

### Testing Guidelines

**Allowed**:
- Testing against local development instances
- Using synthetic test data only
- Automated scanning with rate limiting (<10 req/sec)

**Not Allowed**:
- Testing production systems without explicit permission
- Accessing real patient data (PHI)
- Social engineering staff or users
- Physical attacks on infrastructure
- Testing third-party deployments

---

## Bug Bounty Program

### Current Status

🚧 **Coming Q1 2026**

We are establishing a formal bug bounty program with monetary rewards. Details will be published at: https://openhims.org/security/bounty

### Interim Recognition

Until the formal program launches:
- Public acknowledgment in security advisories
- Listed in our [Security Hall of Fame](https://openhims.org/security/hall-of-fame)
- Contributor status for significant findings
- Opportunity to co-author CVE entries

---

## Security Features

### Built-in Protections

OpenHIMS includes:

- 🔐 **Encryption**
  - TLS 1.3 for all communications
  - AES-256-GCM for data at rest
  - Argon2id for password hashing
  
- 🛡️ **Access Control**
  - Role-based access control (RBAC)
  - Fine-grained permissions
  - Audit logging for all PHI access
  
- 🔍 **Monitoring**
  - Real-time security event logging
  - Anomaly detection
  - Failed authentication tracking
  
- 🧪 **Testing**
  - Automated security scanning in CI
  - Dependency vulnerability checks
  - Fuzzing for parsers

### Compliance Certifications

- ✅ HIPAA Security Rule requirements
- ✅ OWASP Top 10 mitigation
- 🚧 SOC 2 Type II (in progress)
- 🚧 ISO 27001 (planned)

---

## Security Advisories

### Subscription

Stay informed about security updates:

- **GitHub**: Watch repository with "Security alerts only"
- **Email**: security-announce@openhims.org
- **RSS**: https://openhims.org/security/advisories.xml

### Advisory Format

All advisories include:
- CVE identifier
- Affected versions
- Severity rating
- Impact description
- Mitigation steps
- Fixed versions
- Credit to reporter

---

## Security Best Practices

### For Deployers

Recommendations for production deployments:

```yaml
# Minimal security configuration
security:
  tls:
    enabled: true
    min_version: "1.3"
  
  authentication:
    password_policy:
      min_length: 12
      require_mfa: true
    
  logging:
    audit_level: "all_phi_access"
    retention_days: 365
  
  encryption:
    data_at_rest: true
    key_rotation_days: 90
```

See full hardening guide: https://docs.openhims.org/security/hardening

---

## Past Security Advisories

| Date | CVE | Severity | Description |
|------|-----|----------|-------------|
| *None yet* | - | - | *First release* |

---

## Security Team

Our security team includes:

- Healthcare IT security experts
- Rust security specialists
- HIPAA compliance consultants
- Penetration testing professionals

**Contact**: security@openhims.org

---

## Acknowledgments

We thank the following researchers for responsible disclosure:

🏆 **Security Hall of Fame**

*List will be maintained as reports are received*

---

## Resources

- [OWASP Healthcare Security Guidelines](https://owasp.org/www-project-healthcare/)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- [HIPAA Security Rule](https://www.hhs.gov/hipaa/for-professionals/security/)

---

## Legal

This security policy does not create any legally binding obligations. OpenHIMS provides the software "as-is" under the Apache 2.0 License with Healthcare Liability Clause. See [LICENSE](./LICENSE) for full terms.

---

*Last Updated: October 2025*  
*Version: 1.0*  
*Next Review: January 2026*

