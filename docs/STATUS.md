# Status

Last reviewed: 2026-11-20 (github-audit pass 02, from the files and git log; nothing was built or run).

## What works

- The code reads as complete for its tiny scope: a lookup screen and a QR screen.
- **(inference)** The 2014 APK probably still installs on an old device. Not checked.

## What's broken or unknown

- It is unknown whether the app builds. The Gradle plugin (`0.7.+`), wrapper (Gradle 1.9) and SDK 19 settings are from 2014.
- Whether `id.ripple.com/v1/authinfo` still answers is unknown. The app also uses the Apache HTTP classes, which current Android no longer ships by default.
- The QR code shows hard-coded vendor sample data, not the looked-up Ripple address.
- `AndroidBarcodeView.java` is about 1,400 lines of vendor demo code, mostly dead (only the QR sample is called).
- `QrCodeFragment` has a leftover back-button wiring and a commented-out return.
- `rpple checkout/src/main/java/com/ripplecheckout/hyperspace_jump` is an empty file.
- Committed build and IDE leftovers: `.idea/`, `RippleCheckout.iml`, `rpple checkout/src/main/bin/`, `local.properties` (a local SDK path), a 2014 APK and the OnBarcode jar. The directory name `rpple checkout` has a typo and a space.
- The OnBarcode jar is third-party code, and its license terms are unknown.
- No license is declared.

## What's next

Nothing is planned. If revived: move to a current Android Gradle plugin, replace the Apache HTTP client, use the QR library only for the looked-up address, and decide whether Ripple names are still the right idea.

## Not yet from the standard

Remaining baseline items:

- LICENSE (Steven's decision: no license is declared today, so none was added; also check the bundled OnBarcode jar's terms)
- CONTRIBUTING.md
- SECURITY.md
- `.editorconfig`
- `.github` issue and pull request templates
- Dependabot configuration
- `ci.yml` with gitleaks
- Rename the default branch from `master` to `main`
- CloudEvents catalog
- Product ONE-PAGER

Added in this pass: README.md, AGENTS.md, CLAUDE.md, docs/STATUS.md.
