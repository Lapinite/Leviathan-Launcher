# Leviathan Launcher — GitHub Update Map

**Prepared:** 8 September 2026

This package was built against the repository snapshot supplied for review, which contained the existing root legal/governance files and documentation listed below.

## Replace existing root files

Replace the current repository versions with the package versions of:

- `LICENSE`
- `NOTICE`
- `TERMS.md`
- `PRIVACY.md`
- `SECURITY.md`
- `SUPPORT.md`
- `SERVICE_MANAGEMENT.md`
- `THIRD_PARTY_NOTICES.md`
- `TRADEMARKS.md`
- `CODE_OF_CONDUCT.md`
- `CONTRIBUTING.md`
- `.gitignore`

## Add new root files

Add:

- `AUTHENTICATION_AND_APPID_POLICY.md`
- `MINECRAFT_COMPLIANCE.md`
- `LEGAL.md`
- `SENSITIVE_DATA_REVIEW.md`

## Replace documentation files

Replace:

- `docs/AUTHENTICATION.md`
- `docs/RELEASE_POLICY.md`

## Keep and review separately

These files were present in the supplied repository snapshot but are not replaced by this legal/security package because their content is primarily project/product documentation rather than legal policy:

- `README.md`
- `CHANGELOG.md`
- `ROADMAP.md`
- `docs/ARCHITECTURE.md`
- `docs/DEVELOPMENT.md`
- `docs/FAQ.md`
- `docs/INSTALLATION.md`
- `docs/TROUBLESHOOTING.md`
- `.github/CODEOWNERS`
- issue and pull-request templates
- Dependabot/workflow configuration
- asset documentation

Those files should still be checked for stale authentication claims, unowned domains, sensitive identifiers, and statements that imply production approval.

## Entra state reflected by this package

The public documentation reflects the intended current launcher configuration:

- public desktop client;
- personal Microsoft accounts;
- localhost loopback redirect;
- public-client flows enabled;
- legacy Live SDK support disabled;
- no client secret;
- no configured Microsoft Graph permissions for the Minecraft authentication flow;
- publisher verification not claimed;
- production Minecraft AppID approval not claimed unless actually received.

## Public-domain handling

The package does not use an unowned custom domain as Leviathan's official website or publisher domain. The GitHub repository is used as the current public project reference.
