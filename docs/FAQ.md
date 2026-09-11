# Leviathan Launcher FAQ

**Project status:** Private Development  
**Current access:** Developer Only

This FAQ answers common questions about Leviathan Launcher and its current development status.

---

## What is Leviathan Launcher?

Leviathan Launcher is an independent third-party desktop launcher for **Minecraft: Java Edition**.

It is being developed to provide a modern launcher experience with features such as:

- Microsoft account authentication
- Minecraft ownership verification
- Minecraft profiles
- Multiple launcher profiles
- Version management
- Launcher customization
- Performance configuration
- Cosmetics
- Update management
- Additional quality-of-life features

The project is currently under private development.

---

## Is Leviathan Launcher available to download?

No.

Leviathan Launcher is **not currently available for public download or general use**.

Development builds are currently restricted to authorized maintainers of the **Leviathan project portfolio**.

There are no official public beta builds or public release packages at this time.

---

## Why is the GitHub repository public if the launcher is private?

The repository is public for:

- Project information
- Documentation
- Development transparency
- Security and licensing information
- Microsoft / Mojang review
- Future project organization

A public repository does **not** mean that public launcher builds are currently available.

Public visibility also does not make Leviathan Launcher open-source software.

See [LICENSE](../LICENSE) for the complete licensing terms.

---

## Is Leviathan Launcher open source?

No.

Leviathan Launcher is **proprietary software**.

The project is publicly documented, but public visibility does not grant permission to copy, redistribute, modify, repackage, sell, sublicense, or commercially exploit original Leviathan Launcher materials.

See the [LICENSE](../LICENSE) file for details.

---

## Is Leviathan Launcher free?

No public release currently exists, so final release and pricing details have not been announced.

Any future pricing, free features, optional cosmetics, or other commercial features will be documented before public release.

---

## Does Leviathan Launcher require a legitimate Minecraft account?

Yes.

Leviathan Launcher is intended for users who legitimately own or otherwise have valid access to **Minecraft: Java Edition**.

The launcher is designed to verify Minecraft ownership or entitlement through Minecraft Services.

---

## Does Leviathan Launcher support cracked accounts?

No.

Leviathan Launcher does not provide or support:

- Cracked authentication
- Ownership bypasses
- License bypasses
- Authentication bypasses
- Account impersonation
- Unauthorized account access
- Circumvention of Microsoft or Mojang security systems

---

## How does Microsoft login work?

Leviathan Launcher uses Microsoft's official authentication infrastructure.

The intended authentication chain is:

1. Microsoft authentication
2. Xbox Live authentication
3. Xbox Security Token Service (XSTS)
4. Minecraft Services authentication
5. Minecraft ownership verification
6. Minecraft profile retrieval

See [AUTHENTICATION.md](AUTHENTICATION.md) for a more detailed technical overview.

---

## Does Leviathan Launcher see my Microsoft password?

No.

Users authenticate through Microsoft's own authentication system.

Leviathan Launcher is not designed to ask for, receive, or store Microsoft account passwords directly.

---

## Does Leviathan Launcher use a Microsoft client secret?

No confidential client secret is embedded in the desktop launcher.

Leviathan Launcher uses a Microsoft Entra application configured as a **public desktop client**.

The Microsoft Application (Client) ID is an identifier and is not a secret.

---

## What is the Minecraft AppID approval?

Third-party launcher applications may require approval before Minecraft Services accepts their Microsoft application registration for the required authentication APIs.

Leviathan Launcher's Minecraft AppID review has been approved. Approval does not establish that production authentication is fully enabled or that public builds are available.

Current status:

- [x] Microsoft Entra application registered
- [x] Public desktop client configuration enabled
- [x] Microsoft authentication integrated
- [x] Xbox Live authentication integrated
- [x] XSTS authentication integrated
- [x] Minecraft Services integration implemented
- [x] Submit AppID review request
- [x] AppID approval received

---

## Why can Microsoft login work while Minecraft login fails?

Microsoft account authentication and Minecraft Services authorization are separate stages.

A Microsoft sign-in can succeed while Minecraft Services still rejects the application if its AppID has not yet been approved for the required Minecraft APIs.

---

## Is Leviathan Launcher affiliated with Mojang or Microsoft?

No.

Leviathan Launcher is an **independent third-party project**.

It is not affiliated with, sponsored by, endorsed by, operated by, or officially associated with Microsoft Corporation, Mojang Studios, Xbox, or Minecraft unless explicitly stated otherwise by the relevant rights holder.

---

