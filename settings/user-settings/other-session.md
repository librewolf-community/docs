---
title: Other session
---

# Other session

See also: Pref 2805.

## Disable storing extra session data

Extra session data contains contents of forms, scrollbar positions, cookies and `POST` data.

### `browser.sessionstore.privacy_level`

Set sites on which extra session data should be saved.

| Value | Meaning |
| ----- | ------- |
|  `0`  | everywhere |
|  `1`  | unencrypted sites |
|  `2`  | nowhere |

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | ? |
| LibreWolf  | `2` |

## Set the minimum interval between session save operations

Warning: This can also affect entries in the "Recently Closed Tabs" feature i.e. the longer the interval the more chance a quick tab open/close won't be captured.

This longer interval *may* affect history but we cannot replicate any history not recorded.

See also:

- https://bugzilla.mozilla.org/1304389

### `browser.sessionstore.interval`

Value in milliseconds.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `15000` |
| LibreWolf  | `60000` |
