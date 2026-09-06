# Leviathan Launcher Authentication Architecture

**Status:** Private Development  
**Audience:** Project documentation and technical review

Leviathan Launcher is designed to authenticate legitimate Minecraft: Java Edition users through Microsoft's official authentication infrastructure.

This document describes the intended high-level authentication flow without exposing secrets, credentials, or sensitive implementation details.

---

## Goals

The authentication system is designed to:

- Authenticate users through Microsoft
- Avoid handling Microsoft account passwords directly
- Authenticate with Xbox Live
- Authenticate with Xbox Security Token Service (XSTS)
- Authenticate with Minecraft Services
- Verify legitimate Minecraft: Java Edition ownership or entitlement
- Retrieve the authenticated Minecraft profile
- Obtain the credentials required to launch Minecraft legitimately

The system is **not** intended to bypass authentication, ownership checks, licensing, entitlements, or security controls.

---

## Microsoft Entra Application

Leviathan Launcher uses its own Microsoft Entra application registration.

The application is configured as a **public desktop client**.

Because Leviathan Launcher is a desktop application, no confidential client secret is embedded in the launcher.

The Microsoft Application (Client) ID is an identifier and is not treated as a secret.

Private credentials such as client secrets, private keys, user access tokens, refresh tokens, or session data must not be committed to the repository.

---

## Authentication Flow

The intended flow is:

```text
Leviathan Launcher
        |
        v
Microsoft Authentication
        |
        v
Microsoft Access Token
        |
        v
Xbox Live Authentication
        |
        v
Xbox User Token
        |
        v
XSTS Authentication
        |
        v
XSTS Token
        |
        v
Minecraft Services Authentication
        |
        v
Minecraft Access Token
        |
        +----------------------+
        |                      |
        v                      v
Ownership / Entitlement   Minecraft Profile
Verification              Retrieval
        |                      |
        +----------+-----------+
                   |
                   v
             Game Launch
```

---

## 1. Microsoft Authentication

The user signs in through Microsoft's authentication infrastructure.

Leviathan Launcher should not display a custom password form for Microsoft credentials.

The launcher receives authentication results from Microsoft rather than receiving the user's password.

Depending on the final implementation, authentication may use a public-client-compatible Microsoft OAuth flow suitable for desktop applications.

---

## 2. Xbox Live Authentication

After successful Microsoft authentication, the launcher uses the Microsoft-issued token to authenticate with Xbox Live.

The resulting Xbox token is used only as required for the next stage of the authentication process.

---

## 3. XSTS Authentication

The Xbox token is exchanged with Xbox Security Token Service (XSTS).

XSTS provides the authorization information required to continue to Minecraft Services.

XSTS failures should be surfaced to the user without exposing sensitive tokens in logs or UI messages.

---

## 4. Minecraft Services Authentication

The XSTS authorization result is used to authenticate with Minecraft Services.

Minecraft Services may reject an application whose AppID has not been approved for the required APIs.

Leviathan Launcher's AppID has been submitted to Mojang Studios for review.

---

## 5. Ownership / Entitlement Verification

After Minecraft authentication succeeds, the launcher should verify that the authenticated account legitimately owns or otherwise has valid access to Minecraft: Java Edition.

Leviathan Launcher must not treat successful Microsoft authentication alone as proof of game ownership.

Failure of ownership or entitlement verification should prevent a normal authenticated game launch.

---

## 6. Minecraft Profile Retrieval

After authentication, the launcher may retrieve the authenticated Minecraft profile, including information required for launcher functionality such as:

- Minecraft UUID
- Minecraft username
- Profile information returned by Minecraft Services

Only information required for launcher functionality should be processed.

---

## 7. Token Handling

Authentication tokens are sensitive.

Leviathan Launcher should:

- Avoid printing full tokens to logs
- Avoid exposing tokens in crash reports
- Avoid storing tokens in source-controlled files
- Store local authentication state only where necessary
- Restrict token use to the services and purposes for which it was issued
- Clear or invalidate local authentication state when the user signs out
- Prefer secure operating-system storage where practical before public release

Files containing token or session data should remain excluded through `.gitignore`.

---

## 8. Error Handling

Authentication errors should be translated into useful user-facing messages where possible.

Examples include:

- Microsoft sign-in failed
- Public-client configuration error
- Xbox Live authentication failed
- XSTS authentication failed
- Minecraft Services rejected the AppID
- Minecraft ownership could not be verified
- Minecraft profile could not be retrieved
- Session expired

Raw access tokens or other credentials must never be included in user-facing error messages.

---

## 9. Logging

Authentication logging should be useful for development without exposing secrets.

Safe examples:

- Authentication stage name
- HTTP status code
- Microsoft / Xbox / Minecraft error code
- Correlation or trace identifiers
- Timestamp
- Non-sensitive configuration state

Unsafe examples:

- Access tokens
- Refresh tokens
- Session cookies
- Client secrets
- Private keys
- Full authorization headers

---

## 10. Sign-Out

Signing out should remove or invalidate locally stored Leviathan authentication state where practical.

If Microsoft or other providers maintain independent browser sessions, those sessions may remain governed by the relevant provider.

---

## 11. Security Boundaries

Leviathan Launcher does not control:

- Microsoft identity infrastructure
- Xbox Live
- XSTS
- Minecraft Services
- Mojang Studios systems

Those services are external trust boundaries and remain subject to their own terms, policies, availability, and security controls.

---

## 12. AppID Approval Status

Current state:

- [x] Microsoft Entra application registered
- [x] Public desktop client configuration enabled
- [x] Microsoft authentication integrated
- [x] Xbox Live authentication integrated
- [x] XSTS authentication integrated
- [x] Minecraft Services integration implemented
- [x] Mojang AppID approval request submitted
- [ ] Mojang AppID approval received
- [ ] Production Minecraft authentication fully verified after approval

---

## 13. Prohibited Authentication Behavior

Leviathan Launcher must not intentionally implement:

- Cracked authentication
- Offline impersonation presented as legitimate Microsoft authentication
- Ownership bypasses
- Entitlement bypasses
- License circumvention
- Credential harvesting
- Account theft
- Token theft
- Security-check bypasses
- Unauthorized reuse of another application's AppID

---

## Related Documents

- [README](../README.md)
- [Privacy Policy](../PRIVACY.md)
- [Security Policy](../SECURITY.md)
- [License](../LICENSE)
- [Third-Party Notices](../THIRD_PARTY_NOTICES.md)

---

**Leviathan Launcher**  
Authentication Architecture  
Copyright © 2026 Danni. All Rights Reserved.
