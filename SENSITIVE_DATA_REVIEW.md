# Public-Repository Sensitive Data Review

**Review date:** 8 September 2026

This package was prepared for public GitHub use with data minimization in mind.

## Intentionally omitted

The generated public files do not intentionally include:

- Microsoft Entra tenant identifiers;
- Entra object identifiers;
- confidential client secrets;
- access or refresh tokens;
- authorization codes;
- session cookies;
- private or signing keys;
- recovery phrases or recovery codes;
- payment credentials;
- database credentials;
- infrastructure credentials;
- private internal endpoints.

The package also avoids publishing an unowned custom domain as an official Leviathan domain.

## Public information retained

The package retains only public project references necessary for GitHub documentation, primarily:

https://github.com/Lapinite/Leviathan-Launcher

## Important limitation

A documentation scan cannot prove that the repository's Git history, build artifacts, local configuration, or future commits contain no secrets. Secret scanning and push protection should remain enabled, and any credential ever committed should be rotated even if later removed from the visible branch.
