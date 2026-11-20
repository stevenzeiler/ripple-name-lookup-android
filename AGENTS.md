# AGENTS.md

Guidance for AI agents working in this repo. Humans: see [README.md](README.md).

## What this is

A dormant 2014 Android experiment (profile: `legacy`, baseline tier): Ripple name lookup plus a QR screen. See [docs/STATUS.md](docs/STATUS.md).

## Stack

- Java, Android. `compileSdkVersion 19`, build tools `19.0.1`, `minSdkVersion 7`.
- Android Gradle plugin `0.7.+`, Gradle wrapper 1.9 (`gradle/wrapper/gradle-wrapper.properties`).
- Libraries: `appcompat-v7`, `android-async-http` 1.4.5, `OnBarcode.AndroidBarcode.jar` (bundled).

## Layout

- `build.gradle`, `gradle/`, `gradlew`: top-level build.
- `rpple checkout/`: the app module. Note the directory name has a typo and a space. Sources are under `src/main/java/com/ripplecheckout/`, with `build.xml`, `project.properties` and a `bin/` folder, which look like leftovers of an older Ant/Eclipse layout **(inference)**.
- `.idea/`, `RippleCheckout.iml`: committed IDE files.
- `rpple checkout/rpple checkout.apk`: committed 2014 build.

## Commands

- Install and build: `./gradlew assembleDebug`. Known not to work on today's toolchain: the Gradle plugin and wrapper are far too old, and there is no Android SDK in a typical agent environment. Nothing was built in the audit.
- Test: there are no tests.
- Run: install on a device or emulator through Android Studio.

## Rules

- Add tests with every code change.
- Never commit secrets (keystores, API keys, `local.properties` with credentials).
- Use Conventional Commits.
- Keep `docs/STATUS.md` current.

## What agents may and may not do

- May: fix docs, add the missing baseline files, open pull requests.
- May not, without Steven: archive or delete the repo, publish anything, rewrite git history, add a license, delete the committed APK or jar, or merge their own pull requests.
