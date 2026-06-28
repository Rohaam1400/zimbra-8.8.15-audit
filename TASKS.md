# Audit Tasks

## Phase 1

- Identify all Servlets
- Identify all Filters
- Identify all SOAP handlers
- Identify all REST endpoints

---

## Phase 2

Map every request flow.

Request

↓

Authentication

↓

Authorization

↓

Business Logic

↓

Response

---

## Phase 3

Trace every user-controlled value.

Request Parameter

↓

Parser

↓

Validation

↓

Storage

↓

Sink

---

## Phase 4

Review every sink.

Filesystem

SQL

LDAP

XML

Shell

Serialization

Network

Templates

Reflection

---

## Phase 5

Search for

TODO

FIXME

HACK

XXX

disabled validation

ignore exception

catch(Exception)

printStackTrace()

---

## Phase 6

Generate attack surface documentation.

Produce one Markdown file per subsystem.

---

## Phase 7

Generate a prioritized vulnerability report.
