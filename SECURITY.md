# Leviathan Launcher — Security Policy

**Status:** Private development  
**Last updated:** 8 September 2026

Security reports are welcome. Do not publish secrets, active credentials, exploit details that endanger users, or personal data in a public issue.

## Reporting a vulnerability

Use GitHub's private vulnerability-reporting or security-advisory workflow for this repository when it is available. If private reporting is not available, do not post exploit details publicly; use the support guidance in `SUPPORT.md` to establish a safe contact path first.

For non-security bugs, use the repository's normal issue tracker.

Repository:

https://github.com/Lapinite/Leviathan-Launcher

## What to include

A useful report may include:

- affected version or commit;
- affected operating system;
- clear reproduction steps;
- expected and actual behavior;
- security impact;
- sanitized logs or screenshots;
- whether exploitation requires authentication or user interaction.

Remove secrets and personal data before submitting anything.

## Never include

Do not send or publish:

- passwords;
- access or refresh tokens;
- session cookies;
- authorization codes;
- client secrets;
- private keys;
- signing keys;
- recovery phrases;
- recovery codes;
- payment credentials;
- database credentials;
- infrastructure credentials.

## Public-client authentication model

Leviathan Launcher is a public desktop client. It uses a system-browser authentication design with a localhost loopback callback and public-client flows.

The distributed launcher must not contain a confidential client secret. A public application identifier is not a password or secret, but administrative identifiers that are not needed in public documentation should still be omitted.

The current launcher authentication design does not require configured Microsoft Graph permissions for its Minecraft sign-in flow.

## Authentication requirements

The launcher must not intentionally implement:

- credential harvesting;
- cracked authentication;
- offline impersonation represented as legitimate Microsoft authentication;
- Minecraft ownership bypasses;
- entitlement bypasses;
- license circumvention;
- token theft;
- hidden production authentication bypasses.

Authentication should use modern public-client protections, including PKCE and state validation where applicable.

## Token handling

Authentication tokens are confidential.

The launcher should:

- keep tokens out of source control;
- redact tokens from logs and crash reports;
- avoid displaying raw tokens in the UI;
- restrict token use to the intended service and purpose;
- clear local authentication state on sign-out where practical;
- prefer secure operating-system credential storage;
- avoid durable weak-obfuscation storage for refresh credentials.

If secure persistent storage is unavailable, re-authentication is preferable to treating simple obfuscation as secure storage.

## Minecraft linking verification

Where Leviathan verifies a Minecraft profile through a verification server, the approved baseline is:

- a verification code remains the same while it is valid;
- codes expire after 10 minutes;
- rejoining while the code is still valid returns the same code;
- five failed attempts trigger a one-hour restriction;
- ten failed attempts trigger a stronger verification-server restriction or ban;
- successful verification resets the failed-attempt count;
- authorized staff may reset attempts or remove the verification restriction only after appropriate account-holder confirmation;
- sensitive staff actions must be permission-controlled and audited.

No additional escalation schedule should be treated as approved unless separately adopted.

## Leviathan Account recovery

Where platform accounts are available, security controls may include 2FA, recovery codes, a recovery phrase, session/device revocation, and staff-assisted recovery under controlled conditions.

A recovery phrase alone must not automatically authorize a high-risk takeover. Staff should not ask users to send a recovery phrase through ordinary support channels.

After staff-assisted 2FA removal, high-risk features should remain locked until 2FA is configured again. Stolen-account recovery should revoke existing sessions and device trust. Restored deleted accounts should require fresh session/device approval.

## High-risk actions

Purchases, gifting, transfers, trading, marketplace activity, sensitive account changes, and similar high-risk operations may require re-authentication, trusted-device/location approval, limits, temporary holds, or manual review.

## Server-side authority

Clients are untrusted. Sensitive state changes should be validated server-side. Economy and ownership mutations should be idempotent and auditable, with authoritative server-side records.

## Release security

Before a public release, Leviathan should have appropriate controls for:

- signed or integrity-verified updates;
- protected release workflows;
- secret scanning and push protection;
- protected primary branches;
- dependency review;
- rollback planning;
- secure build provenance where practical.

## Scope and authorization

A security policy is not authorization to attack third-party systems. Research must remain within systems the reporter owns or has explicit authorization to test.

Microsoft, Xbox, Minecraft Services, Mojang, GitHub, payment providers, and other external services are outside Leviathan's authorization scope unless those providers separately authorize testing.

## Minecraft disclaimer

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**
