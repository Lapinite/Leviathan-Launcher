# Leviathan Launcher App Registration Policy

**Status:** Public policy  
**Last updated:** 5 October 2026

This document defines the registration and configuration rules Leviathan follows for Microsoft and Minecraft authentication integrations.

## Purpose

Authentication documentation explains how a user signs in. This policy separately defines which application registration Leviathan may use and how that registration must be configured and governed.

## Leviathan-owned registration

Leviathan must use its own approved Microsoft and Minecraft application registration for production authentication.

The project must not:

- borrow another launcher's client ID or AppID;
- impersonate another application registration;
- ship credentials or identifiers obtained from an unrelated project;
- claim approval that has not actually been granted;
- bypass registration restrictions or provider review requirements.

## Public-client baseline

The intended desktop launcher registration is a public client and should use:

- personal Microsoft accounts where required by the Minecraft flow;
- the system browser;
- Authorization Code with PKCE;
- a localhost loopback redirect;
- public client flows enabled;
- no confidential client secret embedded in the launcher;
- no unnecessary Web or SPA redirect URI;
- no unrelated Microsoft Graph permissions.

## Minecraft Services approval

Leviathan's production Minecraft Services access must remain tied to the registration that has actually been reviewed and approved for Leviathan.

If Microsoft or Minecraft changes registration, review, or API requirements, Leviathan must update its configuration rather than work around those requirements.

## Secrets and identifiers

Public client identifiers may be present where technically required, but secrets must never be committed to source control or exposed in logs, screenshots, crash reports, Discord messages, documentation, or client-side diagnostics.

Confidential client secrets are not appropriate for a desktop public-client authentication flow.

## Redirect URIs

Desktop authentication should use only approved redirect URIs required by the selected public-client flow. Leviathan should avoid adding broad or unnecessary redirect URIs.

## Permission minimization

The launcher should request only permissions required for legitimate Minecraft authentication and launch.

It must not request unrelated access to mail, contacts, calendars, files, Teams, directory data, or authentication-method data.

## Change control

Changes to production authentication registration should be reviewed before release. Review should cover:

- client/application identity;
- redirect URIs;
- account types;
- public-client settings;
- requested scopes and permissions;
- Minecraft Services compatibility;
- secret handling;
- rollback and incident response.

## Related documentation

See `AUTHENTICATION.md` for the user authentication flow, Xbox/XSTS/Minecraft Services chain, entitlement verification, profile retrieval, token handling, and safe logging.
