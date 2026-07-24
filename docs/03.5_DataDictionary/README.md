---
title: Data Dictionary
version: 1.0.0
status: Approved
owner: ExamCore Team
author: Lead Software Architect
language: English
last_updated: 2026-07-24
---

# Data Dictionary

> The official reference for all database entities used by the ExamCore Platform.

---

# Purpose

The Data Dictionary provides a complete description of every database entity, including:

- Tables
- Relationships
- Constraints
- Business Rules
- Indexes
- Enumerations
- Audit Fields
- Future Extensions

This document acts as the **Single Source of Truth** for database design.

---

# Objectives

The Data Dictionary exists to:

- Standardize database structure.
- Reduce ambiguity.
- Improve communication between teams.
- Support API development.
- Support frontend development.
- Simplify maintenance.
- Ensure consistent naming conventions.

---

# Design Principles

The database follows these principles:

- UUID Primary Keys
- Soft Delete
- Audit Fields
- Tenant Isolation
- Referential Integrity
- Explicit Constraints
- Performance-Oriented Indexes
- Future Scalability

---

# Domain Structure

The database is divided into independent business domains.

```
Identity
│
├── Organizations
├── Workspaces
├── Users
├── Roles
├── Permissions
└── Sessions

Academic
│
├── Subjects
├── Classes
├── Groups
└── Participants

Question Bank
│
├── Questions
├── Categories
├── Tags
├── Attachments
└── Question Versions

Exam
│
├── Exams
├── Exam Sessions
├── Participants
├── Randomization
└── Navigation

Assessment
│
├── Answers
├── Results
├── Essay Reviews
└── Score Details

Certificate
│
├── Templates
├── Certificates
└── Verification

Analytics
│
├── Statistics
├── Reports
└── Dashboard Cache

System
│
├── Audit Logs
├── Settings
├── Notifications
└── Background Jobs
```

---

# Documentation Standard

Every table documentation must include:

- Purpose
- Business Rules
- Columns
- Constraints
- Foreign Keys
- Indexes
- Relationships
- Validation Rules
- Audit Information
- Future Extensions

---

# Naming Convention

## Tables

Plural nouns.

Examples

```
users
organizations
questions
exam_sessions
```

---

## Primary Keys

Always

```
id UUID
```

---

## Foreign Keys

```
organization_id

workspace_id

question_id

exam_id
```

Always use

```
<table_name>_id
```

---

## Timestamps

Every transactional table should include:

```
created_at

updated_at
```

Optional:

```
deleted_at
```

for soft delete.

---

# Audit Columns

Recommended standard columns:

| Column | Required |
|---------|----------|
| created_at | Yes |
| updated_at | Yes |
| created_by | Yes |
| updated_by | Yes |
| deleted_at | Optional |
| deleted_by | Optional |

---

# Entity Relationship Philosophy

Relationships should always be explicit.

Avoid hidden relationships.

Use Foreign Keys whenever applicable.

Do not duplicate information across tables.

---

# Domain Documents

| Document | Description |
|-----------|-------------|
| 01_Identity.md | Authentication and user management |
| 02_Academic.md | Academic structures |
| 03_QuestionBank.md | Question management |
| 04_Exam.md | Examination engine |
| 05_Assessment.md | Answers and scoring |
| 06_Certificate.md | Certificates |
| 07_Analytics.md | Reports and statistics |
| 08_System.md | Internal platform services |

---

# Future Domains

Reserved for future expansion:

- Payment
- LMS
- AI Services
- Public API
- Plugin Marketplace
- Messaging
- File Storage
- Survey Engine

---

# Documentation Lifecycle

```
Draft

↓

Review

↓

Approved

↓

Locked

↓

Versioned

↓

Deprecated
```

---

# Related Documents

- PROJECT_MANIFEST.md
- 03_Database.md
- 04_ERD.md
- 05_API.md

---

# Version History

| Version | Date | Description |
|----------|------------|----------------------|
| 1.0.0 | 2026-07-24 | Initial Release |

---

# Approval

Status

APPROVED

Architecture

LOCKED

Version

1.0.0
