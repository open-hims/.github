# Contributing to OpenHIMS

Thank you for your interest in contributing to **OpenHIMS — powered by RustCare Engine**! 🎉

We're building the most robust, secure, and interoperable healthcare information management system using Rust. Your contributions help improve healthcare technology for everyone.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Workflow](#development-workflow)
- [RFC Process](#rfc-process)
- [Repository Structure](#repository-structure)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Coding Standards](#coding-standards)
- [Testing Requirements](#testing-requirements)
- [Documentation](#documentation)
- [Community](#community)

---

## Code of Conduct

This project adheres to a [Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to conduct@openhims.org.

---

## How Can I Contribute?

### 🐛 Reporting Bugs

Use the [Bug Report template](.github/ISSUE_TEMPLATE/bug_report.md) and include:
- Clear description of the issue
- Steps to reproduce
- Expected vs. actual behavior
- Environment details (OS, Rust version, OpenHIMS version)
- Relevant logs or error messages

### 💡 Suggesting Features

Use the [Feature Request template](.github/ISSUE_TEMPLATE/feature_request.md) and consider:
- Is this a common use case?
- Does it align with healthcare interoperability goals?
- For major features, consider submitting an RFC first (see below)

### 🔌 Plugin Requests

Use the [Plugin Request template](.github/ISSUE_TEMPLATE/plugin_request.md) for:
- New integration ideas
- Data transformation modules
- Compliance tooling suggestions

### 📋 Compliance Rule Requests

Use the [Compliance Rule Request template](.github/ISSUE_TEMPLATE/compliance_request.md) for:
- New regulatory requirements
- Updated standards (HL7, FHIR versions)
- Region-specific compliance needs

### 💻 Contributing Code

1. Check existing issues or create one
2. For major changes, submit an RFC (see below)
3. Fork the repository
4. Create a feature branch
5. Make your changes following our standards
6. Submit a pull request

---

## Development Workflow

### Initial Setup

```bash
# Clone the repository
git clone https://github.com/openhims/rustcare-engine.git
cd rustcare-engine

# Install Rust (if not already installed)
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Install development dependencies
rustup component add rustfmt clippy
cargo install cargo-audit cargo-tarpaulin

# Build the project
cargo build

# Run tests
cargo test

# Run linter
cargo clippy -- -D warnings

# Format code
cargo fmt
```

### Development Commands

```bash
# Run in development mode
cargo run

# Run with specific features
cargo run --features "fhir-r4,hl7-v2"

# Run tests with coverage
cargo tarpaulin --out Html

# Check for security vulnerabilities
cargo audit

# Build documentation
cargo doc --no-deps --open
```

---

## RFC Process

**RFC (Request for Comments)** is required for **substantial changes**:

### What Requires an RFC?

- New core features or major enhancements
- Breaking API changes
- New plugin architecture components
- Significant performance optimizations
- Changes to data models or storage formats
- New compliance modules

### What Doesn't Require an RFC?

- Bug fixes
- Documentation improvements
- Minor refactoring
- Test additions
- Performance optimizations that don't change APIs
- Small feature additions to existing modules

### RFC Workflow

1. **Create an Issue**
   - Use the "RFC" label
   - Title: `[RFC] Your Feature Name`
   - Provide initial overview

2. **Write the RFC Document**
   ```bash
   cp rfcs/0000-template.md rfcs/0000-your-feature.md
   ```
   
   Include:
   - **Summary**: One-paragraph explanation
   - **Motivation**: Why is this needed?
   - **Detailed Design**: Technical specification
   - **Drawbacks**: Potential downsides
   - **Alternatives**: What other approaches were considered?
   - **Unresolved Questions**: Open issues for discussion

3. **Submit RFC Pull Request**
   - PR to add your RFC to `/rfcs/` directory
   - Label with `rfc`
   - Announce in community channels

4. **Discussion Period**
   - Minimum 1 week for minor features
   - 2-4 weeks for major changes
   - Core team and community provide feedback
   - Iterate on design

5. **RFC Decision**
   - ✅ **Accepted**: RFC is merged, implementation can begin
   - ❌ **Rejected**: RFC is closed with reasoning
   - ⏸️ **Postponed**: Good idea, wrong timing

6. **Implementation**
   - Reference RFC number in PRs
   - Break large features into smaller PRs
   - Keep RFC updated if design evolves

### RFC Template Structure

```markdown
- RFC PR: #(number)
- Implementation Issue: #(number)

# Summary
[One paragraph explanation]

# Motivation
[Why are we doing this?]

# Guide-level Explanation
[How would users interact with this?]

# Reference-level Explanation
[Technical details]

# Drawbacks
[Why should we NOT do this?]

# Rationale and Alternatives
[Why is this the best approach?]

# Prior Art
[Similar implementations in other systems]

# Unresolved Questions
[What needs to be resolved during implementation?]

# Future Possibilities
[What could this enable later?]
```

---

## Repository Structure

```
rustcare-engine/
├── .github/               # GitHub configuration (this directory)
├── rfcs/                  # RFC documents
├── crates/
│   ├── rustcare-core/     # Core engine
│   ├── rustcare-fhir/     # FHIR implementation
│   ├── rustcare-hl7/      # HL7 v2 support
│   ├── rustcare-security/ # Security & encryption
│   └── rustcare-plugins/  # Plugin system
├── plugins/
│   ├── oss/               # Open-source plugins
│   └── examples/          # Example plugins
├── docs/                  # Documentation
├── tests/                 # Integration tests
└── benches/               # Benchmarks
```

### Branch Strategy

- `main` — Stable, production-ready code
- `develop` — Integration branch for next release
- `feature/*` — New features
- `fix/*` — Bug fixes
- `docs/*` — Documentation updates
- `rfc/*` — RFC implementation

---

## Pull Request Guidelines

### Before Submitting

- ✅ Code follows Rust style guidelines (`cargo fmt`)
- ✅ All tests pass (`cargo test`)
- ✅ No clippy warnings (`cargo clippy -- -D warnings`)
- ✅ Documentation updated (if applicable)
- ✅ Tests added for new functionality
- ✅ Changelog entry added (for user-facing changes)
- ✅ Security considerations addressed

### PR Template Requirements

All PRs must use the [Pull Request template](.github/PULL_REQUEST_TEMPLATE.md) and include:

1. **Linked Issue/RFC**: Every PR must reference an issue or RFC
2. **Type of Change**: Bug fix, feature, docs, etc.
3. **Description**: What changed and why
4. **Testing**: How was this tested?
5. **Breaking Changes**: If any, with migration guide
6. **Security Impact**: HIPAA, PHI handling considerations

### PR Review Process

1. **Automated Checks**: CI must pass
   - Build on all supported platforms
   - All tests pass
   - Clippy checks
   - Security audit
   - Code coverage maintained

2. **Code Review**: Requires 2 approvals
   - At least 1 from core team
   - Healthcare domain expertise for compliance changes

3. **Documentation Review**: For user-facing changes

4. **Merge**: Squash and merge with descriptive commit message

---

## Coding Standards

### Rust Style Guide

Follow the [Rust API Guidelines](https://rust-lang.github.io/api-guidelines/):

```rust
// ✅ Good
pub struct Patient {
    id: PatientId,
    given_name: String,
    family_name: String,
}

impl Patient {
    /// Creates a new patient record.
    ///
    /// # Errors
    /// Returns error if name validation fails.
    pub fn new(given_name: String, family_name: String) -> Result<Self> {
        // Implementation
    }
}

// ❌ Avoid
pub struct patient {
    ID: String,
    name: String,
}
```

### Healthcare-Specific Guidelines

#### PHI Handling

```rust
// ✅ Always mark PHI types clearly
#[derive(Debug, Clone)]
#[phi_data] // Custom attribute for tracking
pub struct PatientRecord {
    #[phi] pub ssn: Option<SocialSecurityNumber>,
    #[phi] pub medical_record: MedicalHistory,
    pub created_at: DateTime<Utc>,
}

// ❌ Never log PHI
log::info!("Processing patient {}", patient.ssn); // WRONG!
log::info!("Processing patient {}", patient.id);  // Correct
```

#### Error Handling

```rust
// ✅ Use Result types with context
pub fn parse_hl7_message(data: &[u8]) -> Result<Hl7Message, Hl7Error> {
    // Implementation with detailed error context
}

// ❌ Avoid unwrap() in production code
let message = parse_hl7_message(data).unwrap(); // WRONG!
let message = parse_hl7_message(data)?;         // Correct
```

#### Security

```rust
// ✅ Use secure defaults
pub struct EncryptionConfig {
    algorithm: EncryptionAlgorithm::Aes256Gcm,  // Strong default
    key_derivation: KeyDerivation::Argon2id,    // Secure KDF
}

// ✅ Zeroize sensitive data
use zeroize::Zeroize;

pub struct ApiKey(Vec<u8>);

impl Drop for ApiKey {
    fn drop(&mut self) {
        self.0.zeroize();
    }
}
```

---

## Testing Requirements

### Test Coverage

- Minimum **80% code coverage** for core modules
- **100% coverage** required for:
  - Security components
  - Cryptography modules
  - PHI handling functions
  - Compliance validators

### Test Categories

```rust
// Unit tests
#[cfg(test)]
mod tests {
    #[test]
    fn test_patient_creation() {
        // Test logic
    }
}

// Integration tests in /tests
#[test]
fn test_hl7_to_fhir_conversion() {
    // End-to-end test
}

// Property-based tests for parsers
use proptest::prelude::*;

proptest! {
    #[test]
    fn test_fhir_parser_doesnt_crash(s in "\\PC*") {
        let _ = parse_fhir(&s);
    }
}
```

### Healthcare Test Data

- **Never use real patient data** in tests
- Use synthetic data generators
- Follow HIPAA de-identification guidelines

---

## Documentation

### Code Documentation

```rust
/// Parses an HL7 v2.x message into structured format.
///
/// # Arguments
/// * `data` - Raw HL7 message bytes
/// * `version` - HL7 version (e.g., "2.5.1")
///
/// # Returns
/// Parsed message structure or error
///
/// # Errors
/// Returns `Hl7Error::InvalidFormat` if message format is invalid.
///
/// # Example
/// ```
/// let message = parse_hl7(hl7_bytes, "2.5.1")?;
/// assert_eq!(message.message_type, "ADT^A01");
/// ```
pub fn parse_hl7(data: &[u8], version: &str) -> Result<Hl7Message> {
    // Implementation
}
```

### User Documentation

Update `/docs` for:
- New features
- API changes
- Configuration options
- Migration guides

---

## Community

### Communication Channels

- **GitHub Discussions**: Design discussions, Q&A
- **Discord**: Real-time chat ([invite link](https://discord.gg/openhims))
- **Forum**: [forum.openhims.org](https://forum.openhims.org)
- **Mailing List**: dev@openhims.org

### Weekly Sync

- **When**: Thursdays at 2 PM UTC
- **Where**: Video call (link in Discord)
- **Topics**: RFC reviews, roadmap, blockers

### Getting Help

- Check [documentation](https://docs.openhims.org)
- Search existing GitHub issues
- Ask in Discord `#dev-help` channel
- Email: dev-support@openhims.org

---

## Recognition

Contributors are recognized:
- In release notes
- On our [Contributors page](https://openhims.org/contributors)
- Major contributors become project members with commit access

---

## License

By contributing, you agree that your contributions will be licensed under the same license as the project:
- Core platform: Apache 2.0 + Healthcare Liability Clause
- See [LICENSE](./LICENSE) and [LICENSE-PLUGINS.md](./LICENSE-PLUGINS.md)

---

**Questions?** Open a discussion or reach out to maintainers@openhims.org

**Thank you for contributing to better healthcare technology!** 🏥❤️

