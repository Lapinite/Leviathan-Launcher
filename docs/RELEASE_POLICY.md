# Leviathan Launcher — Release Policy

**Status:** Pre-release policy  
**Last updated:** 8 September 2026

This policy defines the minimum gates for representing Leviathan functionality as production-ready.

## General rule

A feature must not be described as live, approved, secure, compliant, or production-ready merely because code or documentation exists.

## Authentication release gate

Before public release, verify:

- Microsoft desktop public-client authentication works end to end;
- redirect configuration matches the shipping implementation;
- no client secret is shipped;
- no unnecessary Microsoft Graph permissions are configured;
- token logs are redacted;
- durable refresh credentials use appropriate secure storage or the app requires re-authentication;
- Minecraft entitlement verification works correctly;
- required Minecraft AppID approval has actually been obtained where required.

## Update-security gate

Before auto-update is trusted for public distribution, the project should implement appropriate integrity/authenticity controls for update metadata and artifacts and protect release credentials and workflows.

## Minecraft compliance gate

Do not commercially release paid Minecraft-visible client cosmetics, paid cape-like items, or equivalent Minecraft-integrated Premium entitlements until the project has sufficient legal and policy confidence for the specific implementation.

Do not redistribute Minecraft game binaries or pre-modded Minecraft JAR files contrary to applicable rules.

## Commerce gate

Before public payments, virtual currency, gifting, marketplace, or creator payouts, verify:

- real operator/trader information required by applicable law is published;
- privacy and retention rules match actual processing;
- consumer refund/withdrawal rules are implemented;
- payment-provider and tax obligations are addressed;
- fraud, chargeback, account-recovery, and high-risk-action controls are operational;
- minors/parental rules are implemented where required.

## Security gate

Before public release, review:

- branch protection and release permissions;
- secret scanning/push protection;
- dependency and third-party notices;
- update signing/integrity;
- session and token storage;
- vulnerability reporting;
- account-recovery and staff break-glass controls for any deployed platform accounts.

## Documentation gate

Public documentation must match actual behavior. Remove stale claims, dead links, unowned domains, fake contact information, and unverified approval statements.
