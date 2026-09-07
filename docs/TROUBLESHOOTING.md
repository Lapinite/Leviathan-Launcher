# Leviathan Launcher Troubleshooting

**Project status:** Private Development

This document collects common troubleshooting steps for Leviathan Launcher.

Because Leviathan Launcher is still in private development, some errors may be caused by incomplete features, changing APIs, or development-only configuration.

---

## Before Troubleshooting

Before making changes, check:

- You are using the latest private development build available to you.
- Your internet connection is working.
- Microsoft, Xbox, and Minecraft services are available.
- Your Microsoft account legitimately owns or has access to Minecraft: Java Edition.
- Your Java installation matches the version required by the launcher or selected Minecraft version.
- Your system clock and timezone are correct.
- Antivirus or firewall software is not blocking the launcher unexpectedly.

---

## Microsoft Sign-In Does Not Open

Possible causes:

- Browser launch failed
- Default browser is misconfigured
- Microsoft authentication endpoint could not be reached
- Local system policy blocked the browser

Try:

1. Confirm your default browser works normally.
2. Restart Leviathan Launcher.
3. Restart Windows.
4. Check firewall or security software.
5. Confirm `login.microsoftonline.com` is reachable in your browser.

---

## Microsoft Sign-In Fails With AADSTS Errors

Microsoft authentication errors often include a code beginning with `AADSTS`.

Examples may include:

- `AADSTS50058`
- `AADSTS70002`
- `AADSTS7000218`

General steps:

1. Read the full error message.
2. Copy the error code, trace ID, correlation ID, and timestamp.
3. Do not post access tokens or cookies publicly.
4. Confirm the Leviathan Microsoft Entra app is configured correctly.
5. Confirm the app is configured as a public desktop client.
6. Confirm public client flows are enabled where required.
7. Restart the launcher and try again.

---

## Error: Client Must Be Marked as Mobile / Public Client

If Microsoft returns an error saying the client is not supported or must be marked as mobile/public:

- Confirm the Microsoft Entra application has a **Mobile and desktop applications** platform.
- Confirm public client flows are enabled.
- Confirm the app registration being used matches Leviathan Launcher's Client ID.

This is an Entra application-configuration issue, not a Minecraft ownership issue.

---

## Microsoft Login Works but Minecraft Services Rejects the Request

A Microsoft login can succeed while Minecraft Services still refuses authentication.

Possible causes include:

- The Leviathan AppID has not yet been approved by Mojang Studios.
- Minecraft Services is temporarily unavailable.
- Xbox/XSTS authentication failed earlier in the chain.
- The authenticated account does not have valid Minecraft access.

If the error states that the Microsoft application is not authorized or approved, the issue may be AppID approval rather than launcher code.

---

## Minecraft AppID Approval Pending

Leviathan Launcher's AppID review submission is currently pending.

While approval is pending:

- Microsoft authentication may succeed.
- Xbox authentication may succeed.
- XSTS authentication may succeed.
- Minecraft Services may still reject the application.

After submission, do not repeatedly resubmit the same AppID unless Microsoft/Minecraft requests it.

---

## Minecraft Ownership Verification Fails

Possible causes:

- The Microsoft account does not own Minecraft: Java Edition.
- The wrong Microsoft account was used.
- Minecraft entitlement services are unavailable.
- Authentication tokens expired.
- The AppID is not yet approved.

Try signing out and signing in with the Microsoft account that owns Minecraft.

---

## XSTS Authentication Fails

XSTS failures can occur for several reasons.

Possible causes:

- Xbox profile setup is incomplete.
- Account age or family restrictions apply.
- Xbox services are unavailable.
- The Xbox token is invalid or expired.
- Region/account configuration is incomplete.

Keep the exact XSTS error code for diagnosis, but never post full tokens.

---

## Launcher Does Not Start

Try:

1. Open PowerShell.
2. Confirm Java is installed:

```powershell
java -version
```

3. Confirm the project uses the expected Java version.
4. Try launching from PowerShell so the error remains visible.
5. Check launcher logs.

---

## Java Not Found

If PowerShell says `java` is not recognized, install a supported JDK.

Leviathan Launcher development currently targets **Java 21**.

