# Leviathan Launcher Security Policy

**Project status:** Private Development

Leviathan Launcher takes security issues seriously.

This document explains how to report potential security vulnerabilities involving Leviathan Launcher and what kinds of testing are considered appropriate.

> **Current access:** Leviathan Launcher is currently privately developed and is not publicly distributed.

---

## Supported Versions

Leviathan Launcher has not yet reached a public stable release.

| Version | Supported |
| --- | --- |
| Private development builds | Developer testing only |
| Public releases | Not yet available |

This table will be updated when public releases begin.

---

## Reporting a Security Vulnerability

If you believe you have discovered a security issue involving Leviathan Launcher, please avoid publishing sensitive details publicly before the developer has had a reasonable opportunity to investigate.

For now, contact the developer through:

**Developer:** Danni  
**GitHub:** https://github.com/Lapinite  
**Repository:** https://github.com/Lapinite/Leviathan-Launcher

A dedicated security contact or private vulnerability-reporting channel may be added before public release.

When reporting an issue, include as much useful information as possible, such as:

- A clear description of the vulnerability
- The affected launcher component
- Steps required to reproduce it
- The expected behavior
- The actual behavior
- Relevant error messages
- Screenshots, where appropriate
- Operating system and Java version
- Launcher version or commit
- Potential security impact
- Suggested mitigation, if known

Do **not** include passwords, private keys, access tokens, refresh tokens, session cookies, recovery codes, or other credentials in a public GitHub issue.

---

## Sensitive Reports

Potential vulnerabilities involving any of the following should be treated as sensitive:

- Microsoft authentication
- Xbox Live authentication
- XSTS authentication
- Minecraft Services authentication
- Access tokens
- Refresh tokens
- Session information
- Account impersonation
- Ownership verification
- Launcher update mechanisms
- Remote code execution
- Arbitrary file writes
- Path traversal
- Command injection
- Code-signing systems
- Download verification
- Launcher infrastructure
- Private APIs
- Private keys
- Developer credentials
- Authentication configuration
- User data exposure

Please avoid publicly disclosing exploit details for these issues before a fix can be investigated.

---

## Authentication Security

Leviathan Launcher is designed to use official Microsoft authentication infrastructure.

The project is intended to follow these principles:

- Microsoft passwords are not entered directly into Leviathan Launcher
- No confidential Microsoft client secret is embedded in the desktop application
- Authentication occurs through Microsoft
- Xbox Live and XSTS authentication are used where required
- Minecraft Services is used for legitimate ownership and profile verification
- Authentication tokens are treated as sensitive
- Authentication bypasses are not intentionally supported

The Microsoft Entra Application ID used by Leviathan Launcher is an identifier, not a secret.

Private keys, client secrets, account tokens, and other confidential credentials must never be committed to the repository.

---

## Credential Handling

Do not commit or publish:

- Microsoft access tokens
- Microsoft refresh tokens
- Xbox Live tokens
- XSTS tokens
- Minecraft access tokens
- Session cookies
- Client secrets
- Private keys
- Signing keys
- API secrets
- Recovery codes
- Personal authentication files
- Developer credentials

The repository's `.gitignore` should exclude local token, session, environment, cache, and credential files where applicable.

If a credential is accidentally committed, removing it from the latest commit is **not sufficient**.

The affected credential should be considered compromised and revoked or rotated as soon as possible.

---

## Dependency Security

Leviathan Launcher may rely on third-party libraries and tools.

Dependencies should be obtained from trusted sources and updated when necessary to address known security issues.

Before public release, the project may introduce additional dependency-scanning or software-composition-analysis tooling.

---

## Download and Update Security

Future public releases should take reasonable measures to protect launcher downloads and update mechanisms from tampering.

Possible protections may include:

- HTTPS-only downloads
- Trusted release hosting
- File hashes
- Digital signatures
- Code signing
- Verified update metadata
- Restricted release credentials

These mechanisms may evolve as the project approaches public distribution.

---

## Good-Faith Security Research

Good-faith security research is welcome when it is conducted responsibly.

Researchers should:

- Avoid accessing accounts or data that do not belong to them
- Avoid damaging systems or data
- Avoid service disruption
- Avoid denial-of-service testing
- Avoid credential theft
- Avoid persistence on systems
- Avoid malware deployment
- Stop testing if sensitive user data is exposed
- Report vulnerabilities privately where reasonably possible
- Allow reasonable time for investigation and remediation before public disclosure

Nothing in this policy grants permission to access third-party systems, Microsoft services, Mojang services, Minecraft Services, GitHub, or any infrastructure without authorization.

Testing of third-party services remains subject to those providers' own policies and authorization requirements.

---

## Out of Scope

Unless explicitly authorized, the following are out of scope:

- Social engineering
- Phishing
- Credential stuffing
- Password spraying
- Denial-of-service attacks
- Physical attacks
- Testing against accounts you do not own
- Testing against Microsoft, Xbox, Mojang, Minecraft Services, GitHub, or other third-party infrastructure without authorization
- Malware deployment
- Destructive testing
- Data exfiltration beyond what is necessary to demonstrate an issue
- Publishing private credentials or authentication tokens

---

## Public Issues vs. Security Reports

Normal bugs can be reported through the GitHub repository when public issue tracking is available.

Examples of normal bugs include:

- UI layout problems
- Non-sensitive crashes
- Version-selection issues
- Display problems
- Cosmetic glitches
- Non-security download errors

Security-sensitive issues should not include exploitable details in public issue threads.

---

## Disclosure Process

For a valid security report, the developer may:

1. Acknowledge the report
2. Reproduce and investigate the issue
3. Determine severity and affected versions
4. Develop a fix or mitigation
5. Test the fix
6. Release or deploy the fix where appropriate
7. Coordinate disclosure where reasonable

Because Leviathan Launcher is currently privately developed, response times are not guaranteed.

---

## Security Updates

Before public release, Leviathan Launcher may introduce a formal security-update policy.

Critical vulnerabilities may require:

- Mandatory launcher updates
- Token revocation
- Credential rotation
- Disabled versions
- Backend configuration changes
- Emergency releases

---

## Third-Party Vulnerabilities

Security vulnerabilities affecting Microsoft, Xbox, Mojang Studios, Minecraft Services, Java, GitHub, or other third-party software should generally be reported to the relevant third-party provider.

Leviathan Launcher does not control those services.

If a third-party vulnerability specifically creates a security issue in Leviathan Launcher, it may still be appropriate to notify the Leviathan developer as well.

---

## No Guarantee of Security

Reasonable efforts may be made to improve security, but no software can be guaranteed to be completely secure or free of vulnerabilities.

Leviathan Launcher is currently under active development and may change significantly before public release.

---

## Contact

**Developer:** Danni  
**GitHub:** https://github.com/Lapinite  
**Repository:** https://github.com/Lapinite/Leviathan-Launcher

A dedicated security email or GitHub private vulnerability-reporting mechanism may be added later.

---

## Independent Project Notice

Leviathan Launcher is an independent third-party project.

It is not affiliated with, sponsored by, endorsed by, operated by, or officially associated with Microsoft Corporation, Mojang Studios, Xbox, or Minecraft unless explicitly stated otherwise.

---

**Leviathan Launcher**  
Security Policy  
Copyright © 2026 Danni. All Rights Reserved.
