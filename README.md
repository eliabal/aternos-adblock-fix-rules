# aternos-adblock-fix-rules

Runtime configuration for the **Aternos AdBlock Fix** browser extension.

The extension periodically fetches [`rules.json`](rules.json) from GitHub Pages and
uses it to adjust part of its settings, so small adjustments don't require a new
release on the Chrome Web Store.

- Published at `https://eliabal.github.io/aternos-adblock-fix-rules/rules.json`
- Fetched at most once every few hours and cached locally.
- If the file is unreachable, invalid or partial, the extension keeps using the
  defaults bundled in the build.

## Format

Plain JSON object. Every key is optional and mirrors a bundled default, so a
partial file is valid: what you omit keeps its built-in value. `version` and
`lastUpdate` are informational.

## Updating

Edit `rules.json`, bump `version`, commit. GitHub Pages republishes within a few
minutes; installed extensions pick the change up at their next refresh.
