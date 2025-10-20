# Plugin and Package Licensing Model

## Overview

OpenHIMS follows a **three-tier licensing model** to balance open-source collaboration with sustainable development of specialized features:

1. **Open-Source Core** — Apache 2.0 (with healthcare/corporate clauses)
2. **Open-Source Plugins** — Apache 2.0 (community-developed extensions)
3. **Commercial-Only Packages** — Proprietary (advanced enterprise features)

This document explains how each tier works and what you can expect.

---

## Core Platform License

The **OpenHIMS core platform** (RustCare Engine) is licensed under the **Apache 2.0 License** with additional Healthcare Liability and Corporate Use Restriction clauses. This ensures:

- ✅ Free and open-source usage
- ✅ Permissive modification and redistribution
- ✅ Commercial use allowed
- ✅ Patent grant protection

See the main [LICENSE](./LICENSE) file for full details.

---

## Three-Tier Model Explained

### Tier 1: **Open-Source Core Platform** (Apache 2.0 + Restrictions)

The foundation — fully functional, production-ready healthcare interoperability engine.

**Includes:**
- HL7 FHIR R4 support
- HL7 v2.x message processing
- Basic DICOM support
- Authentication and authorization
- Audit logging
- Encryption and security
- Plugin architecture and SDK
- REST APIs
- Basic administration tools

**License**: Apache 2.0 with Healthcare Liability and Corporate Use Restrictions

**Free for**: Small businesses (<$10M revenue, <100 employees), non-profits, academic institutions, development/testing

**Commercial license required for**: Enterprise production use ($10M+ revenue OR 100+ employees)

---

### Tier 2: **Open-Source Plugins** (Apache 2.0)

General-purpose plugins that enhance core functionality remain open-source under Apache 2.0:

- Basic data transformations
- Common integrations (HL7, FHIR base adapters)
- Standard authentication modules
- Performance monitoring tools
- Community-contributed enhancements

**Location**: `/plugins/oss/`

**License**: Apache 2.0 (same as core)

---

### Tier 3: **Commercial-Only Packages** (Proprietary)

**Pure commercial packages** with NO source code access — distributed as binary/compiled only.

These are advanced enterprise features that go beyond the open-source offerings:

**Examples:**
- **OpenHIMS Enterprise Manager** — Advanced multi-tenant admin console
- **OpenHIMS Analytics Platform** — Advanced BI, reporting, and dashboards
- **OpenHIMS AI/ML Extensions** — Predictive analytics and machine learning
- **OpenHIMS Cloud Control Plane** — Multi-region orchestration
- **OpenHIMS HL7 Accelerator Pro** — High-performance message processing
- **OpenHIMS Enterprise Security Bundle** — Advanced threat detection
- **OpenHIMS Compliance Suite Pro** — Multi-regulation automated compliance

**Key Characteristics:**
- ❌ **NO source code** provided (proprietary)
- ✅ Binary/compiled distribution only
- ✅ Each package has its own EULA
- ✅ Subscription or perpetual licensing
- ✅ Includes support and updates
- ✅ 30-90 day trial periods available
- ✅ Free for non-profits (case-by-case)

