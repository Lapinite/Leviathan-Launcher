# Leviathan Launcher

Leviathan Launcher is a third-party desktop launcher for **Minecraft: Java Edition**.

The launcher is designed for legitimate Minecraft owners and aims to provide a modern, customizable desktop experience with Microsoft account authentication, profiles, launcher customization, cosmetics, performance options, and additional quality-of-life features.

> **Project Status:** Private Development  
> **Current Access:** Developer Only

---

## About Leviathan Launcher

Leviathan Launcher is an independent Minecraft: Java Edition launcher focused on providing a modern, customizable, and user-friendly desktop experience.

Users authenticate using their own Microsoft account, and Minecraft ownership is verified through the official Microsoft, Xbox Live, XSTS, and Minecraft Services authentication systems.

Leviathan Launcher does **not** bypass:

- Minecraft authentication
- Microsoft authentication
- Game ownership requirements
- Minecraft licensing
- Account security
- Entitlement checks
- Microsoft or Mojang security systems

A legitimate Microsoft account with access to Minecraft: Java Edition is required to play.

---

## Access Notice

Leviathan Launcher is currently a **private development project**.

At this stage, development builds are restricted to the **Leviathan project portfolio** for:

- Development
- Authentication integration
- Game-launch testing
- User-interface development
- Technical testing
- API integration
- Security testing
- Minecraft Services integration

The launcher is **not currently available for public download or general use**.

There are currently no public builds, public beta versions, or public launcher downloads.

The GitHub repository is publicly accessible for project information, transparency, documentation, and review purposes.

Public testing or distribution may be introduced later when the project is considered ready.

---

## Features

Current and planned features include:

- Microsoft account authentication
- Xbox Live authentication
- XSTS authentication
- Minecraft Services authentication
- Minecraft: Java Edition ownership verification
- Minecraft player profiles
- Account management
- Multiple launcher profiles
- Minecraft version management
- Game installation management
- Custom launcher settings
- Launcher themes
- UI customization
- Cosmetics
- News and announcements
- Download management
- Automatic launcher updates
- Java configuration
- Performance settings
- Game launch options
- Modern desktop interface
- Future social and community features

Additional features may be introduced as development continues.

---

## Microsoft Authentication

Leviathan Launcher uses Microsoft's authentication infrastructure to authenticate users.

The authentication process involves:

1. Microsoft OAuth
2. Xbox Live authentication
3. Xbox Security Token Service (XSTS)
4. Minecraft Services
5. Minecraft ownership verification
6. Minecraft profile retrieval

Users authenticate through Microsoft's own authentication system.

Leviathan Launcher does **not** request or store Microsoft account passwords.

The launcher uses its own Microsoft Entra registered application.

Leviathan Launcher is configured as a **public desktop client**, meaning no confidential client secret is embedded inside the launcher.

---

## Minecraft AppID

Leviathan Launcher uses its own Microsoft Entra Application ID.

The AppID review submission is currently pending. Production Minecraft Services access remains subject to the applicable Microsoft/Minecraft AppID review and approval requirements.

The application requires Minecraft Services access for legitimate launcher functionality including:

- Authenticating Minecraft users
- Verifying Minecraft: Java Edition ownership
- Retrieving Minecraft player profiles
- Obtaining the authentication required to launch Minecraft
- Integrating Microsoft, Xbox Live, XSTS, and Minecraft Services authentication

The AppID is intended exclusively for Leviathan Launcher.

It must not be reused by unrelated launchers, applications, websites, or services.

---

## Minecraft Ownership

Leviathan Launcher is intended exclusively for users who legitimately own or otherwise have valid access to Minecraft: Java Edition.

The launcher uses Minecraft Services to verify that the authenticated Microsoft account has access to Minecraft.

Leviathan Launcher does not provide or support:

- Cracked authentication
- Minecraft ownership bypasses
- License bypasses
- Authentication bypasses
- Account impersonation
- Account sharing systems
- Unauthorized account access
- Circumvention of entitlement checks
- Circumvention of Microsoft or Mojang security systems

Users are responsible for using their own legitimate Microsoft and Minecraft accounts.

---

## Security

Security is an important part of Leviathan Launcher.

