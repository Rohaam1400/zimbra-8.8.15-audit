# Zimbra 8.8.15 Security Audit Instructions

## Objective

This repository is used exclusively for security review of Zimbra 8.8.15.

Never summarize the project before understanding the code.

Always produce evidence.

Every security finding must include:

- Severity
- CWE
- File
- Function
- Call chain
- User-controlled source
- Dangerous sink
- Exploitability
- Suggested remediation

---

## Primary Goals

Search for:

- Remote Code Execution
- Authentication Bypass
- Authorization Bypass
- XXE
- SSRF
- Path Traversal
- Arbitrary File Read
- Arbitrary File Write
- Zip Slip
- LDAP Injection
- SQL Injection
- Command Injection
- Deserialization
- SSTI
- XSS
- CSRF
- Open Redirect
- Header Injection
- Host Header Injection
- Request Smuggling
- XML parser abuse
- SOAP parser abuse
- REST endpoint abuse
- Privilege Escalation

---

## Trust Boundaries

Always identify:

External Request

↓

Servlet

↓

SOAP Endpoint

↓

Business Logic

↓

Filesystem

↓

Database

↓

LDAP

↓

OS Command

↓

Response

---

## Dangerous APIs

Search for:

Runtime.exec

ProcessBuilder

ScriptEngine

Class.forName

ObjectInputStream

XMLDecoder

DocumentBuilderFactory

SAXParserFactory

XPathFactory

TransformerFactory

InitialContext

NamingContext

DirContext

Files.write

Files.copy

Files.move

FileOutputStream

RandomAccessFile

ZipInputStream

JarInputStream

Commons FileUpload

Multipart

ServletInputStream

---

## Output format

Always generate Markdown.

Never omit file paths.

Always include line numbers whenever possible.

Always explain why a finding is exploitable.

Never report theoretical issues without evidence.
