# Leviathan Launcher Release Policy

**Project status:** Private Development

This document describes the intended release process for Leviathan Launcher.

---

## Current State

Leviathan Launcher currently has no public release.

Private development builds may change without notice and are not intended for general distribution.

---

## Release Channels

Potential future release channels may include:

### Stable
Recommended for general users after public release.

### Beta
For broader testing of upcoming features.

### Development / Nightly
Potentially unstable builds intended for development or advanced testing.

No release channel is currently guaranteed.

---

## Versioning

Public releases are intended to use semantic-style version numbers:

`MAJOR.MINOR.PATCH`

Examples:

- `1.0.0`
- `1.1.0`
- `1.1.1`

Pre-release versions may use identifiers such as:

- `1.0.0-beta.1`
- `1.0.0-rc.1`

---

## Release Requirements

Before a stable public release, the project should review:

- Microsoft authentication
- Minecraft AppID approval
- Ownership verification
- Token/session security
- Privacy documentation
- Terms of Use
- Third-party licenses
- Dependency vulnerabilities
- Update security
- Download integrity
- Installer security
- Code-signing strategy
- Crash/log privacy
- Known issues
- Rollback/recovery behavior

---

## Release Artifacts

Future public releases may include:

- Installer
- Portable archive
- Checksums
- Digital signatures
- Release notes
- Changelog
- Known issues

Official release artifacts should only be published through trusted project-controlled channels.

---

## Release Verification

Before public release, Leviathan should consider:

- HTTPS-only downloads
- SHA-256 checksums
- Code signing
- Signed update metadata
- Reproducible or auditable build practices where practical

---

## Security Releases

Critical vulnerabilities may require:

- Emergency releases
- Forced or strongly recommended updates
- Disabled outdated versions
- Token invalidation
- Credential rotation
- Backend changes

Security-sensitive release information should be coordinated responsibly.

---

## Deprecation

Old launcher versions may be deprecated when:

- Third-party APIs change
- Security issues require it
- Authentication compatibility breaks
- Update infrastructure changes
- Maintaining compatibility becomes unreasonable

---

## Release Notes

Each public release should describe:

- New features
- Changes
- Bug fixes
- Security fixes
- Breaking changes
- Known issues
- Upgrade notes

---

## Official Repository

https://github.com/Lapinite/Leviathan-Launcher

---

**Leviathan Launcher**  
Release Policy
