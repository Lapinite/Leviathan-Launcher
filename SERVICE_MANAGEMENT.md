# Leviathan Launcher — Service Management

This document provides public service-management and application-context information for **Leviathan Launcher**.

## Application

**Application name:** Leviathan Launcher  
**Application type:** Public desktop client  
**Project status:** Private development / pre-release  
**Repository:** https://github.com/Lapinite/Leviathan-Launcher

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
- optionally connect a separate Leviathan Account for platform features

A Leviathan Account does **not** replace Microsoft authentication for launching Minecraft.

## Microsoft Authentication

Leviathan Launcher uses the Microsoft identity platform as a **public desktop client**.

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
- substitute another application's AppID for Leviathan's own application registration

## Desktop OAuth Configuration

The launcher is intended to use:

- Microsoft identity platform v2 endpoints
- Authorization Code flow with PKCE
- system-browser authentication
- localhost loopback redirect handling
- public client flows
- state validation
- nonce validation where applicable
- secure token handling
- least-privilege permissions

The current desktop redirect model uses:

`http://localhost`

This document intentionally does **not** publish internal tenant metadata, administrative object identifiers, credentials, or other unnecessary Entra configuration details.

## Public and Confidential Information

Public client applications necessarily contain some non-secret configuration, such as the application identifier and public redirect configuration.

The following must **never** be published, committed to the repository, logged unnecessarily, or distributed with the launcher:

- client secrets
- certificate private keys
- access tokens
- refresh tokens
- session tokens
- signing private keys
- recovery credentials
- Recovery Phrases
- recovery codes
- payment-provider secrets
- API secrets
- database credentials
- infrastructure credentials
- private encryption keys
- internal administrative credentials

Administrative tenant IDs, object IDs, internal account identifiers, and similar metadata should not be published unless there is a documented operational requirement.

## API Permissions

Leviathan follows the principle of least privilege.

The launcher should not request unrelated Microsoft Graph permissions for data such as:

- email
- contacts
- calendars
- files
- OneDrive
- Teams
- organizational directory data
- Microsoft 365 content

Microsoft Graph permissions should only be added if a future feature has a specific, documented, reviewed requirement.

## Client Credentials

Leviathan Launcher is a public desktop application and must not rely on a confidential client secret.

If future Leviathan backend services require confidential credentials, they should use an appropriate server-side architecture and, where appropriate, a separate application registration.

Confidential credentials must remain outside the distributed launcher.

## Redirect URIs

Redirect URIs must:

- match the actual launcher authentication implementation
- be explicitly configured
- avoid unrelated third-party domains
- avoid exposing authorization codes or tokens to untrusted applications
- be reviewed before production changes

Web or SPA redirect configurations should not be added unless an approved architecture actually requires them.

## Supported Accounts

Leviathan Launcher is intended for personal Microsoft accounts used for legitimate Minecraft authentication.

Supported account settings must remain aligned with:

- the Microsoft Entra application registration
- the actual authentication implementation
- Minecraft authentication requirements
- AppID review requirements

Changes to the sign-in audience must be reviewed before release.

## Leviathan Account Linking

Leviathan Account authentication is separate from Microsoft/Minecraft authentication.

A user may optionally link a Leviathan Account to access Leviathan platform features such as:

- purchases
- cosmetic ownership records
- LeviCoins
- Premium
- social features
- marketplace functionality
- creator features
- synchronized platform settings

A Leviathan Account must never replace Microsoft authentication for launching Minecraft.

One Leviathan Account may link multiple verified Minecraft profiles.

Linking and unlinking sensitive identities should use appropriate verification, authorization, and audit controls.

## Minecraft Services AppID Review

Production Minecraft Services access remains subject to the required Microsoft/Minecraft AppID approval process.

Leviathan must not represent Minecraft authentication as production-approved until that approval has actually been received and verified.

The project must remain compliant with the applicable Minecraft EULA, Usage Guidelines, Community Standards, and Microsoft identity/security requirements.

Applications or builds that bypass authentication, security, licensing, entitlement checks, or safety functionality must not be distributed.

## Security

Security information and vulnerability-reporting guidance are available at:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/SECURITY.md

Core security principles include:

- least privilege
- secure authentication
- no credential collection
- no authentication bypass
- no entitlement bypass
- no secrets committed to source control
- secure token handling
- auditable security-sensitive changes
- controlled recovery
- session revocation
- protection for high-risk actions

## Privacy

Privacy information is available at:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/PRIVACY.md

Leviathan should collect and retain only data needed for documented operational, security, legal, or product purposes.

Sensitive authentication credentials must not be retained unnecessarily.

## Terms

Terms of service are available at:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/TERMS.md

## Support

Support information is available at:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/SUPPORT.md

## Application Ownership and Management

Leviathan Launcher is currently maintained through the Leviathan project repository.

Application registration, authentication configuration, release configuration, and security-sensitive changes should be limited to authorized project administrators.

Changes to the following areas should receive additional review:

- Microsoft Entra application settings
- supported account types
- redirect URIs
- API permissions
- OAuth scopes
- AppID configuration
- authentication implementation
- publisher information
- release signing
- update distribution
- production secrets
- Minecraft Services integration
- confidential backend credentials
- security-sensitive feature flags

## Change Management

Changes to authentication, permissions, identity-provider configuration, or security-sensitive behavior should be documented and reviewed before production release.

Where appropriate, changes should include:

- a documented reason
- testing
- security review
- rollback planning
- audit history

## Publisher Information

Leviathan currently does not claim ownership of a custom production domain for publisher verification.

A custom publisher domain must not be configured until Leviathan actually owns or controls that domain and can complete the required verification.

Publisher verification must not be represented as complete until Microsoft has actually verified the publisher.

## Current Public Project Reference

Until Leviathan owns and operates an official project domain, the canonical public project reference is:

https://github.com/Lapinite/Leviathan-Launcher

Public legal and project URLs should use real, controlled resources rather than unowned or inactive domains.

## Current Release State

Leviathan Launcher is currently under private development / pre-release development.

The following must not be represented as complete until actually verified:

- public production launch
- Minecraft Services AppID approval
- Microsoft publisher verification
- custom publisher-domain verification
- production payments
- production marketplace settlement
- production creator payouts
- other external certifications or approvals

Prototype, local-test, and specification-only functionality must not be represented as live production functionality.

## Compliance Principles

Leviathan must not:

- unlawfully redistribute Minecraft game binaries
- distribute a modified Minecraft game JAR as a Leviathan product
- bypass Microsoft/Minecraft ownership checks
- bypass authentication or license checks
- disable Microsoft/Minecraft safety systems
- claim official Mojang or Microsoft endorsement without authorization
- use Mojang or Microsoft branding as Leviathan's own branding
- publish secrets in the launcher or repository

Minecraft game files should be retrieved only from authorized sources.

Independent mods and client components should remain separate from Minecraft game binaries and respect their applicable licenses.

## Minecraft Disclaimer

**NOT AN OFFICIAL MINECRAFT PRODUCT.  
NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**
