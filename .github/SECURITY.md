# Security Policy

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

The RustCare team takes security seriously. We appreciate your efforts to responsibly disclose your findings.

### Reporting Process

#### 1. Send a Report

Send an email to: **security@openhims.health**

Include the following information:
- Type of vulnerability (e.g., SQL injection, XSS, authentication bypass)
- Full paths of affected source file(s)
- Location of the affected source code (tag/branch/commit or direct URL)
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact assessment and suggested severity
- Any potential mitigations you've identified

#### 2. Encrypted Communication (Optional)

For sensitive disclosures, use our PGP key:
- **PGP Key:** Available at https://pages.openhims.health/pgp
- **Fingerprint:** `[To be added]`

#### 3. What to Expect

**Initial Response:**
- We will acknowledge receipt within **48 hours**
- We'll assign a tracking ID for your report

**Triage:**
- We will validate and triage the issue within **1 week**
- We'll provide an initial assessment and expected timeline

**Resolution:**
- **Critical vulnerabilities:** Patched within **7 days**
- **High severity:** Patched within **14 days**
- **Medium severity:** Patched within **30 days**
- **Low severity:** Patched within **90 days**

**Disclosure:**
- We coordinate public disclosure with you
- Credit given unless you prefer anonymity
- CVE assigned for confirmed vulnerabilities
- Security advisory published on GitHub

---

## Supported Versions

| Version | Supported          | End of Support |
| ------- | ------------------ | -------------- |
| 0.x.x   | :white_check_mark: | Active Development |
| 1.x.x   | :white_check_mark: | TBD (when released) |

**Note:** As an early-stage project, we're currently supporting the latest development version. Once we reach 1.0, we'll maintain the latest major version plus security patches for the previous major version.

---

## Security Update Policy

### Update Channels

1. **Security Advisories**
   - Published at: https://github.com/open-hims/rustcare-engine/security/advisories
   - Includes severity, impact, and mitigation steps

2. **Security Releases**
   - Tagged with `security-` prefix (e.g., `v0.5.1-security`)
   - Published on GitHub Releases
   - Includes upgrade instructions

3. **Notifications**
   - GitHub Security Advisories (automatic)
   - Mailing list: security-announce@openhims.health (planned)
   - RSS feed: https://github.com/open-hims/rustcare-engine/security/advisories.atom

### Patch Distribution

Security patches are released as:
- Source code updates on GitHub
- Docker images with updated tags
- Cargo crate updates (when published)
- Binary releases for supported platforms

---

## Security Best Practices for Deployment

### 1. Keep Software Updated

```bash
# Check for updates weekly
git pull origin main
cargo update

# Review security advisories
gh api /repos/open-hims/rustcare-engine/security-advisories
```

### 2. Use Secrets Management

**Never hardcode secrets.** Use:
- HashiCorp Vault
- AWS Secrets Manager
- Azure Key Vault
- Kubernetes Secrets

See: [Secrets Service Documentation](docs/SECRETS_API.md)

### 3. Enable Audit Logging

```toml
# config/audit.toml
[audit]
enabled = true
log_level = "info"
retention_days = 2555  # 7 years for HIPAA compliance
tamper_evident = true
```

### 4. Configure TLS/SSL

```toml
# config/tls.toml
[tls]
enabled = true
cert_file = "/path/to/cert.pem"
key_file = "/path/to/key.pem"
min_version = "1.3"  # TLS 1.3 minimum
```

### 5. Implement Network Segmentation

- Deploy auth services in separate network zone
- Use firewall rules to restrict access
- Enable DDoS protection
- Use VPN for administrative access

### 6. Regular Security Audits

```bash
# Run security audit tools
cargo audit
cargo clippy -- -D warnings
cargo deny check

# Static analysis
cargo-geiger  # Check unsafe code usage
```

### 7. Monitor and Alert

- Enable application monitoring (Prometheus/Grafana)
- Set up security event alerts
- Review audit logs regularly
- Track failed authentication attempts

---

## Security Features

### Built-in Security

RustCare includes enterprise-grade security features:

#### Memory Safety
- Built with Rust (eliminates 70% of vulnerabilities)
- No buffer overflows or use-after-free bugs
- Compile-time memory safety guarantees

#### Authentication & Authorization
- OAuth 2.0 / OpenID Connect
- JWT token-based authentication
- Fine-grained authorization (Zanzibar)
- Multi-factor authentication (MFA)
- Session management with secure tokens

