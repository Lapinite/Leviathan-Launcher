# Leviathan Launcher — Privacy Notice

**Status:** Pre-release / private development  
**Last updated:** 8 September 2026

This notice describes the privacy approach for Leviathan Launcher during private development and the requirements that apply before broader public operation.

## 1. Current scope

Leviathan is currently in private development. The public repository is primarily documentation and project information. Production account, commerce, marketplace, creator, and social systems must not be represented as live unless they are actually deployed.

## 2. Microsoft and Minecraft authentication

Leviathan is designed to authenticate legitimate Minecraft: Java Edition users through Microsoft's authentication infrastructure and the Xbox/XSTS/Minecraft Services chain where required.

Leviathan does not need users to type their Microsoft password into a Leviathan-controlled password form. Microsoft credentials are entered on Microsoft-controlled authentication surfaces.

Depending on the authentication stage, the launcher may process technical authentication data such as:

- authorization responses;
- short-lived access tokens;
- refresh credentials where required for session continuity;
- Xbox/XSTS authorization data;
- Minecraft access tokens;
- Minecraft profile identifiers and username;
- entitlement or ownership results;
- authentication error codes and correlation identifiers.

Authentication tokens are confidential and must not be committed to source control or intentionally exposed in public logs.

## 3. Microsoft Graph

The current Leviathan Launcher app registration does not require configured Microsoft Graph permissions for the Minecraft authentication flow. Leviathan should not request unrelated access to mail, contacts, calendars, files, Teams, or directory data.

If a future feature genuinely requires Microsoft Graph, the privacy notice and permission rationale must be updated before that feature is enabled.

## 4. Local launcher data

The launcher may store non-sensitive settings and operational state locally, such as:

- launcher preferences;
- installation and instance configuration;
- selected Java/runtime settings;
- game-version metadata;
- non-sensitive account display information;
- diagnostic preferences.

Sensitive credentials should use secure operating-system storage where practical. If secure persistent storage is unavailable, the launcher should prefer re-authentication over weak long-term credential storage.

## 5. Leviathan Accounts

If optional Leviathan Accounts are introduced, the service may need to process data required for identity, security, social, economy, purchase, entitlement, moderation, and recovery functions. Only data necessary for documented purposes should be collected.

A Leviathan Account is separate from Microsoft/Minecraft authentication and must not be used to bypass Minecraft ownership checks.

## 6. Security and anti-abuse data

To protect users and the platform, Leviathan services may process proportionate security information such as:

- login and verification timestamps;
- session and device identifiers;
- coarse security signals about new or unusual access;
- failed verification counts;
- fraud and abuse indicators;
- account-recovery events;
- moderation and enforcement records;
- audit records for sensitive administrative actions.

Security information should not be retained longer than needed for legitimate security, legal, operational, or dispute purposes.

## 7. Purchases and payment data

If commerce is launched, payment processing should use appropriate payment providers. Leviathan should avoid storing full payment-card details unless a compliant payment architecture specifically requires it.

Transaction records may include product, amount, currency, payment-provider reference, purchaser account, recipient Minecraft profile identifier, timestamps, refund/reversal state, and fraud state where needed for accounting, support, security, or legal obligations.

## 8. Virtual items and provenance

Where virtual items are supported, Leviathan may retain ownership and provenance records needed to prevent duplication, resolve disputes, enforce refunds or reversals, and preserve legitimate ownership history.

A Minecraft username is not a stable ownership key; a stable Minecraft profile identifier may be used where required.

## 9. Diagnostics and logs

Logs should follow data minimization. Safe diagnostic records may include stage names, timestamps, status codes, non-sensitive configuration state, and correlation identifiers.

Logs must not intentionally contain:

- Microsoft passwords;
- access or refresh tokens;
- authorization headers;
- session cookies;
- client secrets;
- private keys;
- recovery phrases or recovery codes;
- payment credentials.

## 10. Children and minors

Before public features directed to or likely to be used by minors are launched, Leviathan must implement an age/consent model appropriate to the relevant jurisdictions and feature risks. A generic age number must not be treated as sufficient for every country or every feature.

## 11. Retention

Leviathan should apply retention periods by data category and purpose. Account status does not justify indefinite retention of every category of personal data.

Data may be retained when reasonably required for security, fraud prevention, legal obligations, accounting, dispute resolution, or enforcement, subject to applicable law.

## 12. Sharing

Information may be transmitted to third parties where necessary to provide the requested functionality, including Microsoft/Xbox/Minecraft Services for authentication and infrastructure or payment providers for features that actually use those providers.

Leviathan does not authorize advertisers to access private conversations or authentication credentials through this launcher.

## 13. User rights

Applicable privacy law may provide rights such as access, correction, deletion, restriction, objection, or portability. The exact rights and exceptions depend on the user's jurisdiction and the reason data is processed.

Before a public service requiring statutory privacy contacts is launched, the project must publish the legally required operator/contact information.

## 14. Security

Security practices are described in `SECURITY.md`. Never post authentication tokens, recovery material, payment credentials, private keys, or other secrets in a public GitHub issue.

## 15. Changes

This notice will be revised before materially different public data processing begins.

## 16. Project reference

https://github.com/Lapinite/Leviathan-Launcher

## 17. Minecraft disclaimer

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**
