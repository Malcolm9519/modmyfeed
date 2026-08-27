# ModMyFeed Privacy Statement — Public Alpha

**Version:** 0.9.2

ModMyFeed is designed so that core Reddit feed moderation happens entirely inside your browser.

## Data sent automatically by the extension

None.

The extension contains no ModMyFeed backend client, analytics SDK, telemetry system, advertising SDK, `fetch` request, XMLHttpRequest, WebSocket, or beacon code for extension data.

## Data stored locally

ModMyFeed uses `chrome.storage.local` to store your moderation choices, such as muted words, subreddits, users, domains, flairs, optional expiration times, subreddit scope, enabled presets, and small extension settings such as whether first-run onboarding has been completed.

For **Recently hidden**, ModMyFeed keeps a small local history containing a hidden post's title, subreddit/author/domain/flair when available, Reddit permalink, the moderation choice that hid it, and the time it was hidden. It does **not** store the post body for review history. The list is capped at 60 items and entries older than 7 days are pruned when ModMyFeed runs. You can clear it manually at any time.

All of that data stays in the browser profile where the extension is installed.

## Reddit access

The content script runs only on:

`https://www.reddit.com/*`

It reads posts already rendered in your browser so it can apply your local moderation choices and add the Mute control. It does not call Reddit's API and does not upload post content anywhere.

## Chrome permissions

The manifest requests only:

- `storage`

It does not request browser history, cookies, identity, downloads, clipboard, webRequest, or `<all_urls>` access.

## Imports and exports

Import and export are local file operations initiated by the user. Imported preset JSON is validated as data. Imported presets cannot contain executable code or downloaded regex behavior. Recently-hidden review history is not included in personal-mute exports or moderation backups.

## Optional support and source links

The popup contains ordinary links to the public source repository and to Buy Me a Coffee. ModMyFeed does not contact either service automatically. A network request to one of those websites occurs only if you explicitly click the corresponding link.

Those links use `noopener`, `noreferrer`, and a no-referrer policy. ModMyFeed does not attach moderation settings, Reddit post data, or Recently Hidden history to those links.

## Future features

If a future feature would require sending browsing/feed data to an external service, that would be treated as a separate product and privacy decision rather than silently changing this local-only core behavior.
