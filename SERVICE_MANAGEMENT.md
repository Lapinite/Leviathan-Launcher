# Leviathan Launcher — Service Management

**Status:** Private development / pre-release  
**Last updated:** 8 September 2026

This document provides public, non-sensitive service-management context for Leviathan Launcher.

## Application

**Application name:** Leviathan Launcher  
**Application type:** Public desktop client  
**Project reference:** https://github.com/Lapinite/Leviathan-Launcher

No tenant identifier, object identifier, private credential, signing key, token, recovery material, or infrastructure secret is intentionally published in this document.

## Purpose

Leviathan Launcher is an independently developed third-party desktop launcher for legitimate owners of Minecraft: Java Edition.

Its authentication design is intended to:

- authenticate through Microsoft;
- continue through Xbox Live and XSTS where required;
- authenticate with Minecraft Services;
- verify legitimate entitlement/ownership;
- retrieve the authenticated Minecraft profile;
- launch Minecraft only for legitimate authenticated users.

A separate Leviathan Account may provide optional platform functionality but must not replace Microsoft/Minecraft authentication for game launch.

## Microsoft identity configuration

The launcher is configured as a public desktop application.

Current design requirements:

- system-browser authentication;
- Authorization Code flow with PKCE;
- localhost loopback redirect;
- public-client flows enabled;
- legacy Live SDK support disabled;
- personal Microsoft accounts as the supported sign-in audience;
- no confidential client secret in the launcher;
- no configured Microsoft Graph permissions required for the current Minecraft authentication flow;
- no Web or SPA redirect configuration unless a future reviewed architecture requires it.

## Credentials and identifiers

The launcher must not distribute or publish confidential credentials.

Examples of confidential material include:

- client secrets;
- private keys;
- signing private keys;
- access and refresh tokens;
- session cookies;
- recovery credentials;
- payment-provider secrets;
- database credentials;
- infrastructure credentials.

Public-client application identifiers are not passwords, but this document omits identifiers that are not necessary for public service-management context.

## API permissions

Leviathan follows least privilege. The current launcher does not require configured Microsoft Graph permissions for its Minecraft authentication flow.

Unrelated permissions for mail, contacts, calendars, files, Teams, or organizational directory data must not be added without a documented feature requirement, privacy review, and security review.

## Separate backend services

If future Leviathan backend services require confidential Microsoft credentials or server-to-server Microsoft API access, those services should use an architecture and application registration appropriate for confidential server-side workloads. Confidential credentials must not be embedded in the desktop launcher.

## Minecraft Services approval

Production Minecraft Services access remains subject to the applicable Microsoft/Minecraft AppID review and approval requirements.

Leviathan must not claim approval before it has actually been granted and verified.

The application must not bypass authentication, ownership, entitlement, licensing, or safety controls.

## Publisher state

The project does not currently publish a custom production domain in this document. Publisher verification must not be claimed until a domain is legitimately controlled and Microsoft verification is actually completed.

## Change management

Changes to the following areas require deliberate review before production deployment:

- supported account types;
- redirect URIs;
- OAuth/OIDC flow behavior;
- requested scopes;
- API permissions;
- public-client configuration;
- publisher information;
- authentication libraries;
- token storage;
- Minecraft Services behavior;
- update signing and release distribution.

Security-sensitive changes should be documented, tested, and reviewable.

## Operational principles

Leviathan follows these service-management principles:

- clients are untrusted;
- sensitive mutations are server-authoritative;
- secrets do not belong in public repositories;
- least privilege is preferred;
- high-risk operations are audited;
- external provider failures fail safely;
- production status is not claimed for prototype-only features.

## Related documents

- Terms: https://github.com/Lapinite/Leviathan-Launcher/blob/main/TERMS.md
- Privacy: https://github.com/Lapinite/Leviathan-Launcher/blob/main/PRIVACY.md
- Security: https://github.com/Lapinite/Leviathan-Launcher/blob/main/SECURITY.md
- Support: https://github.com/Lapinite/Leviathan-Launcher/blob/main/SUPPORT.md
- Authentication: https://github.com/Lapinite/Leviathan-Launcher/blob/main/docs/AUTHENTICATION.md

## Minecraft disclaimer

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**
