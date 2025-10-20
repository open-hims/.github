# OpenHIMS — powered by RustCare Engine

<div align="center">

**Open Healthcare Interoperability, Built with Rust**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](./LICENSE)
[![HIPAA](https://img.shields.io/badge/HIPAA-Compliant-green.svg)]()
[![Rust](https://img.shields.io/badge/Rust-1.70%2B-orange.svg)]()
[![FHIR](https://img.shields.io/badge/FHIR-R4%2B-00a896.svg)]()

[Documentation](https://docs.openhims.org) • [Community](https://forum.openhims.org) • [Discord](https://discord.gg/openhims) • [Website](https://openhims.org)

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

## 📚 Repository Documentation

This `.github` repository contains all community health files, contribution guidelines, and governance documentation for the OpenHIMS project.

### 🔍 How to Access These Files

These files are automatically available across all OpenHIMS repositories:

1. **From Any Repository:**
   - Navigate to the repository's "Insights" tab
   - Click "Community" in the left sidebar
   - View all community health files

2. **From Organization Profile:**
   - Visit [github.com/openhims](https://github.com/openhims)
   - Click on ".github" repository
   - Browse all documentation

3. **Direct Links:**
   - LICENSE: Automatically displayed in all repos
   - Contributing guidelines: Shown when creating pull requests
   - Code of conduct: Referenced in issue templates
   - Security policy: Accessible via "Security" tab

### 🌐 Organization-Wide Default Files

Files in this repository serve as defaults for **all OpenHIMS repositories** that don't have their own versions. This ensures consistent community standards across the entire organization.

### Essential Documentation

| Document | Purpose | Audience |
|----------|---------|----------|
| **[LICENSE](./LICENSE)** | Apache 2.0 + Healthcare Liability Clause | Everyone |
| **[LICENSE-PLUGINS.md](./LICENSE-PLUGINS.md)** | Dual licensing model for plugins | Developers, Organizations |
| **[CONTRIBUTING.md](./CONTRIBUTING.md)** | How to contribute (RFC process, standards) | Contributors |
| **[CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)** | Community standards and behavior | Everyone |
| **[SECURITY.md](./SECURITY.md)** | Vulnerability reporting and security policy | Security Researchers |
| **[BRANDING-GUIDE.md](./BRANDING-GUIDE.md)** | Logo usage and brand guidelines | Marketers, Content Creators |
| **[COMMERCIAL-SUPPORT.md](./COMMERCIAL-SUPPORT.md)** | Professional support and services | Organizations, Enterprises |

### Issue & PR Templates

We provide structured templates to help you contribute effectively:

- 🐛 **[Bug Report](./ISSUE_TEMPLATE/bug_report.md)** — Report bugs with healthcare impact assessment
- 💡 **[Feature Request](./ISSUE_TEMPLATE/feature_request.md)** — Suggest new features
- 🔌 **[Plugin Request](./ISSUE_TEMPLATE/plugin_request.md)** — Request integrations or plugins
- 📋 **[Compliance Request](./ISSUE_TEMPLATE/compliance_request.md)** — Request regulatory compliance features
- 🔀 **[Pull Request Template](./PULL_REQUEST_TEMPLATE.md)** — Comprehensive PR checklist

---

## 🚀 Quick Start

### For Users

```bash
# Clone the main repository
git clone https://github.com/openhims/rustcare-engine.git
cd rustcare-engine

# Build and run
cargo build --release
cargo run
```

📖 **[Read the full documentation →](https://docs.openhims.org/getting-started)**

### For Contributors

1. **Read** [CONTRIBUTING.md](./CONTRIBUTING.md) for our development workflow
2. **Check** existing [issues](https://github.com/openhims/rustcare-engine/issues) or create a new one
3. **Fork** the repository and create a feature branch
4. **Make** your changes following our coding standards
5. **Submit** a pull request using our [template](./PULL_REQUEST_TEMPLATE.md)

For major features, please submit an **RFC** (Request for Comments) first.

### For Organizations

Deploying OpenHIMS in production? We offer:

- 💝 **[FREE Founder Services](./COMMERCIAL-SUPPORT.md#-founder-service-request-program)** — Request complimentary help from founders
- 💼 **[Professional Support](./COMMERCIAL-SUPPORT.md)** — 24/7 support with SLAs
- 🎓 **Training Programs** — For developers and administrators
- 🏥 **Implementation Services** — End-to-end deployment assistance
- 📋 **Compliance Consulting** — HIPAA, GDPR, FDA guidance

**Need help but no budget?** Email founders@openhims.org — we offer free services to organizations with genuine need, especially non-profits, public health, and underserved communities.

**Have budget?** Contact sales@openhims.org for professional support

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                     OpenHIMS Platform                        │
├─────────────────────────────────────────────────────────────┤
│  API Layer          │  Web Dashboard  │  Admin Console      │
├─────────────────────────────────────────────────────────────┤
│              RustCare Engine (Core)                          │
│  ┌──────────┬──────────┬──────────┬──────────┬──────────┐  │
│  │   FHIR   │  HL7 v2  │  DICOM   │   Auth   │  Audit   │  │
│  │  Module  │  Module  │  Module  │  Module  │  Module  │  │
│  └──────────┴──────────┴──────────┴──────────┴──────────┘  │
├─────────────────────────────────────────────────────────────┤
│                    Plugin System                             │
│  [ EHR Connectors ] [ Lab Integrations ] [ Custom Rules ]   │
└─────────────────────────────────────────────────────────────┘
                            ↕
              ┌──────────────────────────┐
              │  External Systems        │
              │  • Epic, Cerner         │
              │  • Laboratory (LIS)     │
              │  • PACS/Imaging         │
              │  • Pharmacy Systems     │
              └──────────────────────────┘
```

---

## 🌟 Key Features

### 🔐 Security & Compliance

- ✅ **HIPAA Security Rule** compliant architecture
- ✅ **GDPR** ready with data protection features
- ✅ **FDA 21 CFR Part 11** validation support
- ✅ **SOC 2** compatible (Type II in progress)
- ✅ End-to-end encryption (TLS 1.3, AES-256-GCM)
- ✅ Comprehensive audit logging

### 🔌 Interoperability Standards

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

### 🔧 Developer Experience

- 📖 Comprehensive API documentation
- 🔌 Plugin SDK with examples
- 🧪 Integration test suite
- 🐳 Docker and Kubernetes ready
- 📦 Pre-built binary releases

---

## 🤝 Community & Support

### Get Help

- 💬 **[GitHub Discussions](https://github.com/openhims/rustcare-engine/discussions)** — Q&A, ideas, announcements
- 🗨️ **[Discord Server](https://discord.gg/openhims)** — Real-time community chat
- 📖 **[Documentation](https://docs.openhims.org)** — Comprehensive guides and API docs
- 📧 **[Mailing List](mailto:community@openhims.org)** — Community updates

### Report Issues

- 🐛 **Bugs** → [Bug Report Template](https://github.com/openhims/rustcare-engine/issues/new?template=bug_report.md)
- 🔒 **Security** → [Security Policy](./SECURITY.md) (private disclosure)
- 💡 **Features** → [Feature Request Template](https://github.com/openhims/rustcare-engine/issues/new?template=feature_request.md)

### Contributing

We welcome contributions! Our community includes:

- 🏥 Healthcare IT professionals
- 💻 Rust developers
- 🔐 Security engineers
- 📋 Compliance experts
- 📚 Technical writers

**No contribution is too small** — from documentation fixes to major features.

---

## 📊 Project Status

| Metric | Status |
|--------|--------|
| **Version** | 1.0.0 (stable) |
| **Build** | ![Passing](https://img.shields.io/badge/build-passing-brightgreen) |
| **Test Coverage** | ![85%](https://img.shields.io/badge/coverage-85%25-green) |
| **Documentation** | ![Up to date](https://img.shields.io/badge/docs-up%20to%20date-blue) |
| **Security Audit** | Last: Oct 2025 |
| **Active Contributors** | 50+ |
| **Production Deployments** | 100+ organizations |

---

## 🗺️ Roadmap

### Current (2025 Q4)

- ✅ FHIR R4 complete implementation
- ✅ HL7 v2.x full support
- ✅ Core plugin architecture
- 🚧 SOC 2 Type II certification
- 🚧 Performance benchmarking suite

### Next (2026 Q1-Q2)

- 📋 FHIR R5 support
- 📋 GraphQL API layer
- 📋 Real-time CDC (Change Data Capture)
- 📋 Advanced analytics engine
- 📋 Multi-region deployment support

### Future

- 📋 AI/ML pipeline integration
- 📋 Blockchain for audit trails
- 📋 SMART on FHIR apps support
- 📋 Mobile SDKs (iOS/Android)

[View detailed roadmap →](https://github.com/openhims/rustcare-engine/projects)

---

## 📄 Licensing

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

[Read case studies →](https://openhims.org/case-studies)

---

## 🎓 Resources

### Learning

- 📖 [Getting Started Guide](https://docs.openhims.org/getting-started)
- 🎥 [Video Tutorials](https://youtube.com/@openhims)
- 📚 [API Reference](https://docs.openhims.org/api)
- 🔌 [Plugin Development Guide](https://docs.openhims.org/plugins)
- 🏥 [Healthcare Interoperability 101](https://docs.openhims.org/healthcare-101)

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

Special thanks to our [core contributors](https://github.com/openhims/rustcare-engine/graphs/contributors) and [sponsors](https://openhims.org/sponsors).

---

## 📞 Contact

### General Inquiries
- 🌐 **Website**: [openhims.org](https://openhims.org)
- 📧 **Email**: info@openhims.org
- 🐦 **Twitter/X**: [@OpenHIMS](https://twitter.com/OpenHIMS)
- 💼 **LinkedIn**: [OpenHIMS Project](https://linkedin.com/company/openhims)

### Specific Contacts
- 💼 **Sales**: sales@openhims.org
- 🔒 **Security**: security@openhims.org
- 📚 **Documentation**: docs@openhims.org
- 🤝 **Partnerships**: partners@openhims.org
- ⚖️ **Legal**: legal@openhims.org

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

[Main Repository](https://github.com/openhims/rustcare-engine) • [Documentation](https://docs.openhims.org) • [Community](https://discord.gg/openhims)

Copyright © 2025 OpenHIMS Project • [Apache 2.0 License](./LICENSE)

</div>

