# Leviathan Launcher — Authentication and AppID Policy

**Status:** Pre-release policy  
**Last updated:** 8 September 2026

This policy defines how Leviathan Launcher must use Microsoft identity, Xbox/XSTS, Minecraft Services, and application-registration information.

## 1. Own application registration

Leviathan must use an application registration authorized for Leviathan. It must not borrow, copy, impersonate, or substitute another launcher's application registration or approval.

## 2. Public desktop client

Leviathan Launcher is a public desktop client. It cannot safely keep a confidential client secret because distributed desktop software can be inspected by end users.

The launcher therefore must not embed or distribute a client secret or private application credential.

## 3. Current authentication baseline

The current intended baseline is:

- Microsoft identity platform;
- personal Microsoft accounts;
- system-browser sign-in;
- Authorization Code with PKCE;
- localhost loopback callback;
- public-client flows enabled;
- legacy Live SDK support disabled;
- no Web redirect URIs;
- no SPA redirect URIs;
- no configured Microsoft Graph permissions for the Minecraft authentication flow;
- no client secret;
- no certificate private key distributed with the launcher.

## 4. Minecraft authentication chain

The intended high-level chain is:

1. Microsoft authentication;
2. Xbox Live authentication;
3. XSTS authorization;
4. Minecraft Services authentication;
5. Minecraft entitlement/ownership verification;
6. Minecraft profile retrieval;
7. legitimate game launch.

Microsoft authentication alone is not proof of Minecraft ownership.

## 5. OAuth scopes

OAuth/OIDC scopes requested at runtime must be limited to those actually required by the documented authentication flow.

Runtime OAuth scopes are not the same thing as granting broad Microsoft Graph permissions. The launcher must not add Graph permissions merely because Microsoft sign-in is used.

## 6. Microsoft Graph

The current launcher does not need configured Microsoft Graph permissions for the Minecraft authentication flow.

If a future feature calls Microsoft Graph, the minimum required delegated permission must be documented and reviewed before it is added. Unrelated access to mail, contacts, calendars, files, Teams, authentication methods, or organizational directory data is prohibited without a specific approved requirement.

## 7. Redirect URI policy

The desktop launcher uses a localhost loopback redirect appropriate to a system-browser public-client flow.

Redirect configuration must match the implementation. New Web, SPA, custom-scheme, or legacy redirect URIs must not be added without an architecture and security reason.

## 8. Secrets and sensitive information

Never publish or commit:

- client secrets;
- private keys;
- signing private keys;
- access or refresh tokens;
- authorization codes;
- session cookies;
- recovery material;
- payment-provider secrets;
- database or infrastructure credentials.

Public client identifiers are not authentication secrets, but administrative identifiers should still be omitted from public documentation when they serve no public purpose.

## 9. Token storage

Refresh credentials and other long-lived authentication material should use secure operating-system credential storage where practical.

Simple encoding, XOR, reversible obfuscation, predictable derived keys, or similarly weak storage must not be described as secure encryption. If secure durable storage is unavailable, re-authentication is preferable to weak persistent credential storage.

## 10. Logging and telemetry

Authentication logs may contain stage names, timestamps, HTTP status codes, provider error codes, and non-sensitive correlation identifiers.

They must not contain full tokens, passwords, cookies, authorization headers, secrets, or private keys.

## 11. AppID review

When Microsoft/Minecraft requires an AppID review, Leviathan submissions must:

- use the real Leviathan application name;
- use accurate application and tenant information in the private submission fields where requested;
- provide a real public project reference;
- give an accurate justification;
- submit one application identifier per form where required;
- avoid duplicate spam submissions;
- avoid placing passwords, tokens, recovery material, signing keys, or other secrets in the form.

The project must not claim approval before approval has actually been received.

## 12. Publisher verification

Publisher-domain or verified-publisher status must not be claimed unless the project legitimately controls the required domain and Microsoft has completed the relevant verification.

An unowned domain must never be presented as Leviathan's official publisher domain.

## 13. Separate confidential backend

If a future server-side Leviathan service needs confidential Microsoft credentials, it should use an appropriate separate server-side registration or architecture. Server credentials must remain on trusted infrastructure and must never be shipped inside the launcher.

## 14. Prohibited behavior

Leviathan must not intentionally implement:

- password harvesting;
- token theft;
- authentication bypasses;
- ownership or entitlement bypasses;
- license circumvention;
- disabling provider safety controls;
- use of another application's AppID or approval;
- fake Microsoft sign-in surfaces intended to capture credentials.

## 15. Review requirement

Authentication changes affecting sign-in audience, redirect URIs, requested scopes, API permissions, token storage, or Minecraft Services behavior require security review before production release.
