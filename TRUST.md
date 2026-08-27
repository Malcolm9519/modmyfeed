# ModMyFeed Trust Architecture

ModMyFeed modifies a page that can contain highly personal browsing interests, so trust is treated as a product requirement rather than a privacy-policy footnote.

## Core trust rule

**Browsing/feed data should not need to leave the browser for ModMyFeed's core functionality to work.**

## Data flow

```text
Reddit page already rendered in your browser
                |
                v
      ModMyFeed content script
                |
       local rule evaluation
          /             \
         v               v
hide/collapse post   show post normally
         |
         v
small local review record
(title + basic metadata only)

chrome.storage.local
  - your mutes
  - enabled presets
  - expiration/scope
  - recent-hidden metadata
```

There is no ModMyFeed server in this flow.

## Chrome access

`manifest.json` requests only the `storage` extension permission. The content script is limited to `https://www.reddit.com/*`.

ModMyFeed does not request browser history, cookies, identity, downloads, clipboard access, webRequest, or `<all_urls>`.

## Network behavior

The runtime contains no `fetch`, XMLHttpRequest, WebSocket, or beacon pipeline for extension data.

The popup contains normal user-clicked links to the public GitHub source repository and Buy Me a Coffee. Those links are navigation only. The extension does not contact either destination in the background.

## Recently Hidden

To make filtering auditable, ModMyFeed keeps a short local history of hidden items. It stores title + basic post metadata, does not store post body text in review history, caps the list at 60 entries, prunes entries older than 7 days, and lets the user clear it manually.

## Presets

Built-in presets are ordinary inspectable local rules. They are not remote classifiers and do not upload posts for analysis. Imported preset JSON is validated as data before storage and cannot inject executable code or downloaded regex behavior.

## Dependency policy

The current runtime has no third-party JavaScript dependencies. Keeping the runtime small and readable is intentional: it reduces supply-chain risk and the amount of code a skeptical user has to audit.

## Future changes

A future feature that requires external processing, accounts, syncing, or feed uploads should be treated as a new trust/privacy decision. It should not silently change the guarantees of the local core product.
