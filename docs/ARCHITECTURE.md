# SNAP Assist – Architecture Overview

## Purpose
Portable, offline-first Flutter application that helps SNAP recipients:
- Log work hours (cash + in-kind)
- Generate work verification reports
- Store and OCR identity / income / asset documents (encrypted)
- Estimate eligibility and surface related benefits (TANF, LIHEAP, GR, SSI/SSDI, etc.)
- Access state SNAP portals and third-party SNAP recipient discounts via built-in browser

## High-Level Architecture

```
Presentation Layer (Flutter + Riverpod)
Application Layer (Services)
Domain Layer (Models + Business Rules)
Data Layer (Drift/SQLite + AES-256 encryption)
```

## Security Model
- App launch (unauthenticated): Public mode only
- Self-replication: Clean copy without encrypted user database
- Onboarding: email + password → derive encryption key → initialize encrypted DB
- Authentication: email + password unlocks key
- Password Reset: 24-hour single-active token emailed to user
- Documents: Original images stored encrypted; OCR text after user confirmation
- Single-user design

## Platform Targets
Windows, macOS, Linux, iOS, Android. Offline-first.
