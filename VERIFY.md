# Verify ModMyFeed Yourself

ModMyFeed is intentionally built so a skeptical user can inspect the trust claims without taking them on faith.

## 1. Inspect permissions

Open `manifest.json`.

The only extension permission should be:

```json
"permissions": ["storage"]
```

The only content-script match should be:

```text
https://www.reddit.com/*
```

There should be no background service worker, broad host permission, or externally-connectable configuration.

## 2. Search for network / telemetry primitives

Inspect the exact source package in `dist/` and search the runtime source under `src/` for network/telemetry primitives such as:

```text
fetch(
XMLHttpRequest
WebSocket
sendBeacon
google-analytics
segment
sentry
```

The automated test suite audits executable network/telemetry primitives.

## 3. Inspect dependencies

There are no third-party runtime JavaScript dependencies. The extension ships as readable source files rather than an opaque minified bundle.

## 4. Inspect what is stored

Open Chrome DevTools for the extension and inspect `chrome.storage.local`. Stored state is moderation data, enabled presets, small local settings such as onboarding/schema version, plus the bounded `recentHidden` review list.

`recentHidden` contains titles/basic metadata only, is capped at 60 items, and is pruned after 7 days.

## 5. Run automated checks

From the complete alpha source package:

```bash
npm test
```

For alpha 0.9.2, **47 tests** should pass.

## 6. Load the exact source yourself

Download `dist/modmyfeed-0.9.2-alpha.zip`, extract it, inspect it, then use Chrome Developer Mode → **Load unpacked** and point Chrome at the extracted folder containing `manifest.json`.

## Support link verification

The optional support link is a plain user-clicked `https://buymeacoffee.com/malcolmb` anchor in `src/popup/popup.html`. It does not use `fetch`, XHR, WebSocket, beacon, background scripts, or additional Chrome permissions. The link is configured with `rel="noopener noreferrer"` and `referrerpolicy="no-referrer"`.

## What would violate the current trust model?

Examples worth reporting include an unexpected background network request, access to a website other than Reddit, storage of data not described in `PRIVACY.md`, imported data executing code, a newly-added broad Chrome permission without clear necessity, or Reddit content being sent to an external service.