**Location**: Available at [https://openhims.org/commercial/packages](https://openhims.org/commercial/packages)

**Pricing**: Custom based on organization size and usage

**Contact**: commercial@openhims.org

**Important**: Commercial-only packages are completely **separate** from open-source components. The core platform remains fully functional without them.

---

## Historical: Dual-Licensed Compliance Plugins

**Note**: This section describes our previous dual-licensing model for compliance plugins. We are transitioning to the three-tier model above, but existing dual-licensed plugins remain available.

Specialized compliance and regulatory plugins previously offered under **dual licensing** (open-source OR commercial):

- **HIPAA Business Associate Agreement (BAA) compliance toolkit**
- **FDA 21 CFR Part 11 validation suite**
- **GDPR healthcare data processing modules**
- **SOC 2 Type II audit logging**
- **HL7 FHIR R4+ certified validators**
- **Region-specific regulatory adapters** (EU MDR, Japan PMDA, etc.)

**Location**: Available via [OpenHIMS Registry](https://registry.openhims.org) or direct contact

**Pricing Model**:
- **Free** for evaluation and non-production use
- **Tiered pricing** based on deployment scale:
  - Small clinics (<10,000 patients): $500/year per plugin
  - Medium organizations (10k-100k patients): $2,500/year per plugin
  - Large enterprises (100k+ patients): Custom pricing
- **Enterprise bundles** available with support SLAs

---

## Why Dual Licensing?

### Sustainability
Compliance work requires:
- Continuous monitoring of regulatory changes
- Expensive certification processes
- Legal review and documentation
- Dedicated support for mission-critical deployments

### Community First
- Core platform remains fully open
- No "bait and switch" — everything needed for basic operation is OSS
- Compliance plugins are **optional enhancements**
- All plugin APIs are open and documented

### Transparency
- Clear separation between OSS and commercial offerings
- Community can build competing compliance plugins
- No vendor lock-in — plugin architecture is open

---

## Contribution Guidelines

### Contributing to Open-Source Plugins

1. All contributions to OSS plugins automatically fall under Apache 2.0
2. Submit via standard pull request with RFC (for major features)
3. See [CONTRIBUTING.md](./CONTRIBUTING.md) for process

### Contributing to Compliance Plugins

If you wish to contribute to commercial compliance plugins:

1. **Contributor License Agreement (CLA)** required
2. Contact: legal@openhims.org
3. Contributors may receive:
   - Revenue sharing for significant contributions
   - Free license for contributed plugins
   - Recognition in credits

---

## Building Your Own Compliance Plugins

You are **free to build and distribute** your own compliance plugins under any license you choose:

- Plugin SDK is Apache 2.0
- No restrictions on third-party plugins
- Can be open-source or commercial
- Can compete directly with official plugins

We encourage ecosystem diversity!

---

## License Enforcement

### For Organizations
- Honor system for small/non-profit uses
- Enterprise deployments require license verification
- Audit logs may be checked for compliance (with notice)

### For Developers
- Core platform: No restrictions beyond Apache 2.0 terms
- Commercial plugins: License key validation at runtime
- Source available for audit, but modification prohibited without license

---

## Getting Commercial Licenses

**Self-Service**: [https://registry.openhims.org/licenses](https://registry.openhims.org/licenses)

**Enterprise Inquiries**: sales@openhims.org

**Academic/Non-Profit**: discounts@openhims.org (up to 90% discount available)

**Open-Source Projects**: Apply for free licensing at oss-grants@openhims.org

---

## Frequently Asked Questions

### Can I use OpenHIMS commercially without paying?

**Yes!** The core platform is fully open-source. Commercial licenses are only needed for specialized compliance plugin modules.

### What if I only need HIPAA compliance?

You can build it yourself using the OSS core, or license our certified HIPAA plugin for peace of mind and ongoing regulatory updates.

### Can I fork and modify commercial plugins?

No. Commercial plugins are source-available for audit purposes only. However, you can use our plugin SDK to build competing implementations.

### Do prices include support?

Basic licenses include community support. Premium support with SLAs is available separately—see [COMMERCIAL-SUPPORT.md](./COMMERCIAL-SUPPORT.md).

---

## License Comparison Table

| Feature | Core Platform | OSS Plugins | Dual-Licensed Plugins | Commercial-Only Packages |
|---------|--------------|-------------|----------------------|-------------------------|
| License | Apache 2.0 + Clauses | Apache 2.0 | Apache 2.0 OR Commercial | Proprietary (EULA) |
| Cost | Free* | Free | Free OR Paid | Paid only |
| Source Code | ✅ Available | ✅ Available | ✅ Available (audit for commercial) | ❌ NOT Available |
| Modification | ✅ Allowed | ✅ Allowed | ✅ OSS version / ❌ Commercial version | ❌ Prohibited |
| Redistribution | ✅ Allowed | ✅ Allowed | ✅ OSS version / ❌ Commercial version | ❌ Prohibited |
| Enterprise Use | Commercial license | ✅ Allowed | Requires License | Requires License |
| Certification | Community | Community | Official (commercial) | Official |
| Support | Community | Community | Included (commercial) | Included |
| Trial Period | N/A | N/A | Available | 30-90 days |
| Reverse Engineering | Allowed | Allowed | ❌ Prohibited (commercial) | ❌ Prohibited |

\* Free for small businesses, non-profits, academics. Commercial license required for enterprises ($10M+ revenue OR 100+ employees) in production.

---

## Contact

**Legal Questions**: legal@openhims.org  
**Open-Source Licensing**: licenses@openhims.org  
**Commercial Packages**: commercial@openhims.org  
**Enterprise Sales**: sales@openhims.org  
**General Support**: support@openhims.org  
**Community Forum**: [https://forum.openhims.org](https://forum.openhims.org)

**Package Catalog**: [https://openhims.org/commercial/packages](https://openhims.org/commercial/packages)

---

*Last Updated: October 2025*  
*Version: 1.0*