After installing Java:

1. Close PowerShell.
2. Open a new PowerShell window.
3. Run:

```powershell
java -version
```

Confirm Java 21 is shown.

---

## Wrong Java Version

Different Minecraft versions may require different Java versions.

The launcher itself may use Java 21 while specific Minecraft versions require another runtime.

Future Leviathan versions may manage this automatically.

If launching manually, confirm the selected runtime matches the Minecraft version requirements.

---

## Gradle Build Fails

Try:

```powershell
.\gradlew.bat build
```

If the Gradle wrapper is not present:

```powershell
gradle build
```

Common causes:

- Wrong Java version
- Missing dependency
- Network failure
- Broken Gradle cache
- Syntax or compile error

To refresh dependencies:

```powershell
.\gradlew.bat build --refresh-dependencies
```

---

## Build Script Will Not Run in PowerShell

If PowerShell blocks a script:

```powershell
Set-ExecutionPolicy -Scope Process Bypass
```

Then rerun the script.

This only changes execution policy for the current PowerShell process.

---

## Launcher Is Already Running

If an old Java process is still running:

```powershell
Get-CimInstance Win32_Process -Filter "Name='java.exe' OR Name='javaw.exe'" |
  Where-Object { $_.CommandLine -like "*leviathan*" } |
  ForEach-Object { Stop-Process -Id $_.ProcessId -Force }
```

Then restart Leviathan Launcher.

---

## Download Fails

Possible causes:

- Network outage
- Remote service unavailable
- Firewall/antivirus interference
- Invalid URL
- Permission error
- Disk is full
- Corrupt cache

Try:

1. Check internet connectivity.
2. Confirm free disk space.
3. Retry the download.
4. Restart the launcher.
5. Clear only the relevant cache if the launcher provides a safe cache-cleaning option.

Avoid deleting account/session data unless necessary.

---

## Corrupt Minecraft Files

Future Leviathan builds may include repair functionality.

Typical repair steps may include:

- Re-download missing libraries
- Re-download assets
- Re-download version metadata
- Re-download the client JAR
- Verify file hashes
- Restore native libraries

Do not delete personal worlds or screenshots during repair.

---

## Game Launches and Immediately Closes

Possible causes:

- Wrong Java version
- Invalid JVM arguments
- Missing libraries
- Missing natives
- Mod incompatibility
- Insufficient memory
- Corrupt Minecraft files

Check the latest game log or crash report.

---

## Mods Cause Crashes

Try:

1. Disable recently added mods.
2. Confirm all mods match the selected Minecraft version.
3. Confirm all mods match the correct mod loader.
4. Check dependency requirements.
5. Add mods back gradually until the failing mod is identified.

Third-party mods are not controlled by Leviathan Launcher.

---

## Discord Rich Presence Does Not Work

Possible causes:

- Discord is not running.
- Rich Presence is disabled.
- Discord IPC is unavailable.
- The launcher integration is still incomplete.

Restart Discord and Leviathan Launcher.

---

## Antivirus Flags the Launcher

Pre-release or unsigned software may sometimes trigger antivirus or Windows SmartScreen warnings.

Do not automatically disable antivirus.

Before public release, Leviathan should use trusted distribution methods, checksums, and potentially code signing.

Only run builds obtained from a trusted Leviathan source.

---

## Logs

Logs can help diagnose:

- Authentication failures
- Download failures
- Java errors
- Launch errors
- API errors
- Internal exceptions

Before sharing a log, check that it does not contain:

- Access tokens
- Refresh tokens
- Session cookies
- Private keys
- Client secrets
- Personal data

Sensitive information should be removed before posting publicly.

---

## Where to Report Issues

Public support is not currently available because Leviathan Launcher is still in private development.

See:

- [SECURITY.md](../SECURITY.md)
- [SUPPORT.md](../SUPPORT.md)
- [FAQ.md](FAQ.md)

---

## Security Issues

Do not post security-sensitive vulnerabilities publicly.

Follow [SECURITY.md](../SECURITY.md).

---

**Leviathan Launcher**  
Troubleshooting Guide  
Copyright © 2026 Leviathan project owner. All Rights Reserved.
