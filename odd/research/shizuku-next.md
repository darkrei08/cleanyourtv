# Shizuku Next and ADB-wireless utility path

Status: research only. No APK was installed and no Chromecast setting was changed.

## Findings

- Official Shizuku is maintained at https://github.com/RikkaApps/Shizuku and documents wireless-debugging setup at https://shizuku.rikka.app/guide/setup/.
- The official setup requires Android 11 or newer, Wireless debugging, a pairing-code flow, and restarting the service after reboot in non-rooted setups.
- Shizuku-Next is a third-party fork at https://github.com/rushiranpise/Shizuku-Next with releases at https://github.com/rushiranpise/Shizuku-Next/releases. It is not the official upstream project and must be treated as a separate signed build until the exact release APK and signature are verified.
- Droid-ify is an F-Droid client, package com.looker.droidify: https://f-droid.org/en/packages/com.looker.droidify/.
- The official Shizuku package is distributed through IzzyOnDroid metadata at https://apt.izzysoft.de/fdroid/index/apk/moe.shizuku.privileged.api/; it is not assumed to be in the default F-Droid repository.

## Device-specific constraints

The target Chromecast is sabrina, Android 14 / SDK 34. Existing probe evidence shows Wireless debugging and ADB are dynamic across reboots. The official guide's notification-based pairing flow may not be practical on a TV without a notification shade; this must be verified on the actual device before selecting upstream Shizuku. A TV-specific fork may improve D-pad usability, but it carries third-party signing and maintenance risk.

## Safe next step

Before installing anything, choose one path:

1. Official RikkaApps/Shizuku, installed from a verified first-party or IzzyOnDroid APK, with pairing performed through the already-authorized host ADB path.
2. Third-party Shizuku-Next, only after verifying the exact release asset, SHA-256, package/signature behavior, and rollback path.

Do not install both variants: package/signature collisions can make an update incompatible. Droid-ify can be considered later as the store client, but it should be installed only after deciding which Shizuku variant is acceptable.

## Local device evidence

- probe-artifacts/probe.txt: Chromecast/sabrina, Android 14, SDK 34, firmware UTTC.250917.004.14193937.
- probe-artifacts/all-packages.txt: neither moe.shizuku.privileged.api nor com.looker.droidify was present in the prior inventory.

## Verification source URLs

- https://github.com/RikkaApps/Shizuku
- https://shizuku.rikka.app/guide/setup/
- https://github.com/rushiranpise/Shizuku-Next
- https://github.com/rushiranpise/Shizuku-Next/releases
- https://f-droid.org/en/packages/com.looker.droidify/
- https://apt.izzysoft.de/fdroid/index/apk/moe.shizuku.privileged.api/
