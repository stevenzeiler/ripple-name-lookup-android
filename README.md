# ripple-name-lookup-android

A small Android app that looks up a Ripple name and can show a QR code. The Android project is called **RippleCheckout** (package `com.ripplecheckout`).

> **Status: dormant since July 2014.** Written in one Saturday afternoon (2014-07-12) during Steven's Ripple Labs era, as a first sketch of a "scan to pay a Ripple name" idea. There are two commits and it was never finished. It uses a 2014 Android toolchain and has not been built or run in this review.

## What it does

1. **Name lookup.** You type a Ripple name and the app asks `https://id.ripple.com/v1/authinfo?username=<name>` and shows the `address` field from the JSON reply, or "No Address Found" or "Lookup Request Failed".
2. **QR screen.** A second screen draws a QR code with the OnBarcode Android library. The code encodes hard-coded sample data from the library's demo, not a Ripple address yet.

Whether the old `id.ripple.com` service still answers is unknown.

## Install and build

You need the Android SDK and an old toolchain, since the project targets 2014 tooling:

- Android Gradle plugin `0.7.+`, wrapper Gradle 1.9
- `compileSdkVersion 19`, build tools `19.0.1`, `minSdkVersion 7`
- Dependencies: `appcompat-v7`, `android-async-http` 1.4.5, and the bundled `OnBarcode.AndroidBarcode.jar` (in `rpple checkout/src/main/libs/`)

It was an Android Studio (early beta) project, so the simplest route is to open the repo folder in a current Android Studio and expect to migrate the Gradle files. A prebuilt `rpple checkout/rpple checkout.apk` is committed. It is an unverified 2014 binary, so install it only on a test device you do not mind.

## Usage

Launch the app, type a Ripple name, tap the lookup button, then tap the QR button to see the QR screen.

## Config

None. There are no environment variables or API keys. `rpple checkout/src/main/local.properties` holds only a local Android SDK path.

## How it works

- `MainActivity` hosts `HomeFragment`.
- `HomeFragment` does the name lookup with `android-async-http` and opens `QrCodeFragment`.
- `QrCodeFragment` shows an `AndroidBarcodeView`, which is the vendor's demo view (about 1,400 lines) trimmed to draw a QR code.

## Status

Dormant, unbuilt. See [docs/STATUS.md](docs/STATUS.md).

## License

No license has been declared. All rights reserved by default until Steven decides. The bundled OnBarcode jar is third-party software with its own terms.
