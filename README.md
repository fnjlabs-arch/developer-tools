# SadSha DevTools

A browser for Android with built-in Chrome DevTools. Built for developers who code on Android.

## What this is

An Android browser that gives you real Chrome DevTools — Elements, Console, Network, Sources, Performance, Lighthouse, and everything else — running entirely on your phone. No laptop required.

## Why

Android can run a terminal. It can run code editors and dev servers. But it can't do desktop browsing with developer tools. This is that missing piece.

## How it works

Two WebViews: one is your browser, the other runs the real Chrome DevTools frontend (built from Chromium source). A local TCP proxy bridges them via the Chrome DevTools Protocol. No root, no ADB, no external device needed.

## Features

- Full Chrome DevTools — Elements, Console, Network, Sources, Performance, Application, Lighthouse
- Inspect and edit HTML/CSS in real time
- Debug JavaScript with the Console
- Monitor network requests
- Desktop and mobile user-agent modes
- Multiple tabs
- Find in page
- Dock DevTools to bottom or right
- Runs on Android 7.0+ (minSdk 24)

## Build

```
# First time: build the DevTools frontend from Chromium source
./scripts/copy-devtools.sh

# Build the APK
./gradlew assembleDebug

# Output: app/build/outputs/apk/debug/app-debug.apk
```

Requires JDK 17 and Android SDK (API 35). The DevTools frontend ships pre-built in `app/src/main/assets/devtools_frontend/`; rebuild it only if you change the Chromium DevTools source (see `./scripts/fetch-devtools-frontend.sh`).

## License

MIT. See [NOTICE](NOTICE) for third-party licenses (Chromium DevTools, NanoHTTPD, AndroidX).

## Credits

Originally "Developer Tools Browser" by Unix Shells (Mark Karpeles), MIT-licensed. Rebranded and maintained as SadSha DevTools by SadSha, with the original license and attribution kept intact.
