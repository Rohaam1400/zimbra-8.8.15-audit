# Zimbra 8.8.15 Security Audit

## Purpose

This repository exists exclusively for architecture review and security research.

Goals:

- Understand the architecture
- Map every external attack surface
- Trace attacker-controlled input
- Discover real vulnerabilities
- Produce reproducible findings

This repository is **not** intended for feature development.

---

# Repository Layout

src/

Contains source repositories.

The most important modules are:

src/zm-mailbox

Core server implementation.

Highest priority.

Contains:

- SOAP handlers
- Mailbox logic
- Authentication
- Authorization
- Account management
- File handling
- XML processing

---

src/zm-admin-console

Administrative interface.

High priority.

Focus:

- Admin actions
- Admin authentication
- Proxy requests
- Administrative servlets

---

src/zm-web-client

User web interface.

Focus:

- XSS
- CSRF
- Client-side trust boundaries
- Upload
- Download

---

src/zm-ajax

AJAX layer.

Focus:

- Request parsing
- JSON
- SOAP interaction

---

src/zm-core-utils

Utility library.

Focus:

- Shared validation
- Encoding
- Filesystem helpers

---

src/zm-zcs

Packaging and deployment.

Low priority unless reviewing installation or configuration behavior.

---

# Audit Order

Always review in this sequence.

1.

Architecture

↓

2.

Entry points

↓

3.

Authentication

↓

4.

Authorization

↓

5.

SOAP

↓

6.

REST

↓

7.

Servlets

↓

8.

Filters

↓

9.

Upload

↓

10.

Download

↓

11.

Filesystem

↓

12.

XML

↓

13.

LDAP

↓

14.

Shell execution

↓

15.

Serialization

↓

16.

Session handling

↓

17.

Admin console

↓

18.

Final report

---

# Deliverables

Store reports here:

docs/findings/

Suggested filenames:

architecture.md

attack_surface.md

authentication.md

authorization.md

soap.md

rest.md

filesystem.md

ldap.md

xml.md

uploads.md

downloads.md

command_execution.md

deserialization.md

admin_console.md

mailbox.md

findings.md

FINAL_REPORT.md

---

# Finding Format

Each issue should contain:

Title

Severity

CWE

Affected files

Affected methods

Reachability

Root cause

Exploit prerequisites

Impact

Evidence

Suggested remediation

Confidence

---

# Evidence Standards

Never report speculative vulnerabilities.

Support every finding with:

- Source code references
- Request flow
- Call chain
- Security impact

Where practical, explain why the issue is exploitable or why existing checks prevent exploitation.

---

# Review Strategy

Prefer end-to-end analysis.

Follow attacker-controlled data from the request to sensitive operations.

Examples of sensitive operations:

- Filesystem access
- XML parsing
- LDAP queries
- Database access
- Shell execution
- Reflection
- Template rendering
- Serialization
- Network requests

Do not stop after identifying one issue.

Continue reviewing the remaining attack surface.

---

# Out of Scope

Unless specifically requested:

- Performance optimizations
- Refactoring suggestions
- Coding style
- Formatting changes
- Non-security improvements

Primary objective:

Produce a technically accurate, evidence-based security assessment.
