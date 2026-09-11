# Leviathan Launcher Authentication Architecture

**Status:** Private development  
**Last updated:** 8 September 2026

Leviathan Launcher is designed to authenticate legitimate Minecraft: Java Edition users through Microsoft's official identity infrastructure and the Xbox/XSTS/Minecraft Services chain where required.

This document intentionally omits private administrative identifiers and confidential credentials.

## Goals

The authentication system is designed to:

- authenticate through Microsoft without collecting a Microsoft password in a Leviathan form;
- use a desktop public-client flow;
- authenticate with Xbox Live and XSTS as required;
- authenticate with Minecraft Services;
- verify legitimate Minecraft ownership or entitlement;
- retrieve the authenticated Minecraft profile;
- obtain credentials required for legitimate game launch.

It is not designed to bypass authentication, ownership, licensing, entitlements, or safety controls.

## Current Entra configuration baseline

The current intended app-registration baseline is:

- public desktop client;
- personal Microsoft accounts;
- system browser;
- Authorization Code with PKCE;
- localhost loopback redirect;
- public client flows enabled;
- legacy Live SDK support disabled;
- no confidential client secret;
- no Web redirect URI;
- no SPA redirect URI;
- no configured Microsoft Graph permissions required by the Minecraft authentication flow.

## Authentication flow

```text
Leviathan Launcher
        |
        v
Microsoft Authentication
        |
        v
Microsoft Token for Required Xbox/Minecraft Flow
        |
        v
Xbox Live Authentication
        |
        v
XSTS Authorization
        |
        v
Minecraft Services Authentication
        |
        +-----------------------+
        |                       |
        v                       v
Entitlement / Ownership     Minecraft Profile
Verification                Retrieval
        |                       |
        +-----------+-----------+
                    |
                    v
             Legitimate Launch
```

## Microsoft authentication

The launcher opens Microsoft-controlled authentication in the system browser. A localhost loopback callback returns the authorization response to the desktop application.

PKCE protects the authorization-code exchange for the public client. State validation should be used to bind the callback to the initiating login attempt.

The launcher must not embed a confidential client secret.

## Xbox Live and XSTS

After Microsoft authentication, the launcher performs the provider-required Xbox Live and XSTS steps needed for Minecraft authentication.

Provider errors should be surfaced without leaking tokens or authorization headers.

## Minecraft Services

The XSTS result is used to authenticate with Minecraft Services. Leviathan Launcher's Minecraft AppID review has been approved. Production use remains subject to the approved configuration and applicable service requirements.

The project must not claim approval until it has actually been granted.

## Entitlement verification

Successful Microsoft sign-in alone is not proof that the user owns Minecraft: Java Edition.

Leviathan must verify the appropriate entitlement/ownership state before a normal authenticated launch.

## Minecraft profile

After successful authentication, the launcher may retrieve the Minecraft profile information needed for launcher functionality, such as a stable Minecraft profile identifier and username.

Only necessary information should be processed.

## Microsoft Graph

Leviathan's current Minecraft authentication flow does not require configured Microsoft Graph permissions.

The launcher should not request unrelated Graph access to mail, contacts, calendars, files, Teams, directory data, or authentication-method data.

## Token handling

Authentication tokens are sensitive. The launcher should:

- keep them out of source control;
- redact them from logs and crash reports;
- avoid displaying raw tokens;
- clear local state on sign-out where practical;
- use secure operating-system credential storage for durable sensitive tokens where practical;
- prefer re-authentication over weak persistent obfuscation.

## Safe logging

Useful diagnostics can include:

- authentication stage;
- timestamp;
- provider error code;
- HTTP status code;
- correlation/trace identifier;
- non-sensitive configuration state.

Never log passwords, full tokens, cookies, secrets, private keys, or authorization headers.

## Separate Leviathan Account

Optional Leviathan Account linking is separate from Microsoft/Minecraft authentication. It may provide platform features but cannot authorize game launch without valid Microsoft/Minecraft authentication and entitlement.

## Prohibited behavior

The launcher must not intentionally implement:

- cracked authentication;
- credential harvesting;
- token theft;
- ownership bypasses;
- entitlement bypasses;
- license circumvention;
- hidden production authentication bypasses;
- use of another application's registration or approval.
