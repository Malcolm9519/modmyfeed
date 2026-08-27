# Install ModMyFeed from GitHub

ModMyFeed is currently a public alpha distributed as readable source from GitHub.

## Install

1. Download `dist/modmyfeed-0.9.2-alpha.zip` from this repository.
2. Extract the ZIP.
3. In Chrome, open `chrome://extensions`.
4. Turn on **Developer mode**.
5. Click **Load unpacked**.
6. Choose the extracted ModMyFeed folder — the folder containing `manifest.json`.
7. Open or refresh `https://www.reddit.com/`.

The ModMyFeed icon should now appear in Chrome's Extensions menu. Pin it if you want quick access.

## Update

GitHub-installed unpacked extensions do not auto-update.

When a new alpha version is released, download the new alpha ZIP, extract it, reload ModMyFeed from `chrome://extensions`, and refresh Reddit.

Your moderation settings live in `chrome.storage.local`, so normal code updates do not require re-creating all of your mutes.

## Uninstall

Open `chrome://extensions` and click **Remove** on ModMyFeed.

## Why Developer Mode?

Until ModMyFeed moves to a signed browser-store distribution channel, Chrome requires unpacked extensions to be installed through Developer Mode. This is useful during alpha testing because you can inspect the exact source before loading it.

If you are not comfortable enabling Developer Mode, do not install the alpha yet.
