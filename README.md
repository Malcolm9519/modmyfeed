# ModMyFeed — Reddit Feed Moderation 0.9.1 Alpha

ModMyFeed is a small Chrome Manifest V3 extension that gives Reddit users a personal moderation layer over the feed they already use.

## Core idea

Reddit moderators decide what belongs in a subreddit. You decide what belongs in **your feed**.

The current alpha focuses on five first-class mute targets:

- words / phrases;
- subreddits;
- users;
- domains;
- flairs.

Each mute can be permanent or temporary. Mutes created from a post can also be scoped to that post's subreddit.

## Privacy / trust architecture

ModMyFeed is intentionally boring to audit:

- no account;
- no backend;
- no analytics or telemetry;
- no extension network requests;
- no third-party runtime JavaScript;
- no remote executable code;
- `chrome.storage.local` only;
- Chrome permission: `storage` only;
- content access: `https://www.reddit.com/*` only;
- readable, unminified source.

See `PRIVACY.md` and `VERIFY.md`.

## Support

ModMyFeed is free. If it makes Reddit better for you, optional support is available at:

https://buymeacoffee.com/malcolmb

The extension never contacts Buy Me a Coffee automatically. The link is ordinary user-initiated navigation only.

## License

The source is public for inspection and auditing. A software license has not yet been selected, so do not assume permission to redistribute or create derivative works beyond what applicable law allows.
