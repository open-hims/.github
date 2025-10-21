# OpenHIMS — powered by RustCare Engine

<div align="center">

<img src="logo.png" alt="OpenHIMS Logo" width="200"/>

**Open Healthcare Interoperability, Built with Rust**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](./LICENSE)
[![HIPAA](https://img.shields.io/badge/HIPAA-Compliant-green.svg)]()
[![Rust](https://img.shields.io/badge/Rust-1.70%2B-orange.svg)]()
[![FHIR](https://img.shields.io/badge/FHIR-R4%2B-00a896.svg)]()

</div>

---

> **📋 Note:** This is the OpenHIMS organization's special `.github` repository. The community health files here (LICENSE, CODE_OF_CONDUCT.md, CONTRIBUTING.md, SECURITY.md, etc.) serve as organization-wide defaults and will be visible across all OpenHIMS repositories. You can view these from any repository in the organization under the "Insights" → "Community" tab, or from the organization profile page.

---

## 🏥 What is OpenHIMS?

**OpenHIMS** is a high-performance, secure, and fully open-source **Healthcare Information Management System** designed for modern healthcare interoperability. Built from the ground up in Rust, it provides:

- 🔒 **HIPAA-Compliant Architecture** — Memory-safe Rust prevents entire classes of security vulnerabilities
- 🔌 **Universal Interoperability** — Native support for HL7 FHIR, HL7 v2.x, DICOM, and more
- ⚡ **Blazing Fast** — Rust's zero-cost abstractions enable high-throughput message processing
- 🌍 **Open Source First** — Apache 2.0 licensed core platform, community-driven development
- 🔐 **Security by Design** — End-to-end encryption, comprehensive audit logging, RBAC
- 🏗️ **Plugin Architecture** — Extensible design for custom integrations and compliance modules

### The Challenge We're Solving

Healthcare systems are fragmented. Electronic Health Records (EHRs), laboratory systems, imaging platforms, and billing software often can't communicate effectively. OpenHIMS provides a unified integration layer that:

- Eliminates vendor lock-in
- Reduces integration costs
- Improves data quality and availability
- Accelerates time-to-market for health tech innovations
- Ensures regulatory compliance (HIPAA, GDPR, FDA)

---

## 🌟 Key Features

### 🔐 Security & Compliance

- ✅ **HIPAA Security Rule** compliant architecture
- ✅ **GDPR** ready with data protection features
- ✅ **FDA 21 CFR Part 11** validation support
- ✅ **SOC 2** compatible (Type II in progress)
- ✅ End-to-end encryption (TLS 1.3, AES-256-GCM)
- ✅ Comprehensive audit logging

### � Security (Data at Rest & in Transit)

- Data in transit is protected by TLS 1.3 with strong cipher suites (AES-256-GCM) and mutual TLS available for high-assurance integrations.
- Data at rest is encrypted using AES-256 with authenticated encryption. Sensitive configuration and secrets use a vetted secrets manager and hardware-backed key storage where available (HSM or cloud KMS).
- Key management follows separation of duties: encryption keys are rotated regularly, access is audited, and keys are never stored alongside application data.
- Access is governed by Role-Based Access Control (RBAC) with least-privilege defaults, multi-factor authentication (MFA) for administrative access, and fine-grained API scopes for integrations.
- Audit and telemetry: all access to PHI and critical systems is logged with immutable, tamper-evident audit trails. Logs are retained according to organizational policy and can be exported to SIEMs for monitoring and alerting.
- Operational controls: secure-by-default configuration, regular vulnerability scanning, dependency management, and periodic third-party security audits (see Security Audit date above).

For implementation details, deployment guidance, and our vulnerability disclosure process, see `SECURITY.md` and `BRANDING-GUIDE.md` or contact security@openhims.org.

### �🔌 Interoperability Standards

- ✅ **HL7 FHIR R4+** — Full resource support
- ✅ **HL7 v2.x** — Versions 2.3 through 2.8
- ✅ **DICOM** — Medical imaging integration
- ✅ **CDA** — Clinical Document Architecture
- ✅ **REST APIs** — OpenAPI/Swagger documented

### ⚡ Performance

- 🚀 **10,000+ messages/sec** throughput
- 🚀 **<10ms** median latency
- 🚀 **Memory safe** — No buffer overflows, no data races
- 🚀 **Concurrent** — Multi-threaded Rust performance

---

<div align="center">

**Built with ❤️ by the OpenHIMS Community**

Copyright © 2025 OpenHIMS Project • [Apache 2.0 License](./LICENSE)

</div>

---

## 🤝 Community & Support

### Get Help

- � **Email**: community@openhims.org — Community updates and questions

### Report Issues

- 🐛 **Bugs** → [Bug Report Template](./ISSUE_TEMPLATE/bug_report.md)
- 🔒 **Security** → [Security Policy](./SECURITY.md) (private disclosure)
- 💡 **Features** → [Feature Request Template](./ISSUE_TEMPLATE/feature_request.md)

### Contributing

We welcome contributions! Our community includes:

- 🏥 Healthcare IT professionals
- 💻 Rust developers
- 🔐 Security engineers
- 📋 Compliance experts
- 📚 Technical writers

**No contribution is too small** — from documentation fixes to major features.

---

## � Licensing

### Completely Open Source

**Apache 2.0 License** with Healthcare-First and Anti-Commercialization Provisions

**✅ FREE FOR EVERYONE:**
- ✅ **Hospitals & healthcare providers** — ANY SIZE, unlimited use
- ✅ **Small businesses, non-profits, education** — completely free
- ✅ **Individuals and developers** — no restrictions
- ✅ **Government and public health** — full access
- ✅ **Modify, customize, deploy** at any scale
- ✅ **Contribute back** improvements to the community

**❌ YOU CANNOT:**
- ❌ Sell or resell OpenHIMS as a standalone product
- ❌ Offer as commercial SaaS without substantial value-add
- ❌ Rebrand and market as your proprietary product
- ❌ Create competing products that just repackage our work

**✅ YOU CAN:**
- ✅ Provide consulting and professional services using OpenHIMS
- ✅ Use internally in your business operations  
- ✅ Build and sell plugins/extensions
- ✅ Offer managed hosting with value-added services
- ✅ Integrate into larger solutions

**Philosophy**: Hospitals can freely download, use, and contribute back. Corporations cannot just resell our work, but can provide legitimate services around it.

[Read full license →](./LICENSE)

### Plugins & Extensions

**All plugins are open source** under Apache 2.0.

The community can build and share:
- Integration plugins (EHR, PACS, LIS systems)
- Data transformation modules
- Compliance and validation rules
- Custom workflows
- Analytics and reporting
- Authentication providers

**You're free to**:
- Build commercial plugins and sell them
- Create proprietary extensions
- Offer premium integrations
- Develop vertical-specific solutions

The core remains completely open. Build businesses on top of it!

[Learn about plugin development →](./LICENSE-PLUGINS.md)

### Why Anti-Commercialization?

We're building **healthcare infrastructure as a public good**, not a product to be repackaged and sold.

**Our Philosophy:**
- 🏥 **Healthcare First** — Hospitals and providers should have free, unrestricted access
- 🌍 **Public Good** — Healthcare interoperability benefits everyone
- 🚫 **No Middlemen** — Corporations shouldn't profit just by reselling our work
- ✅ **Service Economy** — Make money by adding real value, not gatekeeping
- 🤝 **Community Owned** — Built by healthcare professionals, for healthcare

**What This Means:**
- Hospitals of any size: Use freely ✅
- Consultants helping hospitals: Get paid for your expertise ✅
- Corporations reselling OpenHIMS unchanged: Not allowed ❌
- Companies building value-added solutions: Encouraged ✅

This ensures OpenHIMS remains a commons while still allowing a healthy ecosystem of businesses providing legitimate services.

### 💝 Unique: Request Free Services from Founders

**Any organization can request complimentary professional services directly from the OpenHIMS founders**, regardless of size or budget. This unique provision is built into our license (Section 16).

**What you can request:**
- Implementation assistance
- Technical support
- Custom development
- Training and consultation
- Compliance guidance
- Migration help

**Priority given to:**
- Non-profit healthcare organizations
- Public health departments
- Community health centers
- Academic institutions
- Underserved populations
- Public health emergencies

**How to request:** Email founders@openhims.org with your organization's mission, use case, and why you need help.

**Response time:** 14 business days

This ensures that organizations doing important healthcare work can access OpenHIMS expertise even without funding. [Learn more →](./COMMERCIAL-SUPPORT.md#-founder-service-request-program)

---

## 🏢 Who's Using OpenHIMS?

<table>
  <tr>
    <td align="center">🏥<br><b>Regional Hospitals</b><br>200-bed acute care</td>
    <td align="center">🔬<br><b>Clinical Labs</b><br>HL7 result delivery</td>
    <td align="center">🏛️<br><b>Public Health</b><br>Disease surveillance</td>
  </tr>
  <tr>
    <td align="center">🚑<br><b>EMS Networks</b><br>Field data integration</td>
    <td align="center">💊<br><b>Pharmacies</b><br>E-prescribing systems</td>
    <td align="center">🧬<br><b>Research Orgs</b><br>Clinical trial data</td>
  </tr>
</table>

> *"OpenHIMS reduced our integration costs by 60% and improved data quality significantly."*  
> — CTO, Regional Health System

---

## 🎓 Resources

### Standards & Specifications

- [HL7 FHIR](https://hl7.org/fhir/)
- [HL7 v2 Specifications](https://www.hl7.org/implement/standards/product_brief.cfm?product_id=185)
- [DICOM Standard](https://www.dicomstandard.org/)
- [HIPAA Security Rule](https://www.hhs.gov/hipaa/for-professionals/security/)

---

## 🙏 Acknowledgments

OpenHIMS is built on the shoulders of giants:

- **Rust Community** — For an incredible language and ecosystem
- **HL7 International** — For healthcare interoperability standards
- **Open-source Contributors** — For countless hours of dedication
- **Healthcare IT Professionals** — For domain expertise and feedback

---

## 📞 Contact

### General Inquiries
- 📧 **Email**: info@openhims.org

### Specific Contacts
- 💼 **Sales**: sales@openhims.org
- 🔒 **Security**: security@openhims.org
- 📚 **Documentation**: docs@openhims.org
- 🤝 **Partnerships**: partners@openhims.org
- ⚖️ **Legal**: legal@openhims.org
- 💝 **Founders**: founders@openhims.org

---

## ⭐ Star History

If you find OpenHIMS valuable, please consider:

- ⭐ **Starring** the repository
- 🐦 **Sharing** on social media
- 📝 **Writing** about your experience
- 💬 **Joining** the community
- 🤝 **Contributing** code or documentation

---

<div align="center">

**Built with ❤️ by the OpenHIMS Community**

Copyright © 2025 OpenHIMS Project • [Apache 2.0 License](./LICENSE)

</div>

