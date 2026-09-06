# Contributing to Leviathan Launcher

**Project status:** Private Development

Thank you for your interest in Leviathan Launcher.

Leviathan Launcher is currently a privately developed proprietary project maintained by **Danni**. External contributions are not currently accepted by default.

---

## Current Contribution Policy

At this stage:

- Unsolicited code contributions may be declined.
- Pull requests should only be opened when explicitly invited or approved by the developer.
- Feature suggestions and bug reports may be considered when public issue tracking is enabled.
- Security vulnerabilities should follow [SECURITY.md](SECURITY.md), not public issue threads.
- Public visibility of the repository does not make Leviathan Launcher open-source software.

See [LICENSE](LICENSE) for the complete licensing terms.

---

## Before Contributing

If you have been invited to contribute, please:

1. Discuss the proposed change with the developer first.
2. Keep the change focused and limited in scope.
3. Follow the existing project structure and coding conventions.
4. Do not commit secrets, tokens, passwords, private keys, or personal data.
5. Test the change before submitting it.
6. Update documentation where necessary.
7. Include third-party license information for any newly introduced dependency.

---

## Pull Requests

Approved pull requests should include:

- A clear title
- A short explanation of the change
- Why the change is needed
- Testing performed
- Any known limitations
- Any dependency or licensing changes

Large unrelated changes should not be bundled into one pull request.

---

## Security-Sensitive Changes

Changes involving any of the following require extra care:

- Microsoft authentication
- Xbox Live authentication
- XSTS authentication
- Minecraft Services
- Token handling
- Session storage
- Launcher updates
- Download verification
- File-system operations
- External process launching
- Remote content
- Secrets or credentials

Never include real access tokens, refresh tokens, session cookies, client secrets, private keys, or passwords in commits, issues, examples, or screenshots.

---

## Dependencies

Any newly added third-party dependency should include:

- Project name
- Version
- License
- Project URL
- Required attribution or notices

Update [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) when appropriate.

---

## Ownership and Licensing of Contributions

Unless a separate written agreement states otherwise, accepting a contribution does not change the proprietary status of Leviathan Launcher.

Before external contributions are accepted publicly, the project may introduce a formal contributor license agreement or contribution terms.

---

## Coding Standards

Project-specific coding standards may evolve during development.

General expectations:

- Prefer clear, maintainable code
- Avoid unnecessary complexity
- Handle errors explicitly
- Avoid leaking sensitive information into logs
- Keep authentication logic isolated where practical
- Document non-obvious behavior
- Preserve compatibility with supported Java versions

---

## Documentation

Documentation changes should remain consistent with:

- [README.md](README.md)
- [PRIVACY.md](PRIVACY.md)
- [SECURITY.md](SECURITY.md)
- [TERMS.md](TERMS.md)
- [LICENSE](LICENSE)

---

## Contact

**Developer:** Danni  
**GitHub:** https://github.com/Lapinite  
**Repository:** https://github.com/Lapinite/Leviathan-Launcher

---

**Leviathan Launcher**  
Copyright © 2026 Danni. All Rights Reserved.
