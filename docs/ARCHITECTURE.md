# Leviathan Launcher Architecture

**Status:** Private Development  
**Project:** Leviathan Launcher

This document provides a high-level overview of the intended Leviathan Launcher architecture.

It is intentionally focused on project structure and responsibilities rather than confidential infrastructure details.

---

## Overview

Leviathan Launcher is a desktop application for legitimate Minecraft: Java Edition users.

The launcher is designed around several major areas:

```text
+------------------------------------------------------+
|                  Leviathan Launcher                  |
+------------------------------------------------------+
| User Interface                                      |
+------------------------------------------------------+
| Accounts | Profiles | Settings | Version Management |
+------------------------------------------------------+
| Authentication | Downloads | Updates | Game Launch  |
+------------------------------------------------------+
| Minecraft Integration | Java Runtime | Diagnostics   |
+------------------------------------------------------+
| Local Storage | Cache | Configuration | Logs         |
+------------------------------------------------------+
| External Services                                   |
| Microsoft | Xbox | XSTS | Minecraft | Modrinth      |
+------------------------------------------------------+
```

---

## 1. User Interface

The UI layer is responsible for presenting launcher functionality to the user.

Planned or existing areas may include:

- Home
- Play
- Version selection
- Account management
- Microsoft login
- Launcher profiles
- Settings
- Java configuration
- Performance configuration
- Cosmetics
- News
- Downloads
- Updates
- Diagnostics
- Server functionality
- Skin/profile functionality

The UI should avoid directly containing sensitive authentication logic where practical.

---

## 2. Account Management

The account subsystem is responsible for:

- Starting Microsoft authentication
- Tracking the active launcher account
- Retrieving Minecraft profile information
- Managing local session state
- Signing users out
- Providing account information to the game-launch subsystem

Account data must be treated as sensitive where it contains tokens or session information.

---

## 3. Authentication

Authentication is separated into several stages:

1. Microsoft authentication
2. Xbox Live authentication
3. XSTS authentication
4. Minecraft Services authentication
5. Minecraft ownership verification
6. Minecraft profile retrieval

See [AUTHENTICATION.md](AUTHENTICATION.md) for the detailed flow.

---

## 4. Launcher Profiles

Launcher profiles represent user-selected game configurations.

A profile may eventually contain information such as:

- Minecraft version
- Mod loader
- Java runtime
- Memory allocation
- JVM arguments
- Game arguments
- Resolution
- Installation directory
- Mods or content configuration
- Server configuration
- Profile-specific preferences

Profiles should not contain plaintext passwords or other unrelated credentials.

---

## 5. Minecraft Version Management

The version-management subsystem is responsible for identifying, installing, updating, and launching supported Minecraft versions.

Responsibilities may include:

- Version metadata retrieval
- Version manifest parsing
- Library resolution
- Asset resolution
- Native library handling
- Version inheritance
- Client JAR management
- Integrity verification
- Local installation state

---

## 6. Download System

The download subsystem may be used for:

- Minecraft versions
- Libraries
- Assets
- Java runtimes
- Mods
- Modpacks
- Resource packs
- Shaders
- Launcher updates

The downloader should support appropriate validation and error handling.

Before public release, critical downloads should use trusted HTTPS sources and integrity verification where available.

---

## 7. Game Launch System

The launch subsystem is responsible for building and starting the Minecraft Java process.

Responsibilities may include:

- Selecting Java
- Building classpaths
- Loading version metadata
- Applying JVM arguments
- Applying game arguments
- Supplying authenticated Minecraft profile information
- Configuring memory
- Setting native-library paths
- Selecting the game directory
- Starting the Java process
- Tracking process state
- Capturing useful diagnostics

Sensitive tokens should not be unnecessarily exposed in logs.

---

## 8. Java Runtime Management

Leviathan Launcher targets Java 21 for its own development environment.

Minecraft versions may require different Java versions.

The runtime subsystem may eventually:

- Detect installed Java versions
- Validate Java compatibility
- Select an appropriate runtime
- Download supported runtimes where permitted
- Configure JVM paths
- Report compatibility problems

---

## 9. Settings

Settings may include:

