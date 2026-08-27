# Contributing to ModMyFeed

Thanks for helping improve ModMyFeed.

## Product principle

The core loop is:

> annoying post → **Mute** → choose exactly what bothers you → gone

Before adding a feature, ask whether it helps a user remove unwanted Reddit feed content more quickly, precisely, reversibly, or safely.

## Trust constraints

Changes to the core extension should preserve these defaults unless there is an explicit product decision to change them:

- no account required;
- no analytics/telemetry;
- no ModMyFeed backend;
- Reddit-only content access;
- minimal Chrome permissions;
- no third-party runtime JavaScript;
- readable, unminified source;
- local moderation state;
- explainable/reversible filtering.

## Development

The project intentionally uses plain Manifest V3 JavaScript, HTML, and CSS.

Run tests with `npm test` from the full source checkout/package.

Please include or update tests for changes to rule matching, permissions, storage behavior, preset definitions, or privacy-sensitive behavior.

## Issues and pull requests

Good bug reports include the Reddit URL/page type, expected behavior, actual behavior, whether refreshing reproduces the issue, and a screenshot or console error when useful.

Please avoid posting private Reddit data that is not necessary to reproduce a problem.
