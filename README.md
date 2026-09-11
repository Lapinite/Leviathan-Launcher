<div align="center">

<img width="100%" src="assets/readme-hero.svg" alt="Leviathan Launcher">

<br>

<a href="https://github.com/Lapinite/Leviathan-Launcher/actions/workflows/build.yml"><img src="https://github.com/Lapinite/Leviathan-Launcher/actions/workflows/build.yml/badge.svg?branch=main" alt="Build"></a>
<img src="https://img.shields.io/badge/status-private%20development-06131d?style=flat-square" alt="Private development">
<img src="https://img.shields.io/badge/access-developer%20only-06131d?style=flat-square" alt="Developer only">
<img src="https://img.shields.io/badge/Minecraft-Java%20Edition-06131d?style=flat-square" alt="Minecraft Java Edition">
<img src="https://img.shields.io/badge/source-proprietary-06131d?style=flat-square" alt="Proprietary source">

**A modern third-party desktop launcher for legitimate Minecraft: Java Edition players.**

[Documentation](https://github.com/Lapinite/Leviathan-Docs) · [Security](SECURITY.md) · [Support](SUPPORT.md) · [Legal](LEGAL.md) · [License](LICENSE)

</div>

## Project status

> **Leviathan Launcher is under private development. There is no public launcher, installer, beta build, or general-access download at this time.**

The current work is focused on development, integration, security, compatibility testing, stabilization, validation, and release preparation. Public availability will only happen after the required technical and release gates are complete.

<table width="100%">
<tr>
<td width="25%" valign="top"><strong>Access</strong><br><sub>Developer only</sub></td>
<td width="25%" valign="top"><strong>Distribution</strong><br><sub>No public build</sub></td>
<td width="25%" valign="top"><strong>Authentication</strong><br><sub>Microsoft + Xbox + XSTS + Minecraft Services</sub></td>
<td width="25%" valign="top"><strong>Source</strong><br><sub>Private / proprietary</sub></td>
</tr>
</table>

## What Leviathan Launcher is

Leviathan Launcher is an independent Minecraft: Java Edition launcher designed around legitimate ownership, official Microsoft authentication, modern profile and instance management, customization, performance controls, connected services, and a broader Leviathan player platform.

The launcher is intended to complement the legitimate Minecraft experience. It does not bypass authentication, game ownership, licensing, entitlement checks, or Microsoft/Mojang security systems.

## Platform architecture

<p align="center">
  <img width="100%" src="assets/platform-flow.svg" alt="Animated Leviathan Launcher platform and authentication flow">
</p>

The public architecture shows the major trust boundaries and product areas without exposing proprietary source code, private endpoints, credentials, internal service names, database schemas, or sensitive implementation details.

## Authentication model

Leviathan Launcher uses Microsoft's official authentication infrastructure. Microsoft OAuth, Xbox Live, XSTS and Minecraft Services remain external service boundaries, while Leviathan maps verified Minecraft identity and ownership state into its own launcher/platform session model.

The launcher does **not** request or store Microsoft account passwords. It is configured as a public desktop client and does not distribute a confidential Microsoft client secret inside the application.

The Leviathan Launcher Minecraft AppID review has been approved. Production use remains subject to the applicable Microsoft, Minecraft, Xbox, service, application-configuration, security, and release requirements.

## Ownership and usage boundaries

A legitimate Microsoft account with valid access to Minecraft: Java Edition is required.

Leviathan Launcher does not provide or support:

- cracked authentication
- ownership or license bypasses
- authentication bypasses
- account impersonation
- unauthorized account access
- credential harvesting
- circumvention of entitlement checks
- circumvention of Microsoft, Xbox, Mojang, or Minecraft security systems

## Security design goals

Security work includes protecting authentication flows, reducing token exposure, validating ownership, limiting sensitive data, hardening launcher behavior, and testing release paths before distribution.

Public documentation and repositories must not contain production credentials, access tokens, refresh tokens, private keys, signing material, recovery material, private endpoints, database credentials, personal information, or internal-only infrastructure details.

Users should never provide a Microsoft password directly to Leviathan Launcher or to anyone claiming to represent the project.

## Privacy and data boundaries

Leviathan aims to process only information needed for legitimate launcher functionality, including authentication, ownership verification, Minecraft profile retrieval, launch operations, diagnostics, Cast/device state, and supported connected services.

Microsoft, Xbox, Mojang and Minecraft services remain responsible for their own account systems and credentials. Leviathan should retain only the identity mapping, entitlement/product state, session state, device state, diagnostics, telemetry and other platform data required for its own functionality.

A dedicated public privacy policy may be published before public testing or distribution.

## Development roadmap

| Area | Status |
| --- | --- |
| Microsoft Entra application registration | Complete |
| Microsoft account authentication integration | Complete |
| Xbox Live authentication integration | Complete |
| XSTS authentication integration | Complete |
| Minecraft Services integration | Complete |
| Private developer authentication testing | Complete |
| Minecraft AppID review | Approved |
| Minecraft Services production authentication validation | In progress |
| Minecraft installation management | In progress |
| Version and instance management | In progress |
| Launcher customization and cosmetics | In development |
| Automatic launcher updates | In development |
| Cast sender / TV receiver validation | In progress |
| Internal compatibility and regression testing | In progress |
| Public beta | Not started |
| Stable public release | Not started |

The roadmap changes as testing and architecture evolve. A checked or active development item does not imply public availability.

## Current validation focus

Current internal validation includes launcher behavior, authentication integration, compatibility, install/update flows, error recovery, Cast/device behavior, security checks, and connected platform work. Release-facing artifacts remain private until the project is ready for public distribution.

## Repository purpose

This public repository exists for project information, documentation, policies, public roadmap material, support/legal information, and future release-facing resources.

The proprietary implementation is not published here. Public visibility of this repository does not make Leviathan Launcher open source and does not grant permission to copy, redistribute, modify, repackage, sublicense, sell, or reuse proprietary Leviathan materials.

## Developer ecosystem

| Resource | Purpose |
| --- | --- |
| [Leviathan Docs](https://github.com/Lapinite/Leviathan-Docs) | Public ecosystem documentation |
| [Leviathan API Docs](https://github.com/Lapinite/Leviathan-API-Docs) | Public interface documentation |
| [Leviathan SDK](https://github.com/Lapinite/Leviathan-SDK) | Supported developer interfaces |
| [Leviathan Examples](https://github.com/Lapinite/Leviathan-Examples) | Safe example projects |
| [Leviathan Integrations](https://github.com/Lapinite/Leviathan-Integrations) | Public integration patterns |
| [Leviathan Server Tools](https://github.com/Lapinite/Leviathan-Server-Tools) | Public Minecraft server tooling |
| [Leviathan Status](https://github.com/Lapinite/Leviathan-Status) | Public service and incident information |

## Contributing

External code contributions are not currently being accepted unless explicitly authorized. Contribution guidance may be expanded if public contribution workflows are introduced later.

## Security reporting

Please avoid publicly disclosing sensitive technical details before the project has had a reasonable opportunity to investigate. See [SECURITY.md](SECURITY.md) for the current reporting guidance.

## Third-party services and trademarks

Leviathan Launcher may interoperate with services operated by Microsoft, Xbox, Mojang Studios, and Minecraft Services. Those services have their own terms, policies, availability requirements, and restrictions.

Leviathan Launcher is an independent third-party project. It is not affiliated with, sponsored by, endorsed by, operated by, or officially associated with Microsoft Corporation, Mojang Studios, Xbox, or Minecraft.

Minecraft, Microsoft, Xbox, Mojang, and related names, logos, trademarks, assets, and intellectual property remain the property of their respective owners.

## License

Leviathan Launcher is proprietary software.

Copyright © 2026 Leviathan project owner. All Rights Reserved.

See [LICENSE](LICENSE) for the complete terms.
