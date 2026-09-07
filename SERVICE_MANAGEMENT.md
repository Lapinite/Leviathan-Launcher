# Leviathan Launcher — Service Management

This document provides service-management and application-context information for **Leviathan Launcher**.

## Application

**Application name:** Leviathan Launcher

**Application type:** Public desktop client

**Project status:** Private development / pre-release

**Repository:**  
https://github.com/Lapinite/Leviathan-Launcher

## Purpose

Leviathan Launcher is a third-party desktop launcher for legitimate owners of Minecraft: Java Edition.

The launcher is designed to:

- authenticate users through Microsoft
- authenticate with Xbox Live and XSTS
- access Minecraft Services
- verify Minecraft ownership and entitlement
- retrieve the authenticated Minecraft profile
- manage Minecraft installations and launcher instances
- provide Leviathan launcher/client functionality
- optionally connect a separate Leviathan Account for platform features such as purchases, cosmetics, LeviCoins, Premium, social features and other Leviathan services

A Leviathan Account does **not** replace Microsoft authentication for launching Minecraft.

## Microsoft Entra Application

**Application display name:** Leviathan Launcher

**Application (Client) ID:**  
`118a3515-ac1e-4c8f-9a6b-a08cf7a32b67`

**Directory (Tenant) ID:**  
`7e7135d6-1a08-44ff-a736-cd549b529d67`

**Client type:** Public client / desktop application

**Supported users:** Microsoft account users supported by the configured Entra application registration.

## Authentication Model

Leviathan Launcher uses the Microsoft identity platform for authentication.

The intended authentication chain is:

1. Microsoft OAuth authentication
2. Xbox Live authentication
3. XSTS authorization
4. Minecraft Services authentication
5. Minecraft entitlement verification
6. Minecraft profile retrieval

The launcher must not:

- collect Microsoft account passwords
- embed or distribute a confidential client secret
- bypass Microsoft authentication
- bypass Minecraft ownership or entitlement checks
- bypass license checks
- disable Microsoft or Minecraft safety features
- use another application's AppID in place of Leviathan's own AppID

## OAuth / Desktop Client Security

Leviathan Launcher is treated as a public desktop client.

The authentication implementation should use:

- Microsoft identity platform v2 endpoints
- Authorization Code flow with PKCE
- system-browser authentication
- localhost/loopback redirect handling
- state and nonce validation where applicable
- secure token handling
- least-privilege permissions

Confidential credentials must never be embedded in the distributed launcher.

## Minecraft Services AppID Review

Production Minecraft Services access remains subject to the required Microsoft/Minecraft AppID approval process.

Leviathan must not present Minecraft authentication as production-approved until that approval has actually been received and verified.

The AppID review process requires Leviathan to remain compliant with the applicable Minecraft EULA and Usage Guidelines.

## API Permissions

Leviathan should request only permissions that are necessary for its documented authentication and service requirements.

The launcher should not request unrelated Microsoft Graph permissions such as access to:

- email
- contacts
- calendars
- OneDrive
- Teams
- organizational directory data

unless a future feature has a documented, reviewed and approved need for that permission.

## Application Credentials

The Leviathan Launcher desktop application must not use a client secret.

If future Leviathan backend services require confidential credentials, they must use a separate server-side application architecture and keep those credentials outside the launcher.

## Redirect URIs

The desktop launcher uses a public-client redirect configuration.

The intended system-browser flow uses a localhost loopback callback in accordance with Microsoft desktop-application guidance.

## Security

Security issues should be reported according to:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/SECURITY.md

The project applies the following principles:

- least privilege
- secure authentication
- no credential collection
- no authentication bypass
- no entitlement bypass
- no hidden developer authentication bypass in release builds
- no secrets committed to source control
- secure handling of tokens and credentials
- auditable security-sensitive changes

## Privacy

Privacy information is available at:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/PRIVACY.md

## Terms

Terms of service are available at:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/TERMS.md

## Support

Support information is available at:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/SUPPORT.md

## Application Ownership and Management

Leviathan Launcher is currently maintained through the Leviathan project repository.

Application registration, authentication configuration, release configuration and security-sensitive changes should be limited to authorized project administrators.

Changes to the following areas should receive additional review:

- Microsoft Entra application settings
- redirect URIs
- API permissions
- AppID configuration
- authentication implementation
- release signing
- update distribution
- production secrets
- Minecraft Services integration

## Change Management

Changes to authentication, permissions or identity-provider configuration should be documented and reviewed before production release.

In particular, changes to:

- supported account types
- redirect URIs
- OAuth scopes
- API permissions
- public-client configuration
- publisher information
- Microsoft/Minecraft authentication behavior

should not be deployed silently.

## Current Release State

Leviathan Launcher is currently under private development.

Public production availability, Microsoft/Minecraft AppID approval, publisher verification and other external approvals should not be represented as complete until they have actually been verified.

## Minecraft Disclaimer

NOT AN OFFICIAL MINECRAFT PRODUCT.  
NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.
