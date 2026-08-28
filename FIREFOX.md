# Firefox alpha

This is the Firefox desktop port of ModMyFeed 0.9.2.

## What changed from the Chromium build

The runtime JavaScript is the same. Firefox supports the callback-style `chrome.*` WebExtension APIs used by ModMyFeed.

The Firefox manifest adds:

- a stable Gecko add-on ID: `modmyfeed@malcolm9519.github`;
- Mozilla's required data-collection declaration: `required: ["none"]`;
- explicit toolbar action icons.

No new runtime permissions, servers, analytics, or network requests were added.

## Temporary local test in Firefox

1. Open `about:debugging#/runtime/this-firefox`.
2. Click **Load Temporary Add-on**.
3. Select the Firefox build's `manifest.json`.
4. Open or refresh `https://www.reddit.com/`.
5. Test the popup, Mute button, presets, Recently Hidden, and temporary mutes.

Temporary add-ons are removed when Firefox restarts. This flow is only for testing before the AMO-signed build is published.

## AMO submission package

Use `modmyfeed-firefox-0.9.2-amo.zip` for addons.mozilla.org. Its `manifest.json` is at the ZIP root.