## Who develops Leviathan Launcher?

Leviathan Launcher is currently developed and maintained as part of the **Leviathan project portfolio**.

---

## Can I contribute code?

Not currently, unless explicitly authorized by the developer.

Leviathan Launcher is still in private development and external contributions are not currently being accepted by default.

This policy may change in the future.

---

## Can I fork the repository?

GitHub may technically allow users to fork public repositories, but the Leviathan Launcher proprietary license does not grant general permission to redistribute, modify, repackage, or publish derivative versions of Leviathan Launcher.

See [LICENSE](../LICENSE) for the complete terms.

---

## Can I use the Leviathan Launcher Microsoft AppID in my own launcher?

No.

The Leviathan Launcher Microsoft Entra application registration and associated AppID are intended specifically for Leviathan Launcher.

Developers of other launchers should create and obtain approval for their own Microsoft application registration.

---

## Where are authentication tokens stored?

Authentication handling is still under development.

Tokens are treated as sensitive information and should not be committed to the repository, printed in public logs, or exposed in screenshots.

Before a public release, storage and session handling may be further hardened and documented.

See:

- [PRIVACY.md](../PRIVACY.md)
- [SECURITY.md](../SECURITY.md)
- [AUTHENTICATION.md](AUTHENTICATION.md)

---

## Does Leviathan Launcher collect analytics?

There is currently no public Leviathan Launcher telemetry or analytics program.

If telemetry, crash reporting, or analytics are introduced later, the project's privacy documentation should be updated before or alongside those features.

---

## Does Leviathan Launcher contain ads?

No public release currently exists, and no final decision about future monetization or advertising has been announced.

Any future monetization features will be documented before they are introduced.

---

## Will Leviathan Launcher have cosmetics?

Cosmetics are part of the planned launcher feature set.

Details may change significantly during development.

Any cosmetics system will remain separate from Minecraft ownership requirements and must not be used to bypass Minecraft authentication or licensing.

---

## Will Leviathan Launcher have profiles?

Multiple launcher profiles are planned.

Profiles may eventually allow different combinations of:

- Minecraft versions
- Mod loaders
- Java versions
- Memory settings
- JVM arguments
- Game arguments
- Mods
- Resource packs
- Shaders
- Other launcher settings

---

## Will Leviathan Launcher support mods?

Mod and content integration is planned.

The project may integrate with third-party services such as Modrinth.

Mods, modpacks, resource packs, shaders, and other community content remain subject to their creators' licenses and terms.

See [THIRD_PARTY_NOTICES.md](../THIRD_PARTY_NOTICES.md).

---

## How do I report a security issue?

Please read [SECURITY.md](../SECURITY.md).

Do not post passwords, access tokens, refresh tokens, session cookies, private keys, client secrets, or other sensitive credentials in public GitHub issues.

---

## How do I report a normal bug?

Public bug reporting may be enabled when testing becomes available.

The repository includes a bug-report template under:

`.github/ISSUE_TEMPLATE/bug_report.md`

Security-sensitive issues should follow [SECURITY.md](../SECURITY.md) instead.

---

## Where can I see development progress?

See:

- [README](../README.md)
- [CHANGELOG](../CHANGELOG.md)
- [ARCHITECTURE](ARCHITECTURE.md)
- [AUTHENTICATION](AUTHENTICATION.md)

The public repository is:

https://github.com/Lapinite/Leviathan-Launcher

---

## When will Leviathan Launcher release?

There is no announced public release date.

The project is still in private development and several systems remain under development or review.

A public release should happen only when the launcher is considered ready.

---

## Can I download a build from somewhere else?

There are currently **no official public builds**.

Any website, account, or download claiming to distribute an official public Leviathan Launcher build during the current private-development stage should be treated with caution.

Official project information is published through:

https://github.com/Lapinite/Leviathan-Launcher

---

## Where can I read the project policies?

- [License](../LICENSE)
- [Privacy Policy](../PRIVACY.md)
- [Security Policy](../SECURITY.md)
- [Third-Party Notices](../THIRD_PARTY_NOTICES.md)
- [Authentication Architecture](AUTHENTICATION.md)
- [Architecture](ARCHITECTURE.md)
- [Changelog](../CHANGELOG.md)

---

## Contact

**Project:** Leviathan project portfolio  
**Repository:** https://github.com/Lapinite/Leviathan-Launcher

Additional contact and support methods may be added before public release.

---

**Leviathan Launcher**  
Private Development  
Copyright © 2026 Leviathan project owner. All Rights Reserved.
