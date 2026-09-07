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

**Client type:** Public client / desktop application

The Application (Client) ID is a public identifier used by the distributed desktop application and is not treated as a confidential credential.

Administrative tenant identifiers, object identifiers and other internal Entra metadata are not published unless there is a specific operational requirement.

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
- substitute another application's AppID for Leviathan's own AppID
- use undocumented credential-handling shortcuts to avoid the approved authentication process

## OAuth / Desktop Client Security

Leviathan Launcher is treated as a public desktop client.

The authentication implementation should use:

- Microsoft identity platform v2 endpoints
- Authorization Code flow with PKCE
- system-browser authentication
- localhost/loopback redirect handling
- state validation
- nonce validation where applicable
- secure token handling
- least-privilege permissions
- supported Microsoft authentication libraries and standards where practical

Confidential credentials must never be embedded in the distributed launcher.

## Public and Confidential Identifiers

The following may be present in public client software where operationally required:

- Application (Client) ID
- public redirect configuration
- public authentication endpoints
- non-sensitive application metadata

The following must not be published, committed to the repository, logged unnecessarily or distributed with the launcher:

- client secrets
- certificate private keys
- access tokens
- refresh tokens
- session tokens
- signing private keys
- recovery credentials
- Recovery Phrases
- recovery codes
- gift-card secrets or redemption secrets
- payment-provider secrets
- API secrets
- database credentials
- infrastructure credentials
- private encryption keys

Administrative identifiers such as tenant IDs and object IDs should not be published unless there is a documented operational reason.

## Minecraft Services AppID Review

Production Minecraft Services access remains subject to the required Microsoft/Minecraft AppID approval process.

Leviathan must not represent Minecraft authentication as production-approved until that approval has actually been received and independently verified.

The AppID review process requires Leviathan to remain compliant with the applicable:

- Minecraft EULA
- Minecraft Usage Guidelines
- Minecraft Community Standards
- Microsoft identity platform requirements
- Microsoft authentication and security requirements

Applications or builds that bypass security, authentication, license or entitlement checks must not be distributed.

Applications or builds that disable Microsoft/Minecraft safety features must not be distributed.

## API Permissions

Leviathan should request only permissions that are necessary for its documented authentication and service requirements.

Permissions should follow the principle of least privilege.

The launcher should not request unrelated Microsoft Graph permissions such as access to:

- email
- contacts
- calendars
- OneDrive
- Teams
- organizational directory data
- Microsoft 365 content

unless a future feature has a documented, reviewed and approved operational need for that permission.

Any newly requested permission should be reviewed before production deployment.

## Microsoft Graph

Microsoft Graph is not required merely because Leviathan uses Microsoft authentication.

Graph permissions must only be added if a specific Leviathan feature requires them and that requirement has been reviewed for:

- necessity
- privacy impact
- consent requirements
- data minimization
- retention
- security
- Microsoft platform-policy compliance

## Application Credentials

The Leviathan Launcher desktop application must not use a confidential client secret.

If future Leviathan backend services require confidential credentials, they must use an appropriate server-side architecture and keep those credentials outside the distributed launcher.

A future backend or confidential service should use a separate application/service registration where appropriate rather than turning the public launcher registration into a confidential application.

## Redirect URIs

The desktop launcher uses a public-client redirect configuration.

The intended system-browser authentication flow uses a localhost loopback callback in accordance with Microsoft desktop-application guidance.

Redirect URIs must:

- be explicitly configured
- match the application's real authentication implementation
- not redirect authentication results to unrelated third-party domains
- not expose authorization codes or tokens to untrusted applications
- be reviewed before production changes

Web or SPA redirect configurations should not be added to the launcher registration unless they are actually required by an approved architecture.

## Supported Account Types

Leviathan Launcher is intended to support Microsoft accounts required for legitimate Minecraft authentication.

Supported account types must remain aligned with:

- the Microsoft Entra registration
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
- synced platform settings

A Leviathan Account must never replace Microsoft authentication for launching Minecraft.

One Leviathan Account may link multiple verified Minecraft profiles.

Linking or unlinking valuable Minecraft identities should require appropriate security verification and auditing.

## Purchase and Cosmetic Identity

Leviathan uses a recipient-based ownership model for Minecraft-facing purchases.

Where supported and legally permitted:

- a purchase is delivered to a specific verified Minecraft profile
- ownership is stored using the Minecraft UUID
- usernames are treated as display metadata rather than permanent ownership identifiers
- original purchaser and original recipient provenance should be retained
- linking another Minecraft profile must not automatically transfer an existing entitlement

Commercial Minecraft-integrated features remain subject to applicable Minecraft rules and policy review.

## LeviCoins

LeviCoins are intended to operate as Leviathan platform credits.

LeviCoins must not:

- be treated as cryptocurrency
- be redeemable for cash
- be cashed out to fiat currency
- be converted into external monetary value
- be converted back into gift cards
- be represented as Minecoins or an official Mojang/Microsoft currency

