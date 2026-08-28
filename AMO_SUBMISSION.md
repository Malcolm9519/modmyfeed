# AMO submission checklist — ModMyFeed 0.9.2

Use `modmyfeed-firefox-0.9.2-amo.zip` for the first addons.mozilla.org submission.

## Listing basics

**Name:** ModMyFeed — Reddit Feed Moderation

**Summary:** Personal moderation for Reddit. Mute words, subreddits, users, domains, flairs, and common feed clutter locally.

**Suggested categories:** Privacy & Security; Social & Communication (choose the closest options AMO currently offers).

**Support website:** https://github.com/Malcolm9519/modmyfeed/issues

**Homepage:** https://github.com/Malcolm9519/modmyfeed

**Payment required:** No.

## Data collection

The Firefox manifest declares:

```json
"data_collection_permissions": {
  "required": ["none"]
}
```

ModMyFeed does not automatically collect or transmit user data. The GitHub and Buy Me a Coffee links are ordinary user-initiated navigation and do not attach moderation data.

## Reviewer notes

Suggested reviewer note:

> ModMyFeed is a local-only Reddit feed moderation extension. It uses a content script on `https://www.reddit.com/*` to read already-rendered post metadata, apply local rules, and inject a Mute control. The only WebExtension permission is `storage`. There is no background script, backend, analytics, Reddit API access, remote code, or third-party runtime JavaScript. The code is readable and unminified. No account is required. To test, install the add-on, open reddit.com, add a literal phrase mute in the popup, then refresh/scroll the feed; matching posts should collapse with an explanation and Show once/Allow controls.

## License

**MIT License**. The repository includes the full `LICENSE` file. Select MIT in the AMO submission form.

## Before clicking Submit

- Set your AMO developer display name.
- Enter the support email you want users/reviewers to use.
- Select **MIT License**.
- Upload screenshots if the listing flow requests them.
- Link the public privacy/trust docs even though the extension declares no transmitted data.
