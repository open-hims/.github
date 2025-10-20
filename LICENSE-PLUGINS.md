# Plugin Licensing Model

## Overview

OpenHIMS follows a **dual licensing model** to balance open-source collaboration with sustainable development of specialized compliance features.

---

## Core Platform License

The **OpenHIMS core platform** (RustCare Engine) is licensed under the **Apache 2.0 License** with an additional Healthcare Liability Clause. This ensures:

- ✅ Free and open-source usage
- ✅ Permissive modification and redistribution
- ✅ Commercial use allowed
- ✅ Patent grant protection

See the main [LICENSE](./LICENSE) file for full details.

---

## Plugin Licensing Categories

### 1. **Open-Source Plugins** (Apache 2.0)

General-purpose plugins that enhance core functionality remain open-source under Apache 2.0:

- Basic data transformations
- Common integrations (HL7, FHIR base adapters)
- Standard authentication modules
- Performance monitoring tools
- Community-contributed enhancements

**Location**: `/plugins/oss/`

**License**: Apache 2.0 (same as core)

---

### 2. **Compliance Plugins** (Commercial License)

Specialized compliance and regulatory plugins are offered under a **commercial license** to support ongoing development and certification maintenance:

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

| Feature | Core Platform | OSS Plugins | Commercial Plugins |
|---------|--------------|-------------|-------------------|
| License | Apache 2.0 + Healthcare Clause | Apache 2.0 | Commercial |
| Cost | Free | Free | Paid (with free tier) |
| Source Code | Available | Available | Available (audit only) |
| Modification | Allowed | Allowed | Restricted |
| Redistribution | Allowed | Allowed | Prohibited |
| Commercial Use | Allowed | Allowed | Requires License |
| Certification | Community | Community | Official/Certified |
| Support | Community | Community | Included (varies by tier) |

---

## Contact

**Legal Questions**: legal@openhims.org  
**Licensing Inquiries**: licenses@openhims.org  
**General Support**: support@openhims.org  
**Community Forum**: [https://forum.openhims.org](https://forum.openhims.org)

---

*Last Updated: October 2025*  
*Version: 1.0*

