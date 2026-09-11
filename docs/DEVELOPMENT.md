# Leviathan Launcher Development Guide

**Project status:** Private Development  
**Project:** Leviathan project portfolio

This document describes the current development setup and intended development workflow for Leviathan Launcher.

The project is still evolving, so details may change.

---

## Development Environment

Recommended environment:

- **Operating system:** Windows 10 or Windows 11
- **Java:** JDK 21
- **Build system:** Gradle
- **Shell:** PowerShell
- **Version control:** Git
- **Repository hosting:** GitHub

---

## Java Version

Leviathan Launcher development currently targets **Java 21**.

Check your installed version:

```powershell
java -version
javac -version
```

Both should report Java 21.

If multiple Java versions are installed, ensure `JAVA_HOME` and your `PATH` point to the intended JDK when building Leviathan.

Example:

```powershell
$env:JAVA_HOME = "<JDK_INSTALL_DIRECTORY>"
$env:Path = (Join-Path $env:JAVA_HOME "bin") + ";" + $env:Path
```

The exact install path may differ.

---

## Repository Layout

The public documentation repository currently contains:

```text
Leviathan-Launcher/
├── .github/
├── docs/
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── NOTICE
├── PRIVACY.md
├── README.md
├── ROADMAP.md
├── SECURITY.md
├── SUPPORT.md
├── TERMS.md
├── THIRD_PARTY_NOTICES.md
└── TRADEMARKS.md
```

When the actual launcher source is added, the repository may also include:

```text
src/
gradle/
gradlew
gradlew.bat
build.gradle
settings.gradle
```

or equivalent Gradle Kotlin DSL files.

---

## Cloning the Repository

When source code is available:

```powershell
git clone https://github.com/Lapinite/Leviathan-Launcher.git
cd Leviathan-Launcher
```

---

## Building

If the Gradle wrapper exists:

```powershell
.\gradlew.bat build
```

If the project uses a custom build script:

```powershell
powershell -ExecutionPolicy Bypass -File .\build.ps1
```

If neither exists yet, follow the current project-specific build instructions.

---

## Running

Development launch commands may vary as the project evolves.

Typical options may include:

```powershell
.\gradlew.bat run
```

or:

```powershell
.\Leviathan.bat ui
```

or:

```powershell
powershell -ExecutionPolicy Bypass -File .\build.ps1 -Run -Arguments "ui"
```

Use the command supported by the current branch.

---

## Branching Workflow

The `main` branch is protected.

For normal changes:

1. Create a branch.
2. Make your changes.
3. Commit the changes.
4. Push the branch.
5. Open a Pull Request into `main`.
6. Resolve any checks or review comments.
7. Merge the Pull Request.

Example:

```powershell
git switch -c feature/example-change
```

Then:

```powershell
git add .
git commit -m "Add example change"
git push -u origin feature/example-change
```

---

## Branch Naming

Suggested branch prefixes:

```text
feature/
fix/
docs/
refactor/
security/
build/
chore/
```

Examples:

```text
feature/account-switcher
fix/microsoft-login-error
docs/authentication-update
security/token-storage
build/gradle-update
```

---

## Commit Messages

Prefer concise, descriptive commit messages.

Examples:

```text
Add Microsoft authentication flow
Fix XSTS error handling
Update README authentication section
Add launcher profile validation
Improve download retry logic
```

Avoid vague messages such as:

```text
stuff
update
fix
changes
```

---

## Authentication Development

Authentication involves:

1. Microsoft authentication
2. Xbox Live authentication
3. XSTS authentication
4. Minecraft Services authentication
5. Ownership verification
6. Minecraft profile retrieval

See:

[AUTHENTICATION.md](AUTHENTICATION.md)

Never commit:

- Access tokens
- Refresh tokens
- Session cookies
- Client secrets
- Private keys
- Personal Microsoft account data

---

## Microsoft Client ID

Application identifiers are distinct from confidential secrets. Leviathan's actual application, tenant, and object identifiers must nevertheless remain out of this public repository.