- Launcher preferences
- Theme
- Language
- Java configuration
- Memory allocation
- Download settings
- Update settings
- Game-window settings
- Discord Rich Presence preferences
- Privacy-related preferences
- Experimental features

Settings should be stored separately from source code and should not be committed to Git.

---

## 10. Local Storage

Local launcher data may include:

- Configuration
- Profiles
- Cache
- Logs
- Installed-version metadata
- Account/session data
- Download state

Sensitive authentication data should be separated from ordinary settings where practical.

The project `.gitignore` should exclude local runtime data, tokens, sessions, secrets, caches, and developer-specific files.

---

## 11. Update System

A future public update system may be responsible for:

- Checking launcher versions
- Retrieving release metadata
- Downloading updates
- Verifying update integrity
- Applying updates
- Supporting rollback or recovery where practical

A public updater should not trust unsigned or unverified update metadata without careful consideration.

---

## 12. Diagnostics and Repair

Diagnostic functionality may help detect and repair problems involving:

- Java configuration
- Missing files
- Corrupt downloads
- Version metadata
- Authentication state
- Network connectivity
- Libraries
- Native files
- Launcher configuration

Diagnostic output should avoid exposing credentials.

---

## 13. Mod and Content Integration

Leviathan Launcher may integrate with third-party content providers such as Modrinth.

Potential functionality includes:

- Mod discovery
- Mod installation
- Modpack installation
- Resource packs
- Shaders
- Content updates

Third-party content remains subject to its own licenses, permissions, and provider terms.

See [THIRD_PARTY_NOTICES.md](../THIRD_PARTY_NOTICES.md).

---

## 14. Discord Integration

The launcher may support Discord Rich Presence.

Discord integration should remain optional where practical and should not expose authentication tokens or other private launcher data.

---

## 15. External Services

Leviathan Launcher may communicate with:

### Microsoft
Used for Microsoft account authentication.

### Xbox Live
Used as part of the Microsoft-to-Minecraft authentication chain.

### XSTS
Used to obtain Xbox security authorization required by Minecraft authentication.

### Minecraft Services
Used for Minecraft authentication, ownership verification, and profile retrieval.

### Modrinth
May be used for third-party Minecraft content functionality.

### GitHub
May be used for project hosting, documentation, development, and potentially future release metadata.

External services are separate trust boundaries and remain subject to their own terms and availability.

---

## 16. Security Principles

The project should aim to follow these principles:

- Do not collect Microsoft passwords
- Do not embed confidential client secrets in the desktop application
- Treat authentication tokens as sensitive
- Keep secrets out of source control
- Avoid logging credentials
- Verify ownership before legitimate authenticated launch
- Use trusted network endpoints
- Validate downloaded content where practical
- Keep dependencies updated
- Separate third-party licenses from Leviathan's proprietary license
- Avoid security, licensing, or entitlement bypasses

---

## 17. Repository Structure

The public project-information repository currently includes documentation such as:

```text
Leviathan-Launcher/
├── .gitignore
├── CHANGELOG.md
├── LICENSE
├── PRIVACY.md
├── README.md
├── SECURITY.md
├── THIRD_PARTY_NOTICES.md
├── .github/
│   ├── dependabot.yml
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.md
│       └── feature_request.md
└── docs/
    ├── ARCHITECTURE.md
    └── AUTHENTICATION.md
```

The repository may expand as the project approaches public testing.

---

## 18. Current Development Boundaries

Leviathan Launcher is currently:

- Privately developed
- Accessible only to the developer
- Not publicly distributed
- Under active architectural development
- Awaiting Minecraft AppID approval
- Subject to significant internal changes before public release

This architecture document should be updated as major systems change.

---

## Related Documents

- [README](../README.md)
- [Authentication Architecture](AUTHENTICATION.md)
- [Privacy Policy](../PRIVACY.md)
- [Security Policy](../SECURITY.md)
- [License](../LICENSE)
- [Third-Party Notices](../THIRD_PARTY_NOTICES.md)
- [Changelog](../CHANGELOG.md)

---

**Leviathan Launcher**  
Architecture Documentation  
Copyright © 2026 Danni. All Rights Reserved.
