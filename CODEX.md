# CODEX TASK PLAN

## Repository

Target: Zimbra Collaboration Suite 8.8.15

Primary language:
- Java
- JSP
- JavaScript
- XML
- Shell

Goal:
Identify real vulnerabilities with source-code evidence.

---

# Rules

Never stop after finding one issue.

Continue until every reachable subsystem has been reviewed.

Never guess.

Support every conclusion with code.

Always produce Markdown.

Always include file paths.

Always explain the complete execution flow.

---

# Priority Order

1. Authentication
2. Authorization
3. SOAP
4. REST
5. Servlet Filters
6. Session Management
7. Upload
8. Download
9. XML
10. LDAP
11. Filesystem
12. Command Execution
13. Proxy
14. Admin Console
15. Mailbox

---

# Phase 1

Understand architecture.

Tasks

- Identify modules
- Build dependency graph
- Locate entry points
- Locate servlet mappings
- Locate SOAP services
- Locate REST services

Deliverable

architecture.md

---

# Phase 2

Attack Surface Enumeration

Tasks

List

Servlets

Filters

SOAP handlers

REST endpoints

Admin endpoints

Upload handlers

Download handlers

Export handlers

Import handlers

Mailbox handlers

Generate

attack_surface.md

---

# Phase 3

Authentication Review

Locate

Login flow

Session creation

Token generation

Cookie validation

CSRF protection

Admin authentication

Deliverable

authentication.md

---

# Phase 4

Authorization Review

Trace

Role checks

ACL checks

Admin-only paths

Mailbox ownership checks

Deliverable

authorization.md

---

# Phase 5

Input Validation

Trace every user-controlled input.

Request

↓

Parser

↓

Validation

↓

Business Logic

↓

Dangerous Sink

Produce

input_validation.md

---

# Phase 6

Dangerous Sink Review

Review every sink.

Filesystem

LDAP

SQL

Shell

XML

Serialization

Reflection

Network

Generate

dangerous_sinks.md

---

# Phase 7

XML Review

Locate

DocumentBuilderFactory

SAXParserFactory

TransformerFactory

XPathFactory

Check

XXE

XSLT Injection

External Entity resolution

Generate

xml_review.md

---

# Phase 8

Filesystem Review

Locate

File

Path

Files

Zip

Jar

Archive extraction

Check

Traversal

Overwrite

Zip Slip

Symlink attacks

Generate

filesystem.md

---

# Phase 9

LDAP Review

Locate every LDAP query.

Check

Injection

Privilege escalation

Anonymous bind

Unsafe filters

Generate

ldap.md

---

# Phase 10

Command Execution

Search

Runtime.exec

ProcessBuilder

Groovy

Beanshell

ScriptEngine

Generate

command_execution.md

---

# Phase 11

Serialization

Locate

ObjectInputStream

XMLDecoder

Serializable classes

Generate

deserialization.md

---

# Phase 12

REST Review

Review every endpoint.

Authentication

Authorization

Validation

Output Encoding

Generate

rest_review.md

---

# Phase 13

SOAP Review

Review every SOAP service.

Check

Authentication

Authorization

XML parsing

Privilege escalation

Generate

soap_review.md

---

# Phase 14

Admin Console

Review

Admin JSP

Servlets

Actions

Proxy

Generate

admin_console.md

---

# Phase 15

Mailbox

Review

MailboxManager

MailboxBlob

Message

Attachment

Calendar

Contacts

Generate

mailbox.md

---

# Phase 16

Search Patterns

Search for

TODO

FIXME

XXX

HACK

catch(Exception)

printStackTrace()

ignore

debug

Generate

code_smells.md

---

# Phase 17

Historical Vulnerabilities

Compare implementation against

- XXE
- SSRF
- Auth bypass
- Proxy abuse
- Upload vulnerabilities
- Deserialization
- RCE

Document similar patterns.

---

# Phase 18

Call Graph

Generate

callgraph.md

Include

Entry point

↓

Validation

↓

Business Logic

↓

Sink

---

# Phase 19

Exploitability

For every finding answer

Can attacker reach it?

Authentication required?

Admin required?

Remote?

Default installation?

Realistic impact?

---

# Phase 20

Final Report

Generate

FINAL_REPORT.md

For every finding include

Severity

CVSS estimate

CWE

Affected files

Affected methods

Reachability

Root Cause

Proof

Remediation

Confidence
