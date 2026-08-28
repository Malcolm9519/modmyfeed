# ModMyFeed

**Your Reddit feed. Your rules.**

ModMyFeed is a free browser extension for Chrome and Firefox that lets you personally mute the parts of Reddit you do not want to see — without leaving communities you otherwise enjoy.

> No subscription. No ads. No analytics. No account. No ModMyFeed server.

## What it does

Mute Reddit posts by:

- **words / phrases**;
- **subreddit**;
- **user**;
- **domain**;
- **flair**.

Mutes can be temporary or permanent, and can be limited to one subreddit when that makes sense.

ModMyFeed also includes optional, inspectable presets for common clutter such as **Politics**, **AI / generative AI**, **Crypto / NFT**, self-promotion, engagement bait, referral spam, and meme/shitpost flairs.

Everything is reversible. Hidden posts can be shown once, mutes can be paused or removed, and **Recently hidden** gives you a local 7-day review window for false positives.

## Install the public alpha

### Chrome

ModMyFeed is currently distributed directly from this repository while the product is being validated.

1. Download [`dist/modmyfeed-0.9.2-alpha.zip`](dist/modmyfeed-0.9.2-alpha.zip).
2. Extract the ZIP.
3. Open `chrome://extensions` in Chrome.
4. Enable **Developer mode**.
5. Click **Load unpacked**.
6. Select the extracted ModMyFeed folder containing `manifest.json`.
7. Refresh Reddit.

Full instructions: [INSTALL.md](INSTALL.md)

> GitHub-installed Chrome extensions do **not** auto-update. For alpha releases, download the latest package and reload the extension when a new version ships.

### Firefox

A Firefox desktop port is being prepared for Mozilla Add-ons so Firefox users can install it normally and receive automatic updates. Until the signed listing is available, see [FIREFOX.md](FIREFOX.md) for temporary-install testing instructions.

## Trust at a glance

ModMyFeed is intentionally small and boring to audit.

| Question | Answer |
| --- | --- |
| Does ModMyFeed have an account system? | **No** |
| Does it have analytics or telemetry? | **No** |
| Does it send your Reddit feed to a server? | **No** |
| Does it call Reddit's API? | **No** |
| Does it use third-party runtime JavaScript? | **No** |
| Can it read every website you visit? | **No — Reddit only** |
| Browser extension permission requested | **`storage` only** |
| Where are your moderation choices stored? | **local extension storage** |
| Is the runtime source readable/unminified? | **Yes** |
| Can you inspect exactly what presets do? | **Yes** |

Read the full [privacy statement](PRIVACY.md), [trust architecture](TRUST.md), and [verification guide](VERIFY.md).

### Don't trust the claims — verify them

The extension is designed so a skeptical user can check the important claims quickly:

- unzip the alpha package and inspect `manifest.json`;
- search `src/` for network/telemetry primitives;
- inspect local extension storage in DevTools;
- load the exact source you inspected with browser developer tools.

The current alpha has **47 automated tests** covering the moderation engine, presets, data retention, migration, permissions, syntax, and a source-level no-network/no-telemetry audit. The alpha ZIP contains the complete readable runtime source plus the trust/privacy documents.

## What ModMyFeed is not

- It is **not** an ad blocker.
- It is **not** an AI moderation service.
- It does **not** decide what content is objectively good or bad.
- It does **not** moderate a subreddit for other people.

It gives **you** a moderation layer over **your** feed.

## Privacy and external links

Your moderation data stays local. The extension contains ordinary links to this source repository and to Buy Me a Coffee. Those sites are contacted only when you explicitly click a link; no Reddit content, mute settings, or Recently Hidden history is attached by ModMyFeed.

## Support development

ModMyFeed is free because the core product should not need an account, subscription, tracking SDK, or licensing server.

[☕ **If you like the idea, consider funding my caffeine addiction**](https://buymeacoffee.com/malcolmb)

## Feedback

This is a public alpha. Useful feedback includes:

- a post that should have been hidden but was not;
- a post that was hidden incorrectly;
- a Reddit page/layout where the Mute button breaks;
- a common kind of feed clutter that the existing controls cannot express cleanly;
- privacy/trust concerns;
- accessibility issues.

Please use [GitHub Issues](https://github.com/Malcolm9519/modmyfeed/issues).

## Current alpha

**0.9.2** — GitHub public-alpha polish, stronger support visibility, expanded trust/install documentation, and Firefox port preparation. No new moderation category was added.

## License

ModMyFeed is released under the [MIT License](LICENSE). You can use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software subject to the license terms.
