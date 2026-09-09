# Changelog

## v4

This is the final release of this action. It is deprecated in favor of [pnpm/setup](https://github.com/pnpm/setup). Workflows now emit a deprecation warning, and all inputs are marked deprecated in action metadata.

## v3

**Breaking change:** Auditing is now opt-in. The `skip-audit` input now defaults to `true`. Consumers that want the action to run `pnpm audit` must explicitly set `skip-audit: false`.

## v2

**Breaking change:** The default `node-version` input has changed from `24.x` to `26.x`. Consumers who rely on the default Node.js version should either update their workflows to take advantage of Node 26, or explicitly pin `node-version: "24.x"` to retain the previous behavior.

## v1

Initial release