#### Encryption
- **At Rest:** AES-256-GCM with envelope encryption
- **In Transit:** TLS 1.3 minimum
- **Database:** Transparent data encryption (TDE)
- **Backups:** Encrypted with separate keys

#### Audit Logging
- Comprehensive tamper-evident logs
- Merkle tree verification
- HIPAA-compliant retention (7 years)
- Automated log analysis and alerting

#### Access Control
- Role-Based Access Control (RBAC)
- Attribute-Based Access Control (ABAC)
- Principle of least privilege
- Regular access reviews

#### Data Protection
- PHI/PII classification and tagging
- Data masking for non-authorized users
- Automated PII redaction in logs
- GDPR right-to-erasure support

---

## Security Testing

We maintain comprehensive security testing:

### Static Analysis
- CodeQL analysis (GitHub Advanced Security)
- Cargo Clippy with strict lints
- Dependency vulnerability scanning (cargo-audit)
- License compliance checking (cargo-deny)

### Dynamic Analysis
- Regular penetration testing (planned)
- Fuzzing with cargo-fuzz (planned)
- DAST scanning with OWASP ZAP (planned)

### Manual Review
- Security-focused code reviews
- Threat modeling for new features
- Architecture security reviews
- Third-party security audits (annually, when funded)

---

## Bug Bounty Program

**Status:** Planned (pending funding)

We plan to launch a bug bounty program offering rewards for responsibly disclosed vulnerabilities.

**Interested in participating?** Email: security@openhims.health

**Expected Rewards:**
- Critical: $500-$2,000
- High: $250-$1,000
- Medium: $100-$500
- Low: $50-$250

---

## Security Hall of Fame

We recognize security researchers who help make RustCare more secure:

*No reports yet - be the first!*

To be listed (with your permission):
- Responsibly disclose a valid security vulnerability
- Follow our disclosure policy
- Allow public disclosure of your finding

---

## Compliance

### Healthcare Compliance

RustCare is designed to support:

- **HIPAA** (Health Insurance Portability and Accountability Act)
- **GDPR** (General Data Protection Regulation)
- **HITECH** (Health Information Technology for Economic and Clinical Health)
- **FDA 21 CFR Part 11** (Electronic Records and Signatures)
- **WHO Regulations** (World Health Organization standards)

### Security Standards

We follow industry best practices:

- **OWASP Top 10** - Web application security
- **SANS Top 25** - Most dangerous software errors
- **NIST Cybersecurity Framework**
- **CIS Benchmarks** - Configuration security
- **OpenSSF Best Practices** (in progress)

---

## Security Roadmap

See our comprehensive security roadmap: [SECURITY_ROADMAP.md](.github/SECURITY_ROADMAP.md)

**Key Milestones:**
- Q4 2025: OpenSSF Best Practices Badge (Passing)
- Q1 2026: SLSA Level 2, Professional Security Audit
- Q2 2026: SLSA Level 3, Bug Bounty Program
- Q4 2026: SOC 2 Type II Certification

---

## Contact

### Security Team

- **Email:** security@openhims.health
- **PGP Key:** https://pages.openhims.health/pgp
- **Response Time:** 48 hours for acknowledgment

### General Support

- **Email:** support@pages.openhims.health
- **Discussions:** https://github.com/open-hims/rustcare-engine/discussions
- **Issues:** https://github.com/open-hims/rustcare-engine/issues

---

## Legal

### Safe Harbor

We will not pursue legal action against security researchers who:
1. Follow this disclosure policy
2. Act in good faith
3. Do not access or modify user data beyond what's necessary
4. Do not perform Denial of Service attacks
5. Do not publicly disclose before coordinated disclosure

### Scope

**In Scope:**
- RustCare Engine Core (this repository)
- RustCare UI (rustcare-ui repository)
- RustCare Infrastructure (rustcare-infra repository)
- Deployed demo instances (*.openhims.health)

**Out of Scope:**
- Third-party services (databases, cloud providers)
- Social engineering attacks
- Physical security
- Spam or phishing

---

<p align="center">
  <strong>Thank you for helping keep RustCare and our users safe! 🛡️</strong>
</p>

<p align="center">
  <sub>Last Updated: October 28, 2025</sub>
</p>