The project is designed so that:

- Microsoft passwords are never handled directly by Leviathan Launcher
- Authentication takes place through Microsoft's authentication infrastructure
- No confidential Microsoft client secret is distributed with the launcher
- Authentication tokens are used only where required for authentication and game services
- Minecraft ownership is verified using Minecraft Services
- The launcher does not attempt to bypass Microsoft or Mojang security systems
- Users authenticate using official Microsoft authentication systems
- Authentication-related testing is currently limited to the developer

Users should never provide their Microsoft password directly to Leviathan Launcher or to anyone claiming to represent the project.

---

## Privacy

Leviathan Launcher aims to process only the information necessary for launcher functionality.

Authentication-related information may be used for purposes including:

- Signing the user in
- Authenticating with Microsoft
- Authenticating with Xbox Live
- Authenticating with XSTS
- Authenticating with Minecraft Services
- Verifying Minecraft ownership
- Retrieving the authenticated Minecraft profile
- Launching Minecraft for legitimate account holders

Leviathan Launcher does not require users to provide their Microsoft account password directly to the application.

During the current private-development phase, access and authentication testing are limited to the developer.

A dedicated Privacy Policy may be published before public testing or release.

---

## Installation

Leviathan Launcher is currently under **private development**.

There is currently no official public download.

Development and testing builds are restricted to the Leviathan project portfolio.

Public installation packages may be published in the future when the launcher is ready for testing or release.

Future releases, when available, are expected to be published through the official repository:

https://github.com/Lapinite/Leviathan-Launcher

---

## Development

Leviathan Launcher is currently being developed as a desktop application.

Development areas include:

- Launcher UI
- Microsoft authentication
- Xbox Live authentication
- XSTS authentication
- Minecraft Services authentication
- Minecraft installation
- Game launching
- Account management
- Launcher profiles
- Version management
- Settings
- Launcher customization
- Cosmetics
- Update systems
- Performance configuration
- Java runtime configuration
- Download management

The project is actively evolving and components may change significantly during development.

---

## Project Status

**Current status:** Private Development

Leviathan Launcher is currently being developed and tested privately as part of the **Leviathan project portfolio**.

The launcher is not yet publicly distributed.

The GitHub repository is public for documentation, transparency, and project-review purposes, but public repository access does not mean that public launcher builds are currently available.

Features, authentication systems, user-interface elements, launcher behavior, APIs, infrastructure, and other components may change before public testing or release.

---

## Roadmap

Current development progress:

- [x] Microsoft Entra application registration
- [x] Microsoft account authentication integration
- [x] Public desktop client configuration
- [x] Xbox Live authentication integration
- [x] XSTS authentication integration
- [x] Minecraft Services integration
- [x] Private developer authentication testing
- [x] Submit Minecraft AppID review request
- [ ] Minecraft AppID approved
- [ ] Minecraft Services production authentication fully enabled
- [ ] Complete Minecraft installation management
- [ ] Improved Minecraft version management
- [ ] Multiple launcher profiles
- [ ] Cosmetics system
- [ ] Launcher customization system
- [ ] Automatic launcher updates
- [ ] Internal testing
- [ ] Public beta testing
- [ ] Stable public release

The roadmap may change throughout development.

---

## API Usage

Leviathan Launcher intends to use Microsoft, Xbox, XSTS, and Minecraft-related authentication services only for legitimate launcher functionality.

API access is not intended for:

- Automated account creation
- Credential harvesting
- Account theft
- Ownership circumvention
- Authentication bypasses
- Account resale
- Unauthorized account access
- Abuse of Microsoft infrastructure
- Abuse of Minecraft infrastructure
- Circumvention of licensing requirements

The project aims to comply with applicable Microsoft, Xbox, Mojang, and Minecraft requirements.

---

## Project Maintenance

Leviathan Launcher is currently developed and maintained as part of the **Leviathan project portfolio**.

During the current private-development phase, access to development builds is restricted to authorized project maintainers.

---

## Repository

Official repository:

https://github.com/Lapinite/Leviathan-Launcher


This repository contains project information, documentation, development resources, and other materials related to Leviathan Launcher.

