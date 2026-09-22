# Changelog

All notable changes to **Leviathan Launcher** will be documented in this file.

This project is currently in **Private Development** and has not yet had a public release.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), with versioning intended to follow [Semantic Versioning](https://semver.org/) once public releases begin.

---

## [Unreleased]

### Added

- Continued private development of Leviathan Launcher.
- Microsoft Entra application registration for Leviathan Launcher.
- Microsoft account authentication integration.
- Xbox Live authentication integration.
- Xbox Security Token Service (XSTS) authentication integration.
- Minecraft Services authentication integration.
- Minecraft ownership and profile verification flow.
- Public desktop-client authentication configuration.
- Minecraft AppID review approved. Production authentication validation remains a separate release requirement.
- Project documentation for privacy, security, licensing, and third-party notices.
- Public GitHub repository for project documentation, transparency, and review.

### Changed

- Improved project documentation and development-status information.
- Updated repository licensing to use the Leviathan Launcher proprietary software license.
- Clarified that public repository visibility does not mean public launcher distribution.
- Clarified that development builds are currently accessible only to the developer.

### Security

- Microsoft passwords are not handled directly by Leviathan Launcher.
- No confidential Microsoft client secret is embedded in the desktop application.
- Authentication tokens are treated as sensitive launcher data.
- Local token, session, environment, cache, and credential files are excluded from source control where applicable.

### Pending

- Full production testing against Minecraft Services after AppID approval.
- Public testing.
- Public release.

---

## [0.1.0] - 2026-09-06

### Added

- Initial Leviathan Launcher desktop application foundation.
- Java 21 project setup.
- Gradle build configuration.
- Launcher user interface foundation.
- Minecraft version and installation management foundation.
- Launcher profile and account-management foundation.
- Microsoft authentication foundation.
- Minecraft authentication foundation.
- Download and update infrastructure.
- Launcher settings and configuration systems.
- Java runtime configuration.
- Diagnostics and repair systems.
- Mod/content integration foundation.
- Server-list functionality.
- Skin and profile functionality.
- Discord Rich Presence integration foundation.
- Verification and development test suite.

### Notes

- Version `0.1.0` is a private development version.
- No public binaries or public releases are currently available.
- At the time of this private development version, Minecraft AppID approval was outstanding. The review has since been approved; see Unreleased.

---

## Release Policy

Until Leviathan Launcher becomes publicly available:

- Development versions may change without notice.
- Version numbers may be revised.
- Features may be incomplete, experimental, disabled, or removed.
- No compatibility guarantees are made between private development builds.
- Changelog entries may be reorganized before the first stable public release.

When public releases begin, each release should include:

- Version number
- Release date
- Added features
- Changes
- Bug fixes
- Security fixes
- Known issues
- Breaking changes, where applicable

---

**Leviathan Launcher**  
Private Development  
Copyright © 2026 Leviathan project owner. All Rights Reserved.
