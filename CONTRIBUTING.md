# Contributing to Leviathan Launcher

**Status:** Private development / limited external contribution  
**Last updated:** 8 September 2026

Thank you for your interest in Leviathan Launcher. The project is proprietary unless a file explicitly states otherwise.

## Before contributing

Read:

- `LICENSE`;
- `CODE_OF_CONDUCT.md`;
- `SECURITY.md`;
- `MINECRAFT_COMPLIANCE.md` for Minecraft-related changes;
- `AUTHENTICATION_AND_APPID_POLICY.md` for identity/authentication changes.

## No implied source license

The ability to view, clone, fork, or open a pull request does not grant a general right to redistribute or create derivative Leviathan products. The repository license continues to apply.

## Rights in your contribution

By submitting a contribution for inclusion in Leviathan, you represent that you have the legal right to submit it and that it does not knowingly include material you are not permitted to provide.

To the extent you own rights in the submitted contribution, you grant the Leviathan project owner a perpetual, worldwide, non-exclusive, irrevocable, royalty-free license to use, reproduce, modify, distribute, sublicense, display, perform, and incorporate the contribution into Leviathan and related project materials, including proprietary distributions.

Do not submit third-party code or assets whose license is incompatible with that use.

## Security-sensitive changes

Authentication, account recovery, economy, marketplace, payments, update signing, permissions, cryptography, and secret-handling changes require heightened review.

Do not put real credentials, tokens, account recovery material, personal data, production endpoints containing secrets, or private infrastructure details in issues or pull requests.

## Minecraft-related changes

Changes must not intentionally add cracked authentication, entitlement bypasses, unauthorized Minecraft redistribution, or features that violate the project's compliance policy.

Paid Minecraft-integrated features must remain subject to the release gates described in `MINECRAFT_COMPLIANCE.md`.

## Pull requests

A useful pull request should:

- explain the problem and the change;
- keep scope focused;
- include tests where practical;
- avoid unrelated formatting churn;
- update relevant documentation;
- disclose new dependencies and their licenses;
- avoid sensitive information.

Submission does not guarantee acceptance.

## Vulnerabilities

Do not use a public pull request to disclose an exploitable security issue before coordinated handling. Follow `SECURITY.md`.
