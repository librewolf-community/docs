---
title: Autofill
---

## Forms auto fill

### `extensions.formautofill.addresses.enabled

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `extensions.formautofill.available

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | ? |
| LibreWolf  | `"off"` |

### `extensions.formautofill.creditCards.enabled

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `extensions.formautofill.heuristics.enabled

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Require manual intervention to autofill known username/passwords in sign-in forms

### `signon.autofillForms`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

See also:

- http://kb.mozillazine.org/Signon.autofillForms
- https://www.torproject.org/projects/torbrowser/design/#identifier-linkability

## When username/password autofill is enabled, still disable it on non-HTTPS sites

See also:

- https://hg.mozilla.org/integration/mozilla-inbound/rev/f0d146fe7317

### `signon.autofillForms.http`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable inline autocomplete in URL bar

See also:

- http://kb.mozillazine.org/Inline_autocomplete

### `browser.urlbar.autoFill`

Note: Disabled.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `browser.urlbar.autoFill.typed`

Note: Disabled.

This does not cause privacy/leaking issues.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |
