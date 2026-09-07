# Leviathan Launcher — Minecraft Compliance Policy

**Status:** Pre-release policy  
**Last updated:** 8 September 2026

This document records Leviathan's current compliance baseline for Minecraft-related functionality. It is an engineering and release-control policy, not a representation of endorsement by Mojang or Microsoft.

## 1. Independent branding

Leviathan must remain independently branded. It must not present itself as an official Minecraft, Mojang, Microsoft, or Xbox product.

Covered public surfaces should use the disclaimer:

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

## 2. Legitimate ownership

Leviathan is intended for legitimate Minecraft: Java Edition users.

The launcher must not bypass:

- Microsoft authentication;
- Minecraft ownership checks;
- entitlement checks;
- licensing controls;
- safety systems.

## 3. Game files

Leviathan must not unlawfully redistribute Minecraft game binaries or ship a pre-modded Minecraft game JAR as a Leviathan product.

Where the launcher installs game files, it should obtain authorized artifacts from appropriate official sources and keep independently distributed mods/components separate from Minecraft game binaries.

## 4. Mods and third-party content

Leviathan must respect the licenses and distribution terms of third-party mods, libraries, assets, mod loaders, resource packs, shaders, and other content.

A file being publicly downloadable does not automatically grant Leviathan redistribution rights.

## 5. Paid Minecraft-visible client features

Paid client-side features that unlock Minecraft-visible functionality, including paid client cosmetics, remain a release-policy blocker until Leviathan has sufficient legal and policy confidence that the specific implementation is allowed.

This applies even if payment occurs outside Minecraft and even if the entitlement is stored against a Minecraft profile identifier.

The implementation may be designed behind a disabled feature flag, but it must not be commercially released merely because the technical system exists.

## 6. Cape-like cosmetics

Paid cosmetics that visually function as Minecraft player capes require especially conservative review. Renaming a cape-like item does not by itself remove policy risk.

## 7. Premium

Any paid Premium feature that unlocks Minecraft-visible or in-game client functionality inherits the same compliance review requirement as other paid Minecraft-integrated features.

## 8. Marketplace

A marketplace for Minecraft-visible client cosmetics must remain disabled for commercial release while the underlying paid entitlement model is unresolved.

Independent platform marketplace architecture may still be developed where it does not create unauthorized Minecraft commercialization.

## 9. LeviCoins

LeviCoins, if introduced, are Leviathan platform credits and must not be represented as Minecoins or official Minecraft currency.

They should not support:

- cash-out;
- cryptocurrency conversion;
- external-value redemption;
- conversion back into gift cards;
- portable cross-server Minecraft currency behavior.

Creator real-money payouts, if later offered, should use a separate accounting/payout system rather than treating LeviCoins as cash.

## 10. Randomized monetization and minors

Paid randomized loot-box style mechanics are not part of the V1 compliance baseline.

Rotating or seasonal storefronts must not use fake countdowns, false scarcity, or misleading pressure tactics. Features likely to be used by minors require additional age, parental, consumer-protection, and safety review.

## 11. Purchases and recipient identity

Where a legally permitted Minecraft-related entitlement is delivered to a specific player, the stable Minecraft profile identifier should be authoritative and the username should be treated as display/lookup metadata.

Purchase provenance should preserve information necessary to establish the purchaser, original recipient, product, acquisition source, relevant transaction reference, timestamps, and refund/reversal/fraud state.

Linking another profile must not silently transfer ownership.

## 12. Refunds and consumer rights

Leviathan must not rely on a blanket “all sales final” statement where mandatory consumer rights apply. Digital-content withdrawal, immediate-performance consent, refunds, chargebacks, taxes, and trader-identification requirements require jurisdiction-appropriate implementation before public commerce.

## 13. Policy monitoring

Minecraft EULA, Usage Guidelines, and related Microsoft/Mojang policies can change. Compliance should be re-checked before major releases and before enabling commercial Minecraft-integrated features.

## 14. No inherited permission

Another launcher or client offering a similar feature does not prove that Leviathan has permission to offer it. Leviathan must rely on rules and permissions applicable to Leviathan itself.
