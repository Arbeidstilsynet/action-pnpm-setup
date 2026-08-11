# Changelog

## v3

**Breaking change:** Auditing is now opt-in. The `skip-audit` input now defaults to `true`. Consumers that want the action to run `pnpm audit` must explicitly set `skip-audit: false`.

## v2

**Breaking change:** The default `node-version` input has changed from `24.x` to `26.x`. Consumers who rely on the default Node.js version should either update their workflows to take advantage of Node 26, or explicitly pin `node-version: "24.x"` to retain the previous behavior.

## v1

Initial release