Creator real-money payouts, where offered, must remain separate from LeviCoin balances.

## Security

Security issues should be reported according to:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/SECURITY.md

The project applies the following security principles:

- least privilege
- secure authentication
- no credential collection
- no authentication bypass
- no entitlement bypass
- no hidden developer authentication bypass in production builds
- no secrets committed to source control
- secure token handling
- server-side validation for sensitive operations
- auditable security-sensitive changes
- controlled recovery
- session revocation
- device-trust management
- protection for high-risk actions

## Account Recovery

Leviathan security and recovery systems are designed to use layered verification.

Where applicable, recovery may include:

- 2FA
- recovery codes
- a 24-word Recovery Phrase
- trusted sessions
- linked identity confirmation
- security review
- staff-assisted recovery under controlled conditions

A Recovery Phrase must not be treated as sufficient evidence by itself for sensitive account takeover.

Staff should never ask users to send their Recovery Phrase through normal support channels.

## Verification Security

Minecraft account-link verification should use the approved Leviathan verification rules:

- verification codes remain stable while valid
- verification codes expire after 10 minutes
- rejoining while the current code is valid does not rotate it
- five failed verification attempts trigger a one-hour restriction
- ten failed attempts trigger a stronger verification-server restriction or ban
- successful verification resets the approved attempt counter
- authorized staff may reset attempts or remove a verification restriction only after appropriate account-holder confirmation
- all sensitive reset actions should be audited

Unapproved escalation schedules must not be introduced silently.

## Privacy

Privacy information is available at:

https://github.com/Lapinite/Leviathan-Launcher/blob/main/PRIVACY.md

Leviathan should collect and retain only personal data needed for documented operational, security, legal or product purposes.

Sensitive authentication credentials must not be retained unnecessarily.

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
- supported account types
- redirect URIs
- API permissions
- AppID configuration
- OAuth scopes
- authentication implementation
- publisher information
- release signing
- update distribution
- production secrets
- Minecraft Services integration
- confidential backend credentials
- security-sensitive feature flags

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
- token handling
- AppID registration
- external authentication dependencies

should not be deployed silently.

Security-sensitive changes should have:

- a documented reason
- appropriate review
- rollback planning where applicable
- testing
- audit history

## Publisher Information

Leviathan currently uses the Microsoft Entra tenant's default publisher domain while the project does not own a custom production domain.

A custom publisher domain must not be configured until Leviathan actually owns or controls that domain and can complete the required DNS/domain verification.

Publisher verification must not be represented as complete until Microsoft has actually verified the publisher.

## Microsoft Partner / Publisher Verification

If Leviathan later uses Microsoft Partner Center publisher verification:

- the Partner account must be legitimate
- business/contact information must be accurate
- the publisher domain must meet Microsoft's verification requirements
- the relevant domain must be controlled by Leviathan
- the Microsoft Partner identifier must not be copied or borrowed from another organization
- MFA and other Microsoft verification requirements must be satisfied
- the verified-publisher badge must not be claimed before Microsoft grants it

## AppID Review Submissions

AppID review submissions should use accurate information matching the actual application registration.

Submissions may include:

- application name
- Application (Client) ID
- Directory/Tenant ID where Microsoft requests it
- legitimate contact information
- associated public project or repository
- accurate justification
- relevant operational context

AppID review submissions must not contain:

- passwords
- client secrets
- private keys
- access tokens
- refresh tokens
- Recovery Phrases
- recovery codes
- signing keys
- unrelated personal information

Duplicate review submissions should not be used in an attempt to accelerate the review process.

## Current Public Project Reference

Until Leviathan owns and operates an official project domain, the canonical public project reference is:

https://github.com/Lapinite/Leviathan-Launcher

Public legal and project URLs should use real GitHub resources rather than unowned or inactive domains.

## Current Release State

Leviathan Launcher is currently under private development / pre-release development.

The following must not be represented as complete until actually verified:

- public production launch
- Minecraft Services AppID approval
- Microsoft publisher verification
- custom publisher-domain verification
- production payments
- production LeviCoin economy
- production marketplace settlement
- production creator payouts
- other external certifications or approvals

Prototype, local-test and specification-only functionality must not be represented as live production functionality.

## Compliance Principles

Leviathan must not:

- redistribute Minecraft game binaries unlawfully
- distribute a modified Minecraft game JAR as a Leviathan product
- bypass Microsoft/Minecraft ownership checks
- bypass authentication or license checks
- disable Minecraft/Microsoft safety systems
- claim official Mojang/Microsoft endorsement without written authorization
- use Mojang/Microsoft branding as Leviathan's own branding
- publish secrets in the launcher or repository

Minecraft game files should be retrieved only from authorized sources.

Independent mods and client components should remain separate from Minecraft game binaries and must respect their applicable licenses.

## Minecraft Disclaimer

**NOT AN OFFICIAL MINECRAFT PRODUCT.  
NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**