Public visibility of this repository does **not** grant permission to copy, redistribute, modify, repackage, or reuse Leviathan Launcher or its original materials.

See the [LICENSE](LICENSE) file for the complete licensing terms.

---

## Public Availability

Leviathan Launcher is not currently available for public use.

At this stage there are:

- No official public launcher downloads
- No public beta builds
- No public release packages
- No public authentication testing program
- No general-access launcher distribution

This may change after development, testing, Minecraft AppID approval, and other release requirements have been completed.

---

## Usage

Users of Leviathan Launcher are expected to comply with:

- The Minecraft End User License Agreement
- Minecraft Usage Guidelines
- Microsoft account terms
- Xbox terms and policies
- Applicable Minecraft Services requirements
- Applicable Microsoft and Mojang policies

Leviathan Launcher is intended to complement the legitimate Minecraft experience, not circumvent it.

---

## Third-Party Services

Leviathan Launcher may integrate with services provided by:

- Microsoft
- Xbox
- Mojang Studios
- Minecraft Services

These services are operated independently from Leviathan Launcher and may have their own:

- Terms of service
- Privacy policies
- Availability requirements
- API restrictions
- Authentication requirements
- Usage policies

Leviathan Launcher does not control these third-party services.

---

## Disclaimer

Leviathan Launcher is an **independent third-party project**.

It is not affiliated with, sponsored by, endorsed by, operated by, or officially associated with:

- Microsoft Corporation
- Mojang Studios
- Xbox
- Minecraft

Unless explicitly stated otherwise by the relevant rights holder.

Minecraft, Microsoft, Xbox, Mojang, and related names, logos, trademarks, assets, and intellectual property remain the property of their respective owners.

References to Microsoft and Minecraft services are made only to describe compatibility, interoperability, and functionality.

---

## Trademark Notice

Minecraft is a trademark of Microsoft Corporation.

Microsoft, Xbox, Mojang, Minecraft, and other associated trademarks remain the property of their respective owners.

All third-party trademarks and intellectual property referenced by this project remain the property of their respective owners.

The **Leviathan Launcher** name, branding, original artwork, logo, launcher icons, visual identity, and original project materials are reserved by the Leviathan Launcher developer unless otherwise stated.

---

## Contributing

Leviathan Launcher is currently a private development project.

External code contributions are not currently being accepted unless explicitly authorized by the developer.

Contribution guidelines may be introduced in the future if the project becomes open to outside contributors.

---

## Security Reporting

If a security issue involving Leviathan Launcher is discovered, please avoid publicly disclosing sensitive technical details before the developer has had a reasonable opportunity to investigate the issue.

Security-related reports may be submitted through the project's official contact methods when they become available.

Good-faith security reports are appreciated.

---

## Contact

For project-related questions regarding Leviathan Launcher, authentication integration, Minecraft AppID approval, or project development:

**Project:** Leviathan project portfolio

Repository:

https://github.com/Lapinite/Leviathan-Launcher

Additional contact methods may be added before public release.

---

## License

Leviathan Launcher is **proprietary software**.

Copyright © 2026 Leviathan project owner. All Rights Reserved.

Public visibility of this repository does not make Leviathan Launcher open-source software and does not grant permission to redistribute, modify, repackage, sell, sublicense, or commercially exploit the project.

The Leviathan Launcher name, branding, dragon artwork, icons, user-interface assets, original source code, and other original project materials are protected under the project's proprietary licensing terms.

Third-party libraries and materials remain subject to their respective licenses.

See the [LICENSE](LICENSE) file for the complete license terms.

---

## Current Development Summary

Leviathan Launcher is currently:

- Privately developed as part of the Leviathan project portfolio
- Development builds restricted to authorized project maintainers
- Not publicly distributed
- Using its own Microsoft Entra application registration
- Using Microsoft account authentication
- Using Xbox Live authentication
- Using XSTS authentication
- Integrating Minecraft Services
- Awaiting Minecraft AppID approval
- Being tested privately
- Preparing for continued development and eventual public testing

---

**Leviathan Launcher**  
A modern third-party desktop launcher for legitimate Minecraft: Java Edition players.

**Current access:** Developer only  
**Current status:** Private Development