However:

- Client secrets must never be committed.
- Private keys must never be committed.
- User authentication tokens must never be committed.
- Session files must remain ignored.

---

## Local Development Data

Local development files may include:

- Cache
- Logs
- Runtime downloads
- Account sessions
- Launcher settings
- Test profiles
- Temporary files

These should not normally be committed.

Check `.gitignore` before adding new runtime-generated files.

---

## Dependencies

Before adding a dependency:

1. Confirm it is actively maintained.
2. Review its license.
3. Check for known security issues.
4. Prefer trusted repositories.
5. Avoid unnecessary dependencies.
6. Add required notices to `THIRD_PARTY_NOTICES.md`.

---

## Third-Party Licenses

Leviathan Launcher is proprietary software, but third-party components keep their own licenses.

Do not remove legally required notices or attribution.

See:

[THIRD_PARTY_NOTICES.md](../THIRD_PARTY_NOTICES.md)

---

## Security Guidelines

Development should aim to:

- Avoid logging secrets.
- Validate external input.
- Validate downloaded files where practical.
- Use HTTPS for external requests.
- Handle path operations safely.
- Avoid command injection.
- Avoid arbitrary file writes.
- Treat remote metadata as untrusted input.
- Minimize token exposure.
- Keep dependencies updated.

See:

[SECURITY.md](../SECURITY.md)

---

## Logging

Logs should be useful without exposing credentials.

Safe information may include:

- Error codes
- HTTP status codes
- Trace IDs
- Correlation IDs
- Version information
- Java version
- Operating system
- Stack traces without secrets

Never intentionally log:

- Full access tokens
- Refresh tokens
- Authorization headers
- Passwords
- Client secrets
- Private keys

---

## Error Handling

Prefer user-friendly error messages.

Example:

```text
Microsoft authentication failed.
Please sign in again.
```

Rather than exposing internal credentials or raw sensitive payloads.

For development logs, include enough technical context to diagnose the problem safely.

---

## Testing

Before merging a change, test relevant functionality.

Examples:

- Launcher startup
- Microsoft login
- Xbox Live authentication
- XSTS authentication
- Minecraft ownership verification
- Profile retrieval
- Downloading
- Version installation
- Java detection
- Game launch
- Settings persistence
- Logout
- Error handling

---

## GitHub Actions

The repository includes a build workflow under:

```text
.github/workflows/build.yml
```

When project source and Gradle configuration are present, GitHub Actions should build the project automatically.

Build failures should be investigated before merging changes into `main`.

---

## Dependabot

Dependency update configuration is stored in:

```text
.github/dependabot.yml
```

Dependabot may open Pull Requests for supported dependency updates.

Review updates before merging them, especially major-version changes.

---

## Code Ownership

Code ownership is defined in:

```text
.github/CODEOWNERS
```

CODEOWNERS uses the repository maintainer account required by GitHub for automatic review requests.

---

## Documentation Updates

Update documentation when behavior changes.

Relevant files may include:

- README
- CHANGELOG
- ROADMAP
- AUTHENTICATION
- ARCHITECTURE
- FAQ
- TROUBLESHOOTING
- PRIVACY
- SECURITY
- THIRD_PARTY_NOTICES

---

## Release Preparation

Before any public release, review:

- Authentication
- Approved application configuration and applicable service requirements
- Security
- Token storage
- Privacy policy
- Terms
- Third-party licenses
- Dependency vulnerabilities
- Installer security
- Update security
- Download verification
- Code signing
- Crash/log privacy

See:

[RELEASE_POLICY.md](RELEASE_POLICY.md)

---

## Proprietary Project

Public source visibility does not automatically grant permission to reuse or redistribute Leviathan Launcher.

See:

[LICENSE](../LICENSE)

---

## Contact

**Project:** Leviathan project portfolio  
**Repository:** https://github.com/Lapinite/Leviathan-Launcher

---

**Leviathan Launcher**  
Development Guide  
Copyright © 2026 Leviathan project owner. All Rights Reserved.
