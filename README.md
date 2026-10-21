# SNAP Assist

Portable, offline-first Flutter application for SNAP recipients to:

- Log work hours (cash and in-kind)
- Generate work verification reports
- Securely store and OCR identity / income / asset documents
- Receive guidance on work requirements and related benefits (TANF, LIHEAP, GR, SSI/SSDI, etc.)
- Access state SNAP portals and third-party SNAP recipient discounts via built-in browser

## Current Status (v0.1.1 foundation)

- Project structure and architecture defined
- Public (unauthenticated) home screen
- Multi-step Onboarding Wizard (UI complete)
- EncryptionService (Argon2id key derivation + AES-256-GCM)
- PasswordResetService (24h single-active token)
- Database schema designed
- Security model documented
- Oklahoma state configuration pack included

**Next implementation targets:**
1. Wire EncryptionService into onboarding completion
2. Drift database + encrypted open
3. Authentication / login screen
4. Work logging + verification report generation

## Supported Platforms (target)

- Windows, macOS, Linux
- iOS, Android

## Getting Started

```bash
cd snap_assist
flutter pub get
flutter run
```

## Security Notes

- Single-user, local-only encrypted database
- Password-derived encryption
- Password reset uses a short-lived, single-active token delivered by email
- Document images stored encrypted on disk
- No personal data leaves the device unless the user explicitly uses online features

## License

Private / proprietary – adjust as needed.
