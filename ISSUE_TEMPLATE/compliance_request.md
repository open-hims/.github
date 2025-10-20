---
name: 📋 Compliance Rule Request
about: Request support for healthcare compliance rules, regulations, or standards
title: '[COMPLIANCE] '
labels: 'compliance, enhancement, needs-review'
assignees: ''
---

## Compliance Requirement Overview

**Regulation/Standard Name:**


**Issuing Authority:**
- [ ] CMS (Centers for Medicare & Medicaid Services)
- [ ] FDA (Food and Drug Administration)
- [ ] ONC (Office of the National Coordinator)
- [ ] HHS (Department of Health and Human Services)
- [ ] EU Medical Device Regulation
- [ ] National authority (specify country: )
- [ ] Standards organization (HL7, IHE, etc.)
- [ ] Other: 

**Type of Requirement:**
- [ ] New regulation/rule
- [ ] Update to existing regulation
- [ ] Industry standard (HL7, FHIR, DICOM, etc.)
- [ ] Certification requirement
- [ ] Best practice guideline
- [ ] Regional/country-specific law

## Regulatory Details

**Official Regulation Reference:**
- Regulation ID/Number: 
- Section/Clause: 
- Effective Date: 
- Compliance Deadline: 

**Official Documentation:**
- Link: 
- PDF/Document: (attach or link)

**Geographic Scope:**
- [ ] United States
- [ ] European Union
- [ ] United Kingdom
- [ ] Canada
- [ ] Australia
- [ ] Asia-Pacific (specify: )
- [ ] Global/Multi-region
- [ ] Other: 

## Compliance Requirement Description

**What does this regulation require?**


**Specific technical requirements:**

1. 
2. 
3. 

## Impact on OpenHIMS

**Which OpenHIMS components are affected?**
- [ ] Core engine
- [ ] FHIR module
- [ ] HL7 v2.x module
- [ ] Authentication/authorization
- [ ] Audit logging
- [ ] Data encryption
- [ ] API layer
- [ ] Storage layer
- [ ] Plugins (specify: )
- [ ] Other: 

**Nature of changes needed:**
- [ ] New validation rules
- [ ] Data model changes
- [ ] API modifications
- [ ] Security enhancements
- [ ] Audit trail requirements
- [ ] Documentation/reporting
- [ ] Configuration options
- [ ] Other: 

## Current State

**Does OpenHIMS currently support this requirement?**
- [ ] Yes, fully compliant
- [ ] Partially compliant (explain gap: )
- [ ] No, not currently supported
- [ ] Unknown

**If partially compliant, what's missing?**


## Technical Requirements

### Validation Rules

**What needs to be validated?**


**Example valid data:**

```json
// Example compliant data structure

```

**Example invalid data:**

```json
// Example that should fail validation

```

### Data Requirements

**Required data fields:**

| Field Name | Data Type | Required? | Format/Constraints | Example |
|------------|-----------|-----------|-------------------|---------|
| | | [ ] Yes [ ] No | | |
| | | [ ] Yes [ ] No | | |

### Audit Requirements

**What events must be audited?**
- [ ] Data access
- [ ] Data modifications
- [ ] Authentication events
- [ ] Authorization failures
- [ ] Configuration changes
- [ ] Export/transmission of data
- [ ] Other: 

**Audit retention period:**


### Security Requirements

**Security controls needed:**
- [ ] Encryption at rest
- [ ] Encryption in transit
- [ ] Access control
- [ ] Multi-factor authentication
- [ ] Password policies
- [ ] Session management
- [ ] Other: 

## Implementation Approach

**Proposed implementation:**


**Breaking changes:**
- [ ] Yes, this requires breaking changes
- [ ] No, can be backward compatible
- [ ] Optional feature flag

**Configuration needed:**

```yaml
# Example configuration for this compliance requirement
compliance:
  rule_name:
    enabled: true
    # ... options
```

## Testing & Validation

**How should compliance be verified?**


**Test cases needed:**

1. **Test Case 1:**
   - Input: 
   - Expected result: 
   - Validation: 

2. **Test Case 2:**
   - Input: 
   - Expected result: 
   - Validation: 

**Certification requirements:**
- [ ] Official certification needed
- [ ] Self-attestation acceptable
- [ ] Third-party testing required
- [ ] No formal certification

## Use Cases

**Who needs this compliance rule?**
- [ ] Hospitals and health systems
- [ ] Ambulatory clinics
- [ ] Laboratories
- [ ] Pharmacies
- [ ] Health IT vendors
- [ ] Research institutions
- [ ] Payers/insurance
- [ ] Public health agencies
- [ ] Medical device manufacturers
- [ ] Other: 

**Affected regions/organizations:**


## Priority & Timeline

**Urgency:**
- [ ] Critical - Legal deadline approaching
- [ ] High - Required for market access
- [ ] Medium - Competitive advantage
- [ ] Low - Future-proofing

**Regulatory deadline:**


**Consequences of non-compliance:**
- [ ] Legal penalties/fines
- [ ] Loss of certification
- [ ] Market access blocked
- [ ] Liability risk
- [ ] Reputational damage
- [ ] Other: 

## Supporting Materials

**Reference implementations:**
- System/vendor: 
- How they implement it: 
- Documentation: 

**Standards documentation:**
- [ ] Attached PDF
- [ ] Linked URL (above)
- [ ] Available upon request

**Sample data:**
- [ ] Included below
- [ ] Attached file
- [ ] Can be provided later

## Industry Adoption

**Adoption status:**
- [ ] Widely adopted across industry
- [ ] Emerging requirement
- [ ] Early adoption phase
- [ ] Proposed/not yet final

**Vendor support:**
- List vendors already supporting: 

## Commercial vs. Open-Source

**Should this be in the open-source core or a commercial plugin?**
- [ ] Open-source core (fundamental requirement)
- [ ] Commercial plugin acceptable (specialized compliance)
- [ ] No preference

**Justification:**


## Contribution Offer

**Can you help implement this?**
- [ ] Yes, we can provide code/PR
- [ ] Yes, we can provide requirements/specs
- [ ] Yes, we can help test/validate
- [ ] Yes, we can provide compliance expertise
- [ ] Yes, we can sponsor development ($)
- [ ] No, we need the core team to implement

**Resources available:**


## Related Requirements

**Related standards or regulations:**
- 

**Dependencies:**
- 

## Additional Context

**Any other relevant information:**


**Attachments:**
- Regulation PDF: 
- Implementation guide: 
- Example data: 

## Related Issues

**Link to related issues or discussions:**
- #

---

## For Maintainers

**Compliance Review Checklist:**
- [ ] Regulatory requirement verified
- [ ] Geographic scope confirmed
- [ ] Timeline/deadline noted
- [ ] Technical feasibility assessed
- [ ] Open-source vs. commercial decision made
- [ ] Legal review required: [ ] Yes [ ] No
- [ ] Compliance expert consulted
- [ ] Added to compliance roadmap
- [ ] RFC required: [ ] Yes [ ] No

