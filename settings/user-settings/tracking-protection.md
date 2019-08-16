---
title: Tracking Protection
---

## Built-in tracking protection

Firefox now integrates a tracking protection feature (based on disconnect.me). It is a light-list content blocking; the list can not be edited. This feature is disabled in LibreWolf. It's recommended to use UBlock instead. This feature is disabled:

- Until it evolves and integrates at least list editing
- Because double filtering (this + ublock) is not good for performance.

### `privacy.trackingprotection.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable passive Tracking Protection (FF53+)

Passive TP annotates channels to lower the priority of network loads for resources on the tracking protection list.

Note: It has no effect if TP is enabled, but keep in mind that by default TP is
enabled only in Private Windows. This is included for people who want to completely disable Tracking Protection.

See also: https://bugzilla.mozilla.org/buglist.cgi?bug_id=1170190,1141814

### `privacy.trackingprotection.annotate_channels`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `privacy.trackingprotection.lower_network_priority`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `privacy.trackingprotection.pbmode.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Changing block list (Tracking protection)

### `urlclassifier.trackingTable`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `"test-track-simple,base-track-digest256"` |
| LibreWolf  | `""` |

### `pref.privacy.disable_button.change_blocklist`

Since tracking protection is disabled, the button is disabled as well.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |

## contentblocking reportBreakage

### `browser.contentblocking.reportBreakage.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `browser.contentblocking.reportBreakage.url`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | TODO |
| LibreWolf  | `""` |

### `browser.contentblocking.rejecttrackers.reportBreakage.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Third-party cookie UI under preferences

### `browser.contentblocking.rejecttrackers.ui.enabled`

This hides third-party cookie UI. Should lock third-party cookie ui, but third-party cookies are blocked too.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable tracking protection ui list editing under url bar popup

### `browser.contentblocking.trackingprotection.control-center.ui.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable tracking protection ui list editing under preferences

### `browser.contentblocking.trackingprotection.ui.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Other unnecessary CB/TP UI

### `browser.contentblocking.global-toggle.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `browser.contentblocking.rejecttrackers.ui.recommended`

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `browser.contentblocking.fastblock.ui.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `browser.contentblocking.fastblock.control-center.ui.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Tracking Protection Exception List

### `browser.contentblocking.allowlist.annotations.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `browser.contentblocking.allowlist.storage.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable exception button (does not work as expected)

### `pref.privacy.disable_button.tracking_protection_exceptions`

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

This seems to only disable the button; not suitable.

## Third-party cookie ui under url bar

### `browser.contentblocking.rejecttrackers.control-center.ui.enabled`

This disables third-party cookie UI under url bar. This is disabled to leave icon in the URL bar.

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable TP UI

### `browser.contentblocking.ui.enabled`

Fully disable CB/TP ui, this is disabled to leave icon in URL bar.

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Enforce Content Blocking (required to block cookies) (FF63+)

Master switch for all content blocking features (includes tracking protection,
but excludes tracking annotations annotate_channels).

### `browser.contentblocking.enabled`

Other settings already regulate this section's sub-settings (this master switch is not suitable). Disabled because it is needed for blocking third party cookies.

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | `true` |
| LibreWolf  | `false` |
